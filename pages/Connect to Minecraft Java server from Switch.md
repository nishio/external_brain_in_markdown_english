---
title: "Connect to Minecraft Java server from Switch"
---

Java compatible servers for Minecraft (Spigot, Paper, etc.; I'm using Paper in this article). The one used in this article is Paper).
From Nintendo Switch (i.e. Bedrock Edition)
How to connect [* by IP address

Problems that need to be resolved
- Switch does not have a UI to connect by IP address.

solution
- Domain name resolution performed when connecting to the featured server,
- By having it done by a DNS server for this purpose,
- Connect to the "world selection server" (BedrockConnect) instead of the original server

What the server administrator does
- Introduction of Geyser and Floodgate
    - This is necessary to be able to participate in the Bedrock version
What the client side does
- Change the Switch's DNS settings
    - [Explanatory video](https://www.youtube.com/watch?app=desktop&v=zalT_oR1nPM)
    - DNS connection should be 104.238.130.180
        - This is one of the BedrockConnect servers listed below
            - [Publicly available BedrockConnect instances](https://github.com/Pugmatt/BedrockConnect#publicly-available-bedrockconnect-instances)
- Connect to the featured server
    - ![image](https://gyazo.com/1a31de1139167725abdf73f9205c54cb/thumb/1000)
    - Any connection point.
    - I don't seem to get this world list if I'm not logged in with my MS account.
- Leads to "worlds with implemented world selection UI."
    - ![image](https://gyazo.com/0e0f2f932317037fbfcb93dee5e21c4c/thumb/1000)
- Enter the IP address of the server you want to connect to and connect.
    - ![image](https://gyazo.com/605932dfe098a4bcab696f1f03fda435/thumb/1000)
- I was able to connect to the desired Java version of the server from Switch.
    - ![image](https://gyazo.com/2a07e89f65088fe383fed96a002515f4/thumb/1000)
    - Looks a little different from the Java version (transparency of the picture frame doesn't seem to work).

2022-07-16
- The last time I tried it, it seemed slow and unusable, but I got the impression that "I could play it with no problem, okay?" I was able to play it without any problem..." so I tested it again.
- Last time I set up the server myself, but it was too much trouble, so this time I decided to use a public server.

2022-01-19
- It takes about 20 seconds to log in, much longer than the Java version, but some say the frame rate is perfect, and it seems to be world dependent.

Summary (2021-10-27)
- The connection was made.
- The speed was not realistically playable (about 5 FPS).
- I don't know how to improve it.

![image](https://gyazo.com/8374c001060f835727f5aff6ccc4043a/thumb/1000)
- Server Resource Pack is not applied, not sure how to apply it

way
- Put BIND9 in EC2, set up a DNS server (A), and point a specific domain to your Java version of the server (B).
    - [Setting up on Linux · Pugmatt/BedrockConnect Wiki](https://github.com/Pugmatt/BedrockConnect/wiki/Setting-up-on-Linux)
- Switch's network settings can specify a DNS server, so set it to (A).
    - [Explanatory video](https://www.youtube.com/watch?app=desktop&v=zalT_oR1nPM)
- Note that the Bedrock version will connect to port 19132 via UDP.
    - At first I mistook it for TCP and the firewall was blocking me.
- No need to start BedrockConnect server if you don't need the server selection screen
    - If it's the default configuration, port 19132 should be used, so it should clash with (B), I didn't go too deep because I decided not to activate it.
- The server (B) has a plugin that allows it to receive Bedrock packets.
    - [https://github.com/GeyserMC/Geyser](https://github.com/GeyserMC/Geyser)
    - [https://github.com/GeyserMC/Floodgate/wiki](https://github.com/GeyserMC/Floodgate/wiki)

----log
> [nishio](https://twitter.com/nishio/status/1453246991853621259): I don't know DNS at all (I play Minecraft(?))

> [nishio](https://twitter.com/nishio/status/1453248083354136584): I've installed BIND9 on the EC2 running my mikra, opened the DNS port in the security rules, and set my home router's primary DNS to the EC2 address. I'm trying to make sure I'm doing it right, but when I dig on my MacBook, it says the server is 127.0.0.1, and I'm having a hard time figuring it out.

> [nishio](https://twitter.com/nishio/status/1453248966611644420): I don't even know what to check and isolate the problem because I don't have enough basic network knowledge...

> [kaorun](https://twitter.com/kaorun/status/1453253521344761856): maybe: a company machine with AnyConnect or something

> [nishio](https://twitter.com/nishio/status/1453254117237968903): ah... i see...

> [kaorun](https://twitter.com/kaorun/status/1453254477415387139): It may be different on a Mac, but on a machine with AnyConnect, it seems that the DNS is taken to the AnyConnect side and the local I can't understand DNS in many ways.

> [nishio](https://twitter.com/nishio/status/1453256949051674632): i tried it on an unmanaged machine and it didn't go to 127.0.0.1!

> [nishio](https://twitter.com/nishio/status/1453258106977275909): Hmmm, the DHCP server function was turned off in the router configuration to begin with... where on earth is Switch getting its DNS information from...? I'm not sure where the Switch is getting its DNS information from...?

> [nishio](https://twitter.com/nishio/status/1453258225218899972): i want to do ipconfig and stuff on Switch()

> [nishio](https://twitter.com/nishio/status/1453258650437537794): I see, you didn't have to mess with the router settings in the first place?
> m.youtube.com/watch?v=zalT_o…

> [nishio](https://twitter.com/nishio/status/1453262905756078085): I seem to have succeeded in swapping the connection destination in DNS as it now fails to connect to the server. Next, I'd like to know why it's failing... the video looks like it's sending a dialog once it's connected to the world.

> [nishio](https://twitter.com/nishio/status/1453265751440347143): hmm I don't know, I should leave for once

> [nishio](https://twitter.com/nishio/status/1453291426519867403): I just looked back and finally realized something I almost noticed earlier, but both the "server that brings up the server selection screen" and the "server you want to connect to" are on the same machine. There is no way that Bedrock's port can listen, and the reason I'm not getting an "Already used" error is that one of them is clamping down on the error and can't see it.

> [nishio](https://twitter.com/nishio/status/1453292205792243720): the timeline is that "server X that wants to connect" is started first, so this grabs the port, and "server Y that brings up the server selection screen" fails to listen. I've tried closing Y, but I haven't tried starting Y without starting X. This should be verified.

> [nishio](https://twitter.com/nishio/status/1453302861937393681): >BDS uses UDP, unlike Java Edition which uses TCP.
> AAAAAAHHHH
> minecraft.fandom.com/ja/wiki/Bedroc…

> [nishio](https://twitter.com/nishio/status/1453304155234254848): got through to the world selection server! pic.twitter.com/kp5x6Y6Nbb

> [nishio](https://twitter.com/nishio/status/1453304776674926593): mmmm pic.twitter.com/UlMQhjl0LM

> [nishio](https://twitter.com/nishio/status/1453305501157105666): oh, they released a version for 1.17.40, just replace it.

> [nishio](https://twitter.com/nishio/status/1453308334560346112): done! (Server Resource Pack not applied...) pic.twitter.com/4gis0PD9ok

> [nishio](https://twitter.com/nishio/status/1453312156678586375): and unfortunately seriously low FPS. maybe 5.

> [nishio](https://twitter.com/nishio/status/1453314577790234626): there's plenty of room for server load averages and such, so it looks like it's either the performance of the Switch, or the latency of the packet conversion, which is a bit too easy to solve!
---
This page is auto-translated from [/nishio/Minecraft Java版サーバにSwitchから繋ぐ](https://scrapbox.io/nishio/Minecraft Java版サーバにSwitchから繋ぐ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.