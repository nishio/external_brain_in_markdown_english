---
title: "Export data from Polis DB"
---

2024-11-07 Reorganization
- Put psql
    - `$ sudo apt install postgresql-client-common`
- Connect
    - `$ psql -h localhost -p 5432 -U postgres`
        - The password is in the env file, by default `POSTGRES_PASSWORD=oiPorg3Nrz0yqDLE`.
- See the list of conversations and the number of votes received.
sql

```
SELECT v.zid, c.topic, COUNT(v.zid) AS total_votes
FROM votes v
JOIN conversations c ON v.zid = c.zid
WHERE v.zid BETWEEN 1 AND 38
GROUP BY v.zid, c.topic
ORDER BY v.zid DESC;
```

    - Look at this and decide which conversation you want to export.
    - Example
sql

```
SELECT v.zid, c.topic, COUNT(v.zid) AS total_votes
FROM votes v
JOIN conversations c ON v.zid = c.zid
WHERE v.zid IN (38, 34, 31, 30, 29, 28,26)
GROUP BY v.zid, c.topic
ORDER BY v.zid DESC;
```

result

```
 zid |         topic          | total_votes 
-----+------------------------+-------------
  38 | Digital Democracy | 4764
  34 | Constitution | 16881
  31 | Energy Policy | 7958
  30 | Economic Policy and High Prices Measures | 28510
  29 | Social Security (Pension and Medical Care) | 18050
  28 | Taxation | 20061
  26 | Political Fund Regulation Reform | 8900
(7 rows)
```

- write out
sql

```
\COPY (SELECT * FROM comments WHERE zid IN (38, 34, 31, 30, 29, 28,26)) TO 'comments.csv' DELIMITER ',' CSV HEADER;
```

sql

```
\COPY (SELECT * FROM votes WHERE zid IN (38, 34, 31, 30, 29, 28,26)) TO '/home/ubuntu/votes.csv' DELIMITER ',' CSV HEADER;
```


-----


pPolis2023-06-04
- Exported data from Polis DB

