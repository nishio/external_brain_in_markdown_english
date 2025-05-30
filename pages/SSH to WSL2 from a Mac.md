---
title: "SSH to WSL2 from a Mac"
---

2022/9/22
My main machine is a MacBook, but the only PC with a decent GPU for Stable Diffusion was a Windows gaming PC, so I built the environment with WSL2.
I want to be able to SSH into that gaming PC from my MacBook and control it.

Unlike WSL1, WSL2 has a separate network. So basically, port forwarding is done on the Windows side to the WSL side.

[WSL2 networking features that allow Linux to run almost as is: Windows 10 The Latest - @IT](https://atmarkit.itmedia.co.jp/ait/articles/1909/09/news020.html)
- You're kind enough to write it from how [[Hyper-V]] networking works.
- I didn't know how [[localhost]] is not a single address that points to itself, but one in a special network called 127.0.0.0, which can be accessed via localhost even with different IP addresses.

Step-by-step confirmation.

Run the following in bash to set up an HTTP server with the number 8000
- `$ python -mhttp.server`
Access the following in your Windows browser
- [http://localhost:8000/](http://localhost:8000/)
I could see it! On the other hand.
- [http://192.168.1.13:8000/](http://192.168.1.13:8000/)
This is certainly not visible. I see. I see it this way.
![image](https://gyazo.com/1b783dd098acf7e6a56850d38703d06f/thumb/1000)

Launch PowerShell with administrative privileges to check port forwarding status
powershell

```
> netsh interface portproxy show v4tov4
```


powershell

```
> netsh interface portproxy add v4tov4 listenport=8000 connectaddress=localhost

> netsh interface portproxy show v4tov4
 Listen for ipv4: Connect to ipv4:.

 Address         Port        Address         Port
 --------------- ----------  --------------- ----------
 *               8000        localhost       8000

> sc start iphlpsvc
```

with this
I can now access and view the following in my Windows browser
- [http://192.168.1.13:8000/](http://192.168.1.13:8000/)
On the other hand, I can't see it from my MacBook browser, which means it's being played through the firewall.

"Allow applications through the Windows Firewall" would specify apps❌.
This time we want to specify the port, so go to "Advanced", "Receiving Rules", "Add Rule", "Port".
![image](https://gyazo.com/cd361182c52a789fdf641a2eb1467619/thumb/1000)
![image](https://gyazo.com/d36739f795fbd1f7962939a102f95b41/thumb/1000)
Now you can access it from your MacBook with a browser.

The next step is to set up SSH.
First, in bash
bash

```
$ ssh localhost
ssh: connect to host localhost port 22: Connection refused
```

No connection, i.e., SSH server is not running.
Write public keys in authorized keys.
`$ sudo service ssh start`
I can now connect with bash.

When I SSH from MacBook, it timed out...I opened port 22 on the firewall...but...I only did port forwarding for port 8000...I did port forwarding for port 22 as well, and now I can connect from MacBook. I was able to connect from my MacBook.

---
2022-09-25
- > I'm so bummed that for some reason I can't connect to WSL via SSH anymore.

2022-09-26
powershell

```
netsh interface portproxy show v4tov4
Listen for ipv4: Connect to ipv4:.
Address         Port        Address         Port
--------------- ----------  --------------- ----------
*               22          localhost       22
*               8000        localhost       8000

```

bash

```
$ python -mhttp.server
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
```

[http://localhost:8000/](http://localhost:8000/) NG

bash

```
$ ip -4 address
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
6: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    inet 172.28.171.149/20 brd 172.28.175.255 scope global eth0
       valid_lft forever preferred_lft forever
```


[http://172.28.171.149:8000/](http://172.28.171.149:8000/) OK

Localhost forwarding doesn't seem to be working.

[windows - Localhost refused to connect on WSL2 when accessed via https://localhost:8000/ but works when using internal WSL IP adress - Stack Overflow](https://stackoverflow.com/questions/69926941/localhost-refused-to-connect-on-wsl2-when-accessed-via-https-localhost8000-b)
> When it's working normally, as you are clearly aware, the "localhost forwarding" feature of WSL2 means that you can access services running inside WSL2 using the "localhost" address of the Windows host.
>
>  Sometimes, however, that feature breaks down. This is known to happen when you either:
- >  Hibernate
- >  Have the Windows "Fast Startup" feature enabled (and it is the default). Fast Startup is a pseudo-hibernation which triggers the same problem.
>  Typically the best solution is to disable Hibernation and Fast Startup. However, if you do need these features, you can reset the WSL localhost feature by:
>
>  Exiting any WSL instances
>  Issuing wsl --shutdown
>  Restarting your instance
>  It's my experience that localhost forwarding will work after that.
I tried rebooting the WSL, but it didn't work.

[Fixing WSL2 localhost access issue - abdus.dev](https://abdus.dev/posts/fixing-wsl2-localhost-access-issue/)
> Localhost redirection often fails for some reason, such as when PC sleeps and wakes up, and localhost access to Linux services does not work anymore.

Conclusion: "WSL2's localhost binding is easily broken, so don't trust it and use a direct IP address specification."

powershell

```
> netsh interface portproxy set v4tov4 listenport=8000 connectaddress=172.28.174.254
> netsh interface portproxy set v4tov4 listenport=22 connectaddress=172.28.174.254
```


I can now connect to the HTTP server from my Mac browser.
ssh won't connect, this is because I restarted WSL and sshd is not running.
It's up and running. It's connected.

2022-10-03
[SSH into a WSL2 host remotely and reliably | by Gilad Lekner | Medium](https://medium.com/@gilad215/ssh-into-a-wsl2-host-remotely-and-reliabley-578a12c91a2)
[Allow ssh to Ubuntu on WSL2](https://sunday-morning.app/posts/2020-07-16-wsl2-ubuntu-ssh)

2022-10-10
ip -4 address in bash
You can use that address in the administrator PowerShell.
PS C:\WINDOWS\system32> netsh.exe interface portproxy set v4tov4 listenport=22 connectaddress=172.22.33.108

PS C:\WINDOWS\system32> netsh.exe interface portproxy set v4tov4 listenport=8000 connectaddress=172.22.33.108
>  netsh interface portproxy show v4tov4

Listen for ipv4: Connect to ipv4:.

Address         Port        Address         Port
--------------- ----------  --------------- ----------
*               22          172.22.33.108   22
*               8000        172.22.33.108   8000

>  sc.exe start iphlpsvc
[[SC]] StartService FAILED 1056:

The service instance is already running.



---
This page is auto-translated from [/nishio/WSL2にMacからSSHする](https://scrapbox.io/nishio/WSL2にMacからSSHする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.