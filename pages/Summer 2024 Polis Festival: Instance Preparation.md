---
title: "Summer 2024 Polis Festival: Instance Preparation"
---

from  [[Summer Polis Festival 2024]]
Summer 2024 Polis Festival: Instance Preparation

2024-06-18

See previous post: [[Polis in EC2]].
- Create an instance with Ubuntu / t2.medium / 8GB as appropriate


Previously, direct clone was done, but this time fork is done.
    - I might do some Japaneseization of the UI.
- [GitHub - compdemocracy/polis: :milky_way: Open Source AI for large scale open ended feedback](https://github.com/compdemocracy/polis)
- ![image](https://gyazo.com/59cc15bdfd0b814b53dc798d337cd407/thumb/1000)
- What's this?
    - I don't know, so let's make it the default.
- [https://github.com/nishio/polis](https://github.com/nishio/polis)
    - ![image](https://gyazo.com/f67f3503e112a32eaad59e85e5d981b1/thumb/1000)
        - hmm

In the meantime, the instance was activated.
![image](https://gyazo.com/00f7959982e7d683ba30c9434fa8ce5c/thumb/1000)![image](https://gyazo.com/047782a83e3b394c143f62e1f7d9d9cf/thumb/1000)

Install Docker
- [Install Docker Engine on Ubuntu | Docker Documentation](https://docs.docker.com/engine/install/ubuntu/)
- Hello world: OK


# install Polis
.
`$ cp example.env .env`
`$ make start`
:

```
docker compose -f docker-compose.yml -f docker-compose.dev.yml --env-file .env up
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.45/containers/json?all=1&filters=%7B%22label%22%3A%7B%22com.docker.compose.config-hash%22%3Atrue%2C%22com.docker.compose.project%3Dpolis-dev%22%3Atrue%7D%7D": dial unix /var/run/docker.sock: connect: permission denied
make: *** [Makefile:34: start] Error 1
```

well
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>This error occurs because the current user does not have permission to access the Docker daemon socket.
- `$ sudo usermod -aG docker $USER`
- `$ newgrp docker`
Build is in motion.
- There's some kind of log going around, but I'm not sure if the build is finished and the server is running or if it's still building.
- `http://<IP>/createuser`
    - It worked.
    - ![image](https://gyazo.com/e64501b8e819a3cb978a668dfddb172e/thumb/1000)
- When you create an account
:

```
server-1       | info: not whitelisted  ... ,"path":"/api/v3/auth/new","service":"polis-api-server","timestamp":"2024-06-18 08:07:22 +00:00"}
server-1       | POST /api/v3/auth/new 500 160.657 ms - 40
server-1       | unauthorized domain: http://<IP>
```

- That's what happened last time.
    - Because it's not on the white list.
    - It's HTTP, it's IP rounding, it's a problem.
    - This was the development mode to begin with.
- I'll try PROD.
    - `$ cp example.env prod.env`
    - `$ make PROD start`
    - I got access.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
1. obtaining and setting up a domain name
2. obtain an SSL certificate with Let's Encrypt
3. configuration of Nginx
    - Set up a reverse proxy using Nginx to support HTTPS.

Eh, sounds like a pain in the ass.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
1. AWS Elastic Beanstalk
- Benefits
    - Easy Deployment: Just upload your code and the infrastructure is automatically built.
    - Reduced management effort: environment scaling, load balancing, and monitoring are automated.
    - Integration: Integrated with ACM for easy HTTPS certificate application.
- Disadvantages: -Disadvantages: -Disadvantages: -Disadvantages: -Disadvantages
    - Limitations: Restrictions apply when a high degree of customization is required.
    - Cost: Can be somewhat higher than other methods.
2. AWS Fargate
- Benefits
    - Serverless: Eliminates the need for infrastructure management.
    - Scalability: Automatic scaling to handle high traffic.
    - Flexibility: Because it uses ECS clusters, it can be configured and customized in detail.
- Disadvantages: -Disadvantages: -Disadvantages: -Disadvantages: -Disadvantages
    - Learning Cost: Some time is required for initial setup and understanding.
    - Cost: Charges are based on usage, so ongoing cost control is necessary.
3. AWS Lightsail
- Benefits
    - Easy setup: The interface is very easy to set up for beginners.
    - Fixed fee: The fee structure is easy to understand and manage budgets.
    - Integration: Easy configuration of SSL certificates and use of load balancers.
- Disadvantages: -Disadvantages: -Disadvantages: -Disadvantages: -Disadvantages
    - Limitations: Not suited for advanced scaling or complex infrastructure setups.
    - Flexibility: Less customizable than other AWS services.
summary
- AWS Elastic Beanstalk: ideal if you want to deploy easily but can accept some limitations.
- AWS Fargate: best if you need flexibility and scalability but can accept the learning costs of initial setup.
- AWS Lightsail: ideal for beginners who want an easy and cost-effective solution.
Each method has its advantages and disadvantages, and it is important to choose the best method for your specific requirements and budget.

I have no idea which one is better.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- GPT4, you got it!
    - →Let's Encrypt + Nginx route
    - I can't judge, so I'll go with that.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Add DNS records for subdomains
- Open the DNS settings for "nhiro.org" and add an A record to point "polis.nhiro.org" to the IP address of the EC2 instance, as shown below.
    - Host Name: polis
    - Type: A
    - TTL: 600 (or default value)
    - Value: EC2 public IP address

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>To check if the DNS has been updated, use the following methods
- nslookup
- dig

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>It seems that your DNS settings are not reflected correctly. Please check the following steps.
2. clear DNS cache
    - macOS
        - `$ sudo killall -HUP mDNSResponder`

Whoa, it's been updated.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
Installation of Nginx
`$ sudo apt update`
`$ sudo apt install -y nginx`
Edit Nginx configuration file
`$ sudo vi /etc/nginx/sites-available/default`
:

```
server {
    listen 80;
    server_name your_domain.com;
    return 301 https://$host$request_uri;
}

server {
    listen 443 ssl;
    server_name your_domain.com;

    ssl_certificate /etc/letsencrypt/live/your_domain.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/your_domain.com/privkey.pem;

    location / {
        proxy_pass http://localhost:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```


With vi, screen is broken, OK with nano.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

Install Certbot
`$ sudo apt install -y certbot python3-certbot-nginx`
Obtaining an SSL Certificate
`$ sudo certbot --nginx -d polis.nhiro.org`

:

```
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Error while running nginx -c /etc/nginx/nginx.conf -t.

2024/06/18 08:59:32 [emerg] 12342#12342: cannot load certificate "/etc/letsencrypt/live/your_domain.com/fullchain.pem": BIO_new_file() failed (SSL: error:80000002:system library::No such file or directory:calling fopen(/etc/letsencrypt/live/your_domain.com/fullchain.pem, r) error:10000080:BIO routines::no such file)
nginx: configuration file /etc/nginx/nginx.conf test failed

The nginx plugin is not working; there may be problems with your existing configuration.
The error was: MisconfigurationError('Error while running nginx -c /etc/nginx/nginx.conf -t.\n\n2024/06/18 08:59:32 [emerg] 12342#12342: cannot load certificate "/etc/letsencrypt/live/your_domain.com/fullchain.pem": BIO_new_file() failed (SSL: error:80000002:system library::No such file or directory:calling fopen(/etc/letsencrypt/live/your_domain.com/fullchain.pem, r) error:10000080:BIO routines::no such file)\nnginx: configuration file /etc/nginx/nginx.conf test failed\n')
```


<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>This error indicates that Nginx cannot load the configuration because the Let's Encrypt certificate does not exist.
There is no way!<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Temporarily comment out the SSL portion from the Nginx configuration.

:

```
$ sudo certbot --nginx -d polis.nhiro.org
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Enter email address (used for urgent renewal and security notices)
 (Enter 'c' to cancel): nishio.hirokazu@gmail.com 

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Please read the Terms of Service at
https://letsencrypt.org/documents/LE-SA-v1.4-April-3-2024.pdf. You must agree in
order to register with the ACME server. Do you agree?
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(Y)es/(N)o: y

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Would you be willing, once your first certificate is successfully issued, to
share your email address with the Electronic Frontier Foundation, a founding
partner of the Let's Encrypt project and the non-profit organization that
develops Certbot? We'd like to send you email about our work encrypting the web,
EFF news, campaigns, and ways to support digital freedom.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(Y)es/(N)o: y
Account registered.
Requesting a certificate for polis.nhiro.org

Successfully received certificate.
Certificate is saved at: /etc/letsencrypt/live/polis.nhiro.org/fullchain.pem
Key is saved at:         /etc/letsencrypt/live/polis.nhiro.org/privkey.pem
This certificate expires on 2024-09-16.
These files will be updated when the certificate renews.
Certbot has set up a scheduled task to automatically renew this certificate in the background.

Deploying certificate
Successfully deployed certificate for polis.nhiro.org to /etc/nginx/sites-enabled/default
Congratulations! You have successfully enabled HTTPS on https://polis.nhiro.org

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
If you like Certbot, please consider supporting our work by:
 * Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
 * Donating to EFF:                    https://eff.org/donate-le
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```

I heard it was done?

:

```
$ sudo systemctl restart nginx
Job for nginx.service failed because the control process exited with error code.
See "systemctl status nginx.service" and "journalctl -xeu nginx.service" for details.
```


:

```
Jun 18 09:04:06 ip-172-31-37-50 nginx[12385]: 2024/06/18 09:04:06 [emerg] 12385#12385: cannot load certificate "/etc/letsencrypt/live/your_domain.com/fullchain.pem": BIO_new_file() failed (>
Jun 18 09:04:06 ip-172-31-37-50 nginx[12385]: nginx: configuration file /etc/nginx/nginx.conf test failed
```

Uh, `certificate "/etc/letsencrypt/live/your_domain.com/fullchain.pem"`
- I didn't know `your_domain.com` was still there.

`$ sudo systemctl restart nginx`
- This time he says nothing. Success?

Activate Polis
:

```
Error response from daemon: driver failed programming external connectivity on endpoint polis-dev-nginx-proxy-1 (432b7de15349df46efb04a246102c6e420b7fdd790f2d3580a4ad0afc313a5cd): Error starting userland proxy: listen tcp4 0.0.0.0:443: bind: address already in use
```

Ahhhhhh...

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
First, check which process is using port 443.
- `$ sudo lsof -i :443`
Well, usually nginx.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

If a process using port 443 is unnecessary, stop it. For example, if Nginx is already running, stop it.
`$ sudo systemctl stop nginx`

Once the port is released, start the Nginx container again.

This time it seems to be working properly, but when I access it from my browser, it doesn't respond... haha, that's the one!
![image](https://gyazo.com/426f81bb560937f83463a1298af31a82/thumb/1000)
443 is not enough
- I've made this mistake 100 times in my life (exaggeration).

![image](https://gyazo.com/f213f68acb74c12ef23164f7b24a7ea1/thumb/1000)
Well, why not?
![image](https://gyazo.com/4c7ea8af3dc9a8dbe33e0aca9e940f98/thumb/1000)
Why invalid?
![image](https://gyazo.com/27c8b19fe6415a83505e6f34882f8cbb/thumb/1000)
Ehhhhhh...

〜〜〜

Oh, I remember reading in the Polis side documentation that the default is a test certificate!
I guess I need to change the settings on the Polis side.
[polis/docs/ssl.md at edge · nishio/polis](https://github.com/nishio/polis/blob/edge/docs/ssl.md)
rewrite
`$ sudo systemctl restart nginx`

:

```
$ sudo nginx -t
2024/06/18 14:18:04 [warn] 53602#53602: conflicting server name "polis.nhiro.org" on 0.0.0.0:443, ignored
```


:

```
ubuntu@ip-172-31-37-50:~/polis$ grep -r "server_name polis.nhiro.org" /etc/nginx/
/etc/nginx/sites-available/default:    server_name polis.nhiro.org;
/etc/nginx/sites-available/default:    server_name polis.nhiro.org;
/etc/nginx/sites-available/default:    server_name polis.nhiro.org;
ubuntu@ip-172-31-37-50:~/polis$ grep -r "server_name polis.nhiro.org" .
./file-server/nginx/nginx-ssl.site.default.conf:    server_name polis.nhiro.org;
```


Copying configuration files in nginx.Dockerfile
[[Polis#646c4176aff09e0000018cef on EC2]]
Don't mess with the Dockerfile, point to the letsencrypt certificate in the conf

Something doesn't work, let's go to bed.


2024-06-19
Go to sleep, wake up and think again with a clear head.

First of all, you should verbalize and transmit what you're trying to do and for what purpose.
- I wrote in the opening section

Current Issues
- My technical skills around servers are low and I'm stumped.

First calmly check what is happening in order from the entry point
[https://github.com/nishio/polis](https://github.com/nishio/polis)
opened with [[cursor]].

What happens when I make PROD start?


When you run make PROD start, the following happens
PROD target is executed: 1.
ENV_FILE is set to prod.env.
TAG is taken from the prod.env file.
COMPOSE_FILE_ARGS is set to -f docker-compose.yml.
2. start Target is executed: 1.
The echo_vars target is executed and the current ENV_FILE and TAG values are displayed.
The docker compose command starts all Docker containers using COMPOSE_FILE_ARGS and ENV_FILE.
The specific command flow is as follows
make

```
PROD: ## Run in prod mode (e.g. `make PROD start`, etc.) using config in `prod.env`
	$(eval ENV_FILE = prod.env)
	$(eval TAG = $(shell grep -e ^TAG ${ENV_FILE} | awk -F'[=]' '{gsub(/ /,"");print $$2}'))
	$(eval COMPOSE_FILE_ARGS = -f docker-compose.yml)

start: echo_vars ## Start all Docker containers
	docker compose ${COMPOSE_FILE_ARGS} --env-file ${ENV_FILE} up
```

This results in a Docker container being launched based on the settings in the prod.env file.


What happens when docker-compose.yml is executed?


When docker-compose.yml is executed, the following happens
Containers are created and started based on the service definition: 1.
The server, math, postgres, nginx-proxy, and file-server services are defined, and a Docker image corresponding to each service is built or pulled.
Each service is started according to the specified environment variables, volume, and network settings.
Network creation: 1.
A custom network called polis-net is created and all services are connected to this network.
3. volume creation: (1)
Volumes named backups, postgres, and server-logs are created and mounted on the corresponding services.
The specific service operation is as follows
server:
. Build a Docker image from the /server directory and use the prod target.
Store logs in the server-logs volume.
Depends on postgres and file-server.
math:
. /math directory to build the Docker image.
Set necessary environment variables.
Depends on postgres.
postgres:
. /server directory to build an image using Dockerfile-db.
Set database environment variables.
backups and postgres volumes.
nginx-proxy:
. Build an image from the /file-server directory using nginx.Dockerfile.
Depends on server.
Ports 80 and 443 are exposed to the host.
file-server:
Build the image from the root directory using file-server/Dockerfile.
Set necessary environment variables.
This allows all services to work together and launch the entire application.

(Is there a file for nginx-proxy in file-server? <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>)


I'm trying to solve the problem of Nginx using a test certificate, should I read nginx.Dockerfile next?


Yes, then reading the nginx.Dockerfile is a good approach: by reviewing the nginx.Dockerfile, you can understand the build process of the Nginx image and which certificates are being used.
Please pay particular attention to the following points for confirmation
1. a copy of the certificate: 1.
Where in the Dockerfile the certificate file is copied from.
In which directory it is located.
Nginx configuration files: 1.
How the certificate path is specified in the Nginx configuration file.
Build Context: 3.
Does the build context contain the correct certificate file?
By reviewing this information, you can determine the cause of problems that result in test certificates being used and correct them to use the appropriate certificates.


In the nginx.Dockerfile I have a copy of the configuration file and the test certificate. I assume if I edit the configuration file properly it will read the production certificate?


Yes, you can configure Nginx to use a production certificate by properly editing its configuration file. You may wish to proceed as follows
Prepare certificate for production: 1.
Place the production certificate (cert.pem) and private key (key.pem) in the appropriate directories.
Edit Nginx configuration file: 1.
Edit the file nginx/nginx-ssl.site.default.conf and specify the paths for the production certificate and private key.
As an example, edit part of the Nginx configuration file as follows
:

```
server {
    listen 443 ssl;
    server_name your_domain.com;

    ssl_certificate /etc/nginx/certs/your_production.cert.pem;
    ssl_certificate_key /etc/nginx/certs/your_production.key.pem;

    # Other settings
}
```


Dockerfile modification: 1.
Modify nginx.Dockerfile to copy the production certificate to the Docker image.
:

```
FROM docker.io/nginx:1.21.5-alpine
COPY nginx/nginx-ssl.site.default.conf /etc/nginx/conf.d/default.conf
COPY nginx/certs/your_production.cert.pem /etc/nginx/certs/your_production.cert.pem
COPY nginx/certs/your_production.key.pem /etc/nginx/certs/your_production.key.pem

EXPOSE 80
EXPOSE 443
```

This allows Nginx to be started with a production certificate.


Ahh! Okay, okay.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
You have to copy the certificate on the host machine to the Docker image, but you're specifying it by path with the same machine's feelings, that's it.

 dockerfile

```
COPY /etc/letsencrypt/live/polis.nhiro.org/fullchain.pem /etc/nginx/certs/nhiro-fullchain.pem
COPY /etc/letsencrypt/live/your_domain.com/privkey.pem /etc/nginx/certs/nhiro-privkey.pem
```


 nginx/nginx-ssl.site.default.conf

```
ssl_certificate /etc/nginx/certs/nhiro-fullchain.pem;
ssl_certificate_key /etc/nginx/certs/nhiro-privkey.pem;
```



I make PROD start but my browser continues to warn me about the test certificate, why?


If you continue to get a test certificate warning in your browser after running make PROD start, there are several possible causes. Please check the following points
Docker image cache: 1.
The Docker image may be cached. Try disabling the cache and build again.
cache
Reload Nginx configuration: 1.
Nginx may not have loaded the new configuration; try restarting the Nginx container.
proxy
3. check the certificate path:.
Make sure the correct certificate is copied in the nginx.Dockerfile. Also, make sure that the correct path is specified in the Nginx configuration file.
Certificate validity: 4.
Verify that the certificate for production has been issued correctly and has not expired.
Browser cache: 5.
Your browser cache may be causing an outdated certificate to be displayed. Try clearing your browser cache.
6. check Docker Compose file: (1)
Make sure you have the correct configuration in the docker-compose.yml file. In particular, check the configuration of the Nginx container.
If these points do not resolve the problem, specific error messages or logs may help identify the cause of the problem.


It looks like we'll have the means to do 1 or 2 with make.


You may have a way to disable the cache of the Docker image using the make command, rebuild it, and restart the Nginx container. Check the target in the Makefile below:
Build with cache disabled: 1.
A build-no-cache target is provided. This can be used to build Docker images without caching.

2. restart container:.
A start-recreate target is provided. This can be used to recreate and start the container.

Running a combination of these commands may solve the problem.

- [[Monitoring with CloudWatch]] 1


Oh, make is rubbing off.
:

```
------
 > [nginx-proxy 5/6] COPY /etc/letsencrypt/live/polis.nhiro.org/fullchain.pem /etc/nginx/certs/nhiro-fullchain.pem:
------
------
 > [nginx-proxy 6/6] COPY /etc/letsencrypt/live/your_domain.com/privkey.pem /etc/nginx/certs/nhiro-privkey.pem:
------
failed to solve: failed to compute cache key: failed to calculate checksum of ref fdb69f4f-67cc-489f-8061-2f3a24921a15::imnifc4l0wil7tzgrsjx1ezl9: "/etc/letsencrypt/live/your_domain.com/privkey.pem": not found
make: *** [Makefile:61: build-no-cache] Error 17
```


Is it because the owner is root?


:

```
27.89 Downloading: com/cnuernber/jarrow/1.000/jarrow-1.000.jar from clojars
27.90 Error building classpath. Could not transfer artifact org.apache.commons:commons-math3:jar:3.6.1 from/to central (https://repo1.maven.org/maven2/): No space left on device
------
failed to solve: process "/bin/sh -c clojure -A:dev -P" did not complete successfully: exit code: 1
make: *** [Makefile:61: build-no-cache] Error 17
```



procedure
Check disk space: 1.
Check the disk space on the host machine.
- `$ df -h`
Delete unnecessary files: 1.
Delete unneeded files, old Docker images, containers, and volumes to free up disk space.
:

```
    # Delete all suspended containers
    docker container prune

    # Remove all unused images
    docker image prune -a

    # Delete all unused volumes
    docker volume prune

    # Remove all unused networks
    docker network prune
```


before

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root       6.8G  6.5G  217M  97% /
```


after

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root       6.8G  6.0G  752M  90% /
```

No, but it's still a cutthroat job.

:

```
------
 > [file-server client-participation 4/6] RUN npm ci --production=false:
1.505 npm warn config production Use `--omit=dev` instead.
47.22 npm warn tar TAR_ENTRY_ERROR ENOSPC: no space left on device, write
47.28 npm notice
47.28 npm notice New minor version of npm available! 10.7.0 -> 10.8.1
47.28 npm notice Changelog: https://github.com/npm/cli/releases/tag/v10.8.1
47.28 npm notice To update run: npm install -g npm@10.8.1
47.28 npm notice
47.29 npm error code ENOSPC
47.29 npm error syscall write
47.29 npm error errno -28
47.29 npm error nospc ENOSPC: no space left on device, write
47.29 npm error nospc There appears to be insufficient space on your system to finish.
47.29 npm error nospc Clear up some disk space and try again.
47.30 
47.30 npm error A complete log of this run can be found in: /root/.npm/_logs/2024-06-19T05_44_05_167Z-debug-0.log
------
------
 > [file-server client-report 6/7] COPY client-report/. .:
------
failed to solve: process "/bin/sh -c npm ci --production=false" did not complete successfully: exit code: 228
make: *** [Makefile:61: build-no-cache] Error 17
```


That's no good!

:

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root       6.8G  6.4G  359M  95% /
```


:

```
    sudo apt-get clean
    sudo apt-get autoremove
```


:

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root       6.8G  6.2G  577M  92% /
```




I want to expand, EC2.


To expand the disk space of an EC2 instance, perform the following steps
procedure
Stop EC2 instance: 1.
First, stop the EC2 instance.

EBS volume resizing: 1.
Log in to the EC2 Management Console and locate the EBS volume attached to the target instance.
Select a volume and choose "Change Volume" from the "Action" menu.
Save the changes with the new size.

Start EC2 instance: 1.
Restart the instance.

File system extensions: 1.
Connect to the instance via SSH and extend the file system.
:

```
    # Check root file system device name
    lsblk

    # Assume root file system is /dev/xvda1
    sudo growpart /dev/xvda 1

    # Extend file system
    sudo resize2fs /dev/xvda1
```



> Log in to the EC2 Management Console and locate the EBS volume attached to the target instance.
![image](https://gyazo.com/db22e35a7f140bde02961a3653ed375a/thumb/1000)
hmm
![image](https://gyazo.com/8e34baa2baa0825a41c07ba63a211062/thumb/1000)
![image](https://gyazo.com/90a31dd0749d83ae2fa54c2b4ac4a5ff/thumb/1000)
- Can I start an instance with optimizing (0%)?

:

```
$ lsblk
NAME     MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
loop0      7:0    0 25.2M  1 loop /snap/amazon-ssm-agent/7983
loop1      7:1    0 55.7M  1 loop /snap/core18/2812
loop2      7:2    0 25.2M  1 loop /snap/amazon-ssm-agent/7993
loop3      7:3    0 55.7M  1 loop /snap/core18/2823
loop4      7:4    0 38.7M  1 loop /snap/snapd/21465
loop5      7:5    0 38.8M  1 loop /snap/snapd/21759
xvda     202:0    0   16G  0 disk 
├─xvda1  202:1    0   15G  0 part /
├─xvda14 202:14   0    4M  0 part 
├─xvda15 202:15   0  106M  0 part /boot/efi
└─xvda16 259:0    0  913M  0 part /boot
```


:

```
$ sudo growpart /dev/xvda 1
NOCHANGE: partition 1 is size 31455199. it cannot be grown
```


If you look closely, you'll see that we've already done the growpart equivalent.

:

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root        15G  6.2G  8.3G  43% /
```

File system already extended?

rebuild
error
Ah!
:

```
COPY /etc/letsencrypt/live/polis.nhiro.org/fullchain.pem /etc/nginx/certs/nhiro-fullchain.pem
COPY /etc/letsencrypt/live/your_domain.com/privkey.pem /etc/nginx/certs/nhiro-privkey.pem
```

Your_domain.com"...


While waiting for the build, I need to update the DNS because the instance restart changed the IP address.
52.91.132.130

![image](https://gyazo.com/d94651674606127524eba837083a2c0e/thumb/1000)
I'm not sure I need an agent to get DiskRead or something.



To rebuild only the nginx-proxy container, perform the following steps
:

```
# Stop nginx-proxy container
docker compose stop nginx-proxy

# Remove nginx-proxy container
docker compose rm -f nginx-proxy

# Build nginx-proxy container
docker compose build nginx-proxy

# Restart nginx-proxy container
docker compose up -d nginx-proxy
```



:

```
=> ERROR [nginx-proxy 5/6] COPY /etc/letsencrypt/live/polis.nhiro.org/fullchain.pem /etc/nginx/certs/nhiro-fullchain.pem                                                           0.0s
 => ERROR [nginx-proxy 6/6] COPY /etc/letsencrypt/live/polis.nhiro.org/privkey.pem /etc/nginx/certs/nhiro-privkey.pem                                                               0.0s
------
 > [nginx-proxy 5/6] COPY /etc/letsencrypt/live/polis.nhiro.org/fullchain.pem /etc/nginx/certs/nhiro-fullchain.pem:
------
------
 > [nginx-proxy 6/6] COPY /etc/letsencrypt/live/polis.nhiro.org/privkey.pem /etc/nginx/certs/nhiro-privkey.pem:
------
failed to solve: failed to compute cache key: failed to calculate checksum of ref fdb69f4f-67cc-489f-8061-2f3a24921a15::y630wak98lsqz4tftvmxyloof: "/etc/letsencrypt/live/polis.nhiro.org/privkey.pem": not found
make: *** [Makefile:61: build-no-cache] Error 17
```


abbr. of particle "ni" (used especially when it precedes the verb "naru")
`$ sudo ls /etc/letsencrypt/live/polis.nhiro.org/privkey.pem`
/etc/letsencrypt/live/polis.nhiro.org/privkey.pem

Even though there are?


1. check Docker build context
The COPY command in the Dockerfile refers to a file in the build context. The build context may not contain /etc/letsencrypt/live/polis.nhiro.org/privkey.pem.
Method 1: Copy the certificate into the Docker build context
1. copy the certificate file to the project directory
Copy the certificate file into the project directory.


If you copy it, the certbot will keep using the old one when it updates, so maybe you should ln -s it.


It is a good idea to use ln -s to create a symbolic link. This will ensure that Certbot automatically uses the new certificate when it updates it.


such
:

```
COPY nginx/cert/nhiro-fullchain.pem  /etc/nginx/certs/nhiro-fullchain.pem
COPY nginx/cert/nhiro-privkey.pem /etc/nginx/certs/nhiro-privkey.pem
```



:

```
 => ERROR [nginx-proxy 5/6] COPY nginx/cert/nhiro-fullchain.pem  /etc/nginx/certs/nhiro-fullchain.pem                                                                               0.0s
 => ERROR [nginx-proxy 6/6] COPY nginx/cert/nhiro-privkey.pem /etc/nginx/certs/nhiro-privkey.pem                                                                                    0.0s
------
 > [nginx-proxy 5/6] COPY nginx/cert/nhiro-fullchain.pem  /etc/nginx/certs/nhiro-fullchain.pem:
------
------
 > [nginx-proxy 6/6] COPY nginx/cert/nhiro-privkey.pem /etc/nginx/certs/nhiro-privkey.pem:
------
failed to solve: failed to compute cache key: failed to calculate checksum of ref fdb69f4f-67cc-489f-8061-2f3a24921a15::m8mkj6rtbq8r4rggxmzjlbgkw: "/nginx/cert/nhiro-privkey.pem": not found
make: *** [Makefile:61: build-no-cache] Error 17
```

gah
- "/nginx/cert/nhiro-privkey.pem"
- Why access /nginx in this context is a mystery
- I decided to cp without ln -s
    - I thought we cp'd last time.
    - We'll figure out how to renew the certificate later.

I've been distracted by the "why /nginx?", but it's `certs`, not `cert`.

Finally fixed!

- [[Monitoring with CloudWatch]] 2


Certificate error resolved but "Connection refused at polis.nhiro.org". to "polis.nhiro.org".

:

```
$ docker logs polis-dev-nginx-proxy-1
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: /etc/nginx/conf.d/default.conf differs from the packaged version
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2024/06/19 08:48:42 [emerg] 1#1: cannot load certificate key "/etc/nginx/certs/nhiro-privkey.pem": PEM_read_bio_PrivateKey() failed (SSL: error:0909006C:PEM routines:get_name:no start line:Expecting: ANY PRIVATE KEY)
nginx: [emerg] cannot load certificate key "/etc/nginx/certs/nhiro-privkey.pem": PEM_read_bio_PrivateKey() failed (SSL: error:0909006C:PEM routines:get_name:no start line:Expecting: ANY PRIVATE KEY)
```


Calmly look at the dockerfile again.
:

```
FROM docker.io/nginx:1.21.5-alpine

COPY nginx/nginx-ssl.site.default.conf /etc/nginx/conf.d/default.conf

# We only use these in testing.
COPY nginx/certs/snakeoil.cert.pem /etc/nginx/certs/snakeoil.cert.pem
COPY nginx/certs/snakeoil.key.pem  /etc/nginx/certs/snakeoil.key.pem

COPY nginx/certs/nhiro-fullchain.pem  /etc/nginx/certs/nhiro-fullchain.pem
COPY nginx/certs/nhiro-privkey.pem /etc/nginx/certs/nhiro-privkey.pem

EXPOSE 80
EXPOSE 443
```


I'm not wrong.


1. check the contents of the certificate file
Verify that the contents of the nhiro-privkey.pem file are in the correct format. Make sure the file begins with -----BEGIN PRIVATE KEY----- or -----BEGIN RSA PRIVATE KEY----- and ends with -----END PRIVATE KEY----- or -----END RSA PRIVATE KEY-----. Make sure that the

Verify that the permissions on the certificate file are correct. Verify that Nginx has read permission to the file.
sudo chmod 644 /path/to/your/project/nginx/cert/nhiro-privkey.pem

Ahhhh, 600...<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

It finally worked!
![image](https://gyazo.com/64e5abe391390d648c294818eb5a1c39/thumb/1000)
Known to be unauthorized domain

.env

```
# If you are running polis on a custom domain, set both API_PROD_HOSTNAME and DOMAIN_OVERRIDE
# to the same value. In the future these will be combined into one setting.
API_PROD_HOSTNAME=pol.is
DOMAIN_OVERRIDE=
```

Here.
.env

```
API_PROD_HOSTNAME=polis.nhiro.org
DOMAIN_OVERRIDE=polis.nhiro.org
```

Like this.

![image](https://gyazo.com/70cec473da1d47fbb8ef80b2d25a01f3/thumb/1000)
Isn't it `https://polis.nhiro.org`?

:

```
info: not whitelisted {"headers":{"accept":"application/json, text/javascript, */*; q=0.01","accept-encoding":"gzip, deflate, br, zstd","accept-language":"ja,en-US;q=0.9,en;q=0.8,zh;q=0.7,zh-CN;q=0.6,zh-HK;q=0.5,zh-TW;q=0.4","cache-control":"max-age=0","connection":"close","content-length":"97","content-type":"application/json; charset=UTF-8","host":"polis.nhiro.org","origin":"https://polis.nhiro.org","priority":"u=1, i","referer":"https://polis.nhiro.org/createuser","sec-ch-ua":"\"Google Chrome\";v=\"125\", \"Chromium\";v=\"125\", \"Not.A/Brand\";v=\"24\"","sec-ch-ua-mobile":"?0","sec-ch-ua-platform":"\"macOS\"","sec-fetch-dest":"empty","sec-fetch-mode":"cors","sec-fetch-site":"same-origin","user-agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36","x-forwarded-proto":"https","x-requested-with":"XMLHttpRequest"},"path":"/api/v3/auth/new","service":"polis-api-server","timestamp":"2024-06-19 09:34:40 +00:00"}
POST /api/v3/auth/new 500 4.790 ms - 45
unauthorized domain: https://polis.nhiro.org
```


well ... (used before sentences expressing a doubt)
> Could --- [[Polis#646d8611aff09e0000bf04d0 on EC2]].
- How was it done?

I remember last time I was confused about having .env and prod.env, and this time I've been using prod.env all along.
:

```
# Optionally give the server container a distinct env_file. Useful for CI tests.
SERVER_ENV_FILE=.env
```

Maybe it's bad to leave this as the default value in prod.env?

Rather, the domainOverride is null, but even if you `make PROD start`, the `prod.env` is not being read.
:

```
$ make PROD start
make: 'PROD' is up to date.
ENV_FILE=prod.env
TAG=dev
docker compose -f docker-compose.yml --env-file prod.env up
```

I don't think so.

2024-06-21
It is unnatural that prod.env should be read but domainOverride is null, so check there.

- [[Monitoring with CloudWatch]]

- [[Create a list of questions for the Polis test]]

feedback
- Hosted by: fly.io
- Certificate Options: AWS Certificate manager
    - > ACM and connect it to ALB, where it will be SSL terminated, and the server side will return only HTTP.
- Cloudwatch does not have memory monitoring and requires customization, so it may be easier to use a SaaS such as datadog.

2024-06-22
I haven't taken the time at all w

before
`SERVER_ENV_FILE=`
after
`SERVER_ENV_FILE=prod.env`
`$ make build-no-cahce`

:

```
services:
  server:
    env_file:
      - ${SERVER_ENV_FILE:-.env}
```

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- SERVER_ENV_FILE is an environment variable that specifies the path to the .env file. The value of this environment variable may change the configuration and behavior of the service. Details are shown below.
    - If not specified (default value .env): .
        - The server uses .env files in the root directory of the project.
            - Uh huh.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
                - I think you're getting a little too mixed up...
    - If a specific file is specified:.
        - For example, if SERVER_ENV_FILE=.env.production is specified, the server will use the .env.production file.


:

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root        15G   15G  253M  99% /
```

Would you use as much as you had if you had it?
:

```
    # Delete all suspended containers
    docker container prune
    # Remove all unused images
    docker image prune -a
    # Delete all unused volumes
    docker volume prune
    # Remove all unused networks
    docker network prune
```

:

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root        15G   14G  627M  96% /
```

What's bulky?
:

```
$ sudo du -h --max-depth=1 /
12G     /var
```

:

```
/var$ sudo du -h --max-depth=1 .
12G     ./lib
```

:

```
/var/lib$ sudo du -h --max-depth=1 .
11G     ./docker
```

:

```
$ docker system prune
WARNING! This will remove:
  - all stopped containers
  - all networks not used by at least one container
  - all dangling images
  - unused build cache

Are you sure you want to continue? [y/N] y
Deleted build cache objects:
...
Total reclaimed space: 7.928GB
```

Oh, this one.
:

```
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root        15G  3.5G   12G  24% /
```

Maybe if they'd realized they should have erased the build cache, they wouldn't have needed to expand the disk.

return
`$ make build-no-cahce`
`$ make PROD start`
![image](https://gyazo.com/80b314a50c1df680e3a7533ebb239204/thumb/1000)
It's done!


---
This page is auto-translated from [/nishio/2024年夏Polis祭り:インスタンスの準備](https://scrapbox.io/nishio/2024年夏Polis祭り:インスタンスの準備) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.