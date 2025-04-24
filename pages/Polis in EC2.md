---
title: "Polis in EC2"
---

summary
- Create an instance with Ubuntu / t2.medium / 8GB as appropriate
- Install Docker
- Install Polis
    - SSL certificate required if running on anything other than localhost


log on 2023-05-22
Create an instance with Ubuntu / t2.micro / 8GB as appropriate
- As soon as I started the instance, I got a screen that looked like I could connect to the terminal from the browser, and I thought, "I guess I'm in good shape now," and clicked on it, but then I got discouraged because I couldn't connect because the instance was still running.

Install Docker
- [Install Docker Engine on Ubuntu | Docker Documentation](https://docs.docker.com/engine/install/ubuntu/)
- Hello world: OK

Install Polis
- [GitHub - compdemocracy/polis: Open Source AI for large scale open ended feedback](https://github.com/compdemocracy/polis)
- `$ git clone https://github.com/compdemocracy/polis.git`
- `$ sudo apt install make`
- Follow the README
- `$ cp example.env .env`
- `$ make start`
    - `docker compose -f docker-compose.yml -f docker-compose.dev.yml --env-file .env up`
    - ERROR: `permission denied while trying to connect to the Docker daemon ...`
    - <img src='https://scrapbox.io/api/pages/nishio-en/gpt-4/icon' alt='gpt-4.icon' height="19.5"/>
        - The Docker daemon runs as the root user and by default no other user can interact with it. This is why you get "permission denied" errors.
        - Try the following steps to resolve this issue:
            - Adding a user to the docker group: This is the recommended way to solve this problem. You can add a user to the docker group with the following command
            - `$ sudo usermod -aG docker $USER`
        - After executing this command, you must log out and log in again to reevaluate your group membership.
    - Fixed!

The build is not finished after 10 minutes.
- Was the t2.micro too small?
- Let's try t2.medium
- [Amazon EC2 T2 Instance | AWS](https://aws.amazon.com/jp/ec2/instance-types/t2/)

SSL Certificate
- ![image](https://gyazo.com/c0e9f95d8c7b2a598a88e4aaa860b009/thumb/1000)
- > The Docker Compose infrastructure described in the main README uses an insecure self-signed SSL certificate. This is pre-generated and stored publicly in the source code. This HTTPS implementation is only suitable for testing.
    - [polis/ssl.md at edge · compdemocracy/polis · GitHub](https://github.com/compdemocracy/polis/blob/edge/docs/ssl.md)
- I'll do it later.

create account
- ERROR: `unauthorized domain: https://3.87.68.32`
server.ts

```typescript
if (
  !domainOverride &&
  !hasWhitelistMatches(host) &&
  !routeIsWhitelistedForAnyDomain
) {
  logger.info("not whitelisted", { headers: req.headers, path: req.path });
  return next("unauthorized domain: " + host);
}
```

- `.env`
    - ![image](https://gyazo.com/a8cdf4dc6d10f29fc4c0ddc4a109dc70/thumb/1000)
- I'm not on localhost, so I don't know if I need to do any configuration around this.
- It's done.
    - ![image](https://gyazo.com/8ad5ca4a532c28ff9da40035e9309f92/thumb/1000)

SSL Certificate
- Add an A record to the DNS that you manage.
- Confirmation that nslookup can be pulled properly
- Try accessing the site with a browser
    - > Can't access this site DNS_PROBE_FINISHED_NXDOMAIN
    - <img src='https://scrapbox.io/api/pages/nishio-en/gpt-4/icon' alt='gpt-4.icon' height="19.5"/>Local DNS Cache: Your computer stores a local DNS cache to speed up the resolution of domain names. If this cache is outdated or corrupt, it can cause this error. You can clear your local DNS cache with the following command ...
        - (OSX) `% sudo killall -HUP mDNSResponder`
    - Changed to ERR_CONNECTION_REFUSED
        - Oh, I didn't start the server.
- Let's Encrypt certbot uses 80, so not with Polis server built
:

```
Certbot failed to authenticate some domains (authenticator: standalone). The Certificate Authority reported these problems:
  Domain: *****
  Type:   dns
  Detail: DNS problem: NXDOMAIN looking up A for ***** - check that a DNS record exists for this domain; DNS problem: NXDOMAIN looking up AAAA for ***** - check that a DNS record exists for this domain
```

- I thought it was the DNS, so I waited a bit or something, but no, this is not it.
    - EC2 security rules only opened 443 and 22.
    - Open 80 and make sure it is accessible from the outside.
        - `$ sudo python3 -mhttp.server 80`
- > [@nishio](https://twitter.com/nishio/status/1660488886341234690?s=20): I don't know how to make an SSL certificate or anything, but I have a layman's question: I'm trying to make a certificate with Let's Encrypt for a subdomain that I newly added an A record to the DNS about 30 minutes ago. I'm trying to make a certificate with Let's Encrypt for a subdomain to which I newly added an A record in DNS about 30 minutes ago, and I get an NXDOMAIN error.
    - (I may have simply misplaced the domain name, orz)

The certificate is ready.
Tweak `file-server/nginx.Dockerfile` and `file-server/nginx/nginx-ssl.site.default.conf
- The `nginx-ssl.site.default.conf` is copied
diff

```
--- a/file-server/nginx.Dockerfile
+++ b/file-server/nginx.Dockerfile
@@ -1,10 +1,12 @@
 FROM docker.io/nginx:1.21.5-alpine
 
-COPY nginx/nginx-ssl.site.default.conf /etc/nginx/conf.d/default.conf
+COPY nginx/nginx-ssl.site.nhiro.conf /etc/nginx/conf.d/default.conf
 
 # We only use these in testing.
 COPY nginx/certs/snakeoil.cert.pem /etc/nginx/certs/snakeoil.cert.pem
 COPY nginx/certs/snakeoil.key.pem  /etc/nginx/certs/snakeoil.key.pem
+COPY fullchain.pem /etc/nginx/certs/fullchain.pem
+COPY privkey.pem /etc/nginx/certs/privkey.pem
```

conf.diff

```
     server_name _;
 
-    ssl_certificate /etc/nginx/certs/snakeoil.cert.pem;
-    ssl_certificate_key /etc/nginx/certs/snakeoil.key.pem;
+    ssl_certificate /etc/nginx/certs/fullchain.pem;
+    ssl_certificate_key /etc/nginx/certs/privkey.pem;
     ssl_session_timeout 10m;
```

- `$ docker compose up --detach --build --no-deps nginx-proxy`
    - [https://gist.github.com/nishio/917ae036c22c55fc4763d6864898aa5c](https://gist.github.com/nishio/917ae036c22c55fc4763d6864898aa5c)
- In fact, it would be better to get the certificate file from Let's encrypt's certbot, since it seems to update it automatically, but it was too much trouble, so I cp'd it.
    - When a file could not be read due to its location, the owner of the directory or file being root, or permissions, etc., it would simply disconnect from the server instead of stopping with a clear error, and it was a pain to find out what was causing the problem.
    - Finally, just sudo cp'ing the certificate didn't work, chmod 666 did.


After a while, Bad Gateway killed it.
`polis-dev-nginx-proxy-1  | 2023/05/24 04:16:35 [error] 32#32: *12492 connect() failed (111: Connection refused) while connecting to upstream, client: ::ffff:133.200.136.32, server: _, request: "GET /7xrm9snjcc HTTP/2.0", upstream: "http://172.18.0.5:5000/7xrm9snjcc", host: "polis.nhiro.org", referrer: "https://t.co/"`
Hmmm, dead at the end of nginx.
Maybe it's not good if access is concentrated, since the development server is operated in production as it is for the purpose of development observation.
It would be good to see the logs to determine the cause, where is it?

Error in detailed report display
- > GET /report/undefined/api/v3/reports?report_id=r2bafdsneascdm6sbmnad 404
    - `undefined`
- Only the report screen is reading the URL prefix from the .env.
- I'm using document.origin instead when it's not pointed out, but it's undefined



from [/villagepump/2023/05/24](https://scrapbox.io/villagepump/2023/05/24)
<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
- The UI is the same, so it's a mystery to me that I'm not logged in (though of course I should be).
- I was confused because when I clicked on the link for the login lead, I was sent to the main [[Polis]].
- I can't [[link to Twitter]] (haven't set the key?)
    - Maybe I haven't!<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - Opinion posting is allowed anonymously, the seed opinion created by the administrator and the opinion posted by the participants are indistinguishable!
- Background: I wanted to plug Polis for a discussion that occurred within the company.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - pol.is is treated as an "external cloud service", so it is troublesome
        - I think it would be beneficial to the world if it were easier to understand the procedure for getting it up quickly and using it for internal purposes.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
            - Especially since I'm thinking, "Wouldn't this be beneficial for decision making within the private sector?" I think it could be useful for decision making in the private sector.
--
[[polis]]ってログインせずに投票できたんだ<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
- When I vote and leave, I lose my vote results. I don't know what to do.<img src='https://scrapbox.io/api/pages/villagepump/issac/icon' alt='/villagepump/issac.icon' height="19.5"/>
    - There is no Twitter to link to, so I can't even go back through the icons.
        - Only the memory of my vote remains.
    - You can't (and shouldn't) be able to see which of each question you answered when you work together.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
        - No list of votes answered in the past, etc. (I'd like to have one)
        - Understanding that the icon will be yours when the diagram is available, and that you will only receive email notifications when there are additional questions.
        - I want to tinker with various things (my own instance for that).<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>

---
This page is auto-translated from [/nishio/EC2でPolis](https://scrapbox.io/nishio/EC2でPolis) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.