[/yuiseki/pol.is scraping](https://scrapbox.io/yuiseki/pol.is scraping).
- > I want to get my own past voting data from pol.is and do a lot of things with it.
- > [[Cloudflare]]'s powerful WAF or bot management or whatever is enabled Scraping is super difficult.

We talked about whether we could get the data out if we set up an instance, and I told him that we had done so far as to set it up and collect the votes.
    - [[Polis in EC2]]

[Export  pol-is/polis-documentation · GitHub](https://github.com/pol-is/polis-documentation/blob/master/data/Export.md)
- > Data can be exported from the admin page for a conversation.
    - I don't see that on the menu...
    - I guess that means it's off in pol.is.
- API `https://pol.is/api/v3/dataExport?conversation_id=4jbpxizvxf&format=csv`
    - `{}`.
- I wonder if I should pg_dump it.

:

```
$ psql
Command 'psql' not found, but can be installed with:
$ sudo apt install postgresql-client-common
$ psql
Warning: No existing cluster is suitable as a default target. Please see man pg_wrapper(1) how to specify one.
Error: You must install at least one postgresql-client-<version> package
```


:

```
$ sudo apt update
$ sudo apt install postgresql-client
$ psql
psql: error: connection to server on socket "/var/run/postgresql/.s.PGSQL.5432" failed: No such file or directory
        Is the server running locally and accepting connections on that socket?
```


:

```
$ docker ps
CONTAINER ID   IMAGE                           COMMAND                  CREATED       STATUS                   PORTS                                                                                  NAMES
12be7e86bdf7   compdem/polis-nginx-proxy:dev   "/docker-entrypoint.…"   11 days ago   Up 8 minutes             0.0.0.0:80->80/tcp, :::80->80/tcp, 0.0.0.0:443->443/tcp, :::443->443/tcp               polis-dev-nginx-proxy-1
e605f36eaf7d   compdem/polis-server:dev        "docker-entrypoint.s…"   11 days ago   Up 8 minutes             0.0.0.0:5000->5000/tcp, :::5000->5000/tcp, 0.0.0.0:9229->9229/tcp, :::9229->9229/tcp   polis-dev-server-1
25846362cfd3   compdem/polis-math:dev          "entrypoint ./bin/run"   12 days ago   Up 8 minutes             0.0.0.0:18975->18975/tcp, :::18975->18975/tcp                                          polis-dev-math-1
20b437d2786c   maildev/maildev:1.1.1           "/home/node/bin/mail…"   12 days ago   Up 8 minutes (healthy)   0.0.0.0:1025->1025/tcp, :::1025->1025/tcp, 0.0.0.0:1080->1080/tcp, :::1080->1080/tcp   polis-dev-maildev-1
f8d749409bda   compdem/polis-postgres:dev      "docker-entrypoint.s…"   12 days ago   Up 9 minutes             0.0.0.0:5432->5432/tcp, :::5432->5432/tcp                                              polis-dev-postgres-1
8dccf50c2348   compdem/polis-file-server:dev   "docker-entrypoint.s…"   12 days ago   Up 8 minutes             0.0.0.0:8080->8080/tcp, :::8080->8080/tcp                                              polis-dev-file-server-1
```



:

```
$ psql -h localhost -p 5432
Password for user ubuntu:
```

Find your password
It's in example.env.
example.env

```
###### DATABASE ######
# Optional DB replica for reads:
READ_ONLY_DATABASE_URL=
POSTGRES_DB=polis-dev
POSTGRES_HOST=postgres:5432
POSTGRES_PASSWORD=oiPorg3Nrz0yqDLE
POSTGRES_PORT=5432
POSTGRES_USER=postgres
```


:

```
$ psql -h localhost -p 5432 -U postgres
Password for user postgres: 
psql (14.8 (Ubuntu 14.8-0ubuntu0.22.04.1), server 13.4)
Type "help" for help.

postgres=# 
```


![image](https://gyazo.com/44d6190cf0820fc1f7739ee89aa32e24/thumb/1000)

:

```
\c polis-dev
\dt
```

![image](https://gyazo.com/5e53dd1760fb0812b08bcbc29ef95f33/thumb/1000)

:

```
# select * from comments where zid = 3;
```

![image](https://gyazo.com/eba7fc112842308ec172d49585623f13/thumb/1000)

:

```
polis-dev=# COPY comments TO 'comments.csv' DELIMITER ',' CSV HEADER;
ERROR:  relative path not allowed for COPY to file
polis-dev=# COPY comments TO '/home/ubuntu/comments.csv' DELIMITER ',' CSV HEADER;
ERROR:  could not open file "/home/ubuntu/comments.csv" for writing: No such file or directory
HINT:  COPY TO instructs the PostgreSQL server process to write a file. You may want a client-side facility such as psql's \copy.
```

Oh, right, because it's running inside Docker.

Write out your comments.
:

```
# \COPY comments TO '/home/ubuntu/comments.csv' DELIMITER ',' CSV HEADER;
COPY 55
```


It's done.

Write out comments and votes for a specific conversation id (=3)
:

```
polis-dev=# \COPY (SELECT * FROM comments WHERE zid = 3) TO '/home/ubuntu/comments.csv' DELIMITER ',' CSV HEADER;
COPY 8
polis-dev=# \COPY (SELECT * FROM votes WHERE zid = 3) TO '/home/ubuntu/votes.csv' DELIMITER ',' CSV HEADER;
COPY 454
```


[https://gist.github.com/nishio/897cdad38e9a797917f7b8e5a27c7524](https://gist.github.com/nishio/897cdad38e9a797917f7b8e5a27c7524)

I've never used Postgres before, but with GPT-4 I'm not afraid of anything (see below).
[https://chat.openai.com/share/b1ded3df-9e6c-4742-95cb-10e315e76531](https://chat.openai.com/share/b1ded3df-9e6c-4742-95cb-10e315e76531)

---
This page is auto-translated from [/nishio/PolisのDBからデータをエクスポート](https://scrapbox.io/nishio/PolisのDBからデータをエクスポート) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.