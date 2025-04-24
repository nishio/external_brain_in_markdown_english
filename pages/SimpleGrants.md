---
title: "SimpleGrants"
---

- Tools for [[Quadratic Funding]] in [Fiat
[https://github.com/supermodularxyz/simplegrants](https://github.com/supermodularxyz/simplegrants)




Log of attempts to move it at hand.

See this.
- [[build /tkgshn/Simple Grant locally]].

### See Backend's README
.
> You have to use Node version >= 17.5!
`% node -v`
> v21.2.0


> all you need to do is to change the payment provider in [`provider.service.ts`](./src/provider/provider.service.ts#L15) to the provider you want to use.

ts

```typescript
export class ProviderService {
  constructor(private readonly prisma: PrismaService) {
    this.paymentProvider = new StripeProvider({
      prisma,
      secret: process.env.PAYMENT_KEY,
      country: 'US',
    });
  }
```

You need to set this up to use Stripe, but ignore it for now.


`% npm install`
:

```
npm WARN EBADENGINE Unsupported engine {
npm WARN EBADENGINE   package: 'next-auth@4.18.8',
npm WARN EBADENGINE   required: { node: '^12.19.0 || ^14.15.0 || ^16.13.0 || ^18.12.0' },
npm WARN EBADENGINE   current: { node: 'v21.2.0', npm: '10.2.3' }
npm WARN EBADENGINE }
```

Why do I have to install next-auth with npm to get Docker up and running?
Ignore it for now.


`$ npm run docker:up`
![image](https://gyazo.com/1712cf6178e7bcb3c8015bd663cafb61/thumb/1000)
![image](https://gyazo.com/718e59e326adc25aedcb928a8805dd84/thumb/1000)

The container stood up.


## frontend
`$ npm install -g yarn`
`$ yarn install`
`$ cp .env.example .env.local`
`$ yarn dev -p 3001`

At least I got it up and running.
![image](https://gyazo.com/3c1a537de9e0536dc658aa1ea40b614f/thumb/1000)
What is API key required?
- Find out what to put in `NEXT_PUBLIC_FINGERPRINT_KEY`.
- [The device intelligence platform | Fingerprint](https://fingerprint.com/)
    - Oh, this one.
    - Resolved✅.
    - Why do you put it in, like you don't want multiple accounts created because it's QF?

Somewhere around here, you can delete the clone from the original.
[https://github.com/Naokiakazawa/simplegrants/tree/verification](https://github.com/Naokiakazawa/simplegrants/tree/verification)
(akazawa-san was sitting next to me, so I decided it would be more efficient)

### get sign up to work
.
It's not in the .env sample, but [code [https://github.com/supermodularxyz/simplegrants/blob/main/frontend/pages/api/auth/%5B....](https://github.com/supermodularxyz/simplegrants/blob/main/frontend/pages/api/auth/%5B....) .nextauth%5D.ts], but I'm reading the configuration from `process.env`.
- I decided to set only GOOGLE_CLIENT_ID / GOOGLE_CLIENT_SECRET
- [[OAuth 2.0]]

[Setting up OAuth 2.0 - Google Cloud Platform Console Help](https://support.google.com/cloud/answer/6158849?hl=en)
I set up a mess and put in `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET`, but `'"ikm" must be at least one byte in length'`.
- What needed to be set up and how?
- Ah, `NEXTAUTH_SECRET`.
    - [next.js - "ikm" must be at least one byte in length - Stack Overflow](https://stackoverflow.com/questions/72518497/ikm-must-be-at-least-one-byte-in-length)
- How to get it?
- They say random is good.
    - `$ openssl rand -base64 32`
    - Or this: [https://generate-secret.vercel.app/32](https://generate-secret.vercel.app/32)

### redirect_uri_mismatch
We made it this far.
- ![image](https://gyazo.com/924e55f3366ad5eeaaf2f4a79d1251af/thumb/1000)
- I guess I need to set the redirect url.
- I got a sample.
    - ![image](https://gyazo.com/32e64cd5009613f4139f37260c5e9cc0/thumb/1000)

### frontend also needs to be run on docker
.
There is no mention of that in the README.
- It says to `yarn install` and `yarn dev -p 3001`, so it seems to work normally.
- But in frontend's .env it references DATABASE_CONTAINER (why? What is [[Prisma]] doing?)
.env.local

```
# Prisma ENV
DATABASE_URL="postgresql://${POSTGRES_USER}:${POSTGRES_PASSWORD}@${DATABASE_CONTAINER}:5432/${POSTGRES_USER}?schema=public&connect_timeout=300"
```

- Therefore, access must be passed from the frontend with the container's name.
    - Configure `networks: simplegrants`-like settings in docker-compose.yaml, etc., this is important, maybe
    - This is the reason why I get a toaster with "Network Error" when I start frontend, maybe

docker compose with project root
- `$ docker compose -f docker-compose.dev.yml up --build`

Then initialize DB with root/backend
- `$ cd backend`
- `$ yarn setup`
:

```
All migrations have been successfully applied.
Environment variables loaded from .env
Running seed command `ts-node prisma/seed` ...

An error occurred while running the seed command:
Error: Command failed with ENOENT: ts-node prisma/seed
spawn ts-node ENOENT
```

- I get this error?

### redirect_uri_mismatch continued
.
- Once made the mistake of turning `http://` into `https://`.
- one step further
    - ![image](https://gyazo.com/b19792cb28d5c9e35b3f88dd697b89eb/thumb/1000)

    - Publishing status: In production

### no PostgreSQL user name specified in startup packet
- The login dialog completed without error, but
    - `2024-01-31 02:44:34.623 UTC [93] FATAL:  no PostgreSQL user name specified in startup packet`
    - It's dying trying to write user data...
- cause
    - `$ docker compose -f docker-compose.dev.yml up --build`
    - Here we are using `docker-compose.dev.yml`, so .env.local is read, not .env.production.
    - FIX: POSTGRES_USER/POSTGRES_PASSWORD in .env.production also in .env.local


I was able to do it by starting over from docker compose!
- ![image](https://gyazo.com/3f920c6bf0f66c440a564cfa0fe63fd3/thumb/1000)
    - You don't have the sample data in there, do you?
- I've confirmed that [[Swagger]] comes up on localhost:3000/api.
- What we haven't done yet: [[Stripe]] setup

---
This page is auto-translated from [/nishio/SimpleGrants](https://scrapbox.io/nishio/SimpleGrants) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.