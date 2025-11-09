---
title: "I want to do a miner certification."
---

- [[My Number Authentication]] を現代のモダンな方法で扱うにはどうしたらいい?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
To put it simply, the correct answer now is to "treat [[JPKI]] (the digital certificate of the My Number Card) as a 'normal [[ID provider]]'" with [[OIDC]]. Combine "step by step" with usual login such as [[Passkey]] on the premise of a digital certificate installed in a smart phone.
- The identity infrastructure is OIDC (Auth Code + PKCE)
    - Digital Agency's "Digital Authentication App" operates as an OP (OpenID Provider)

We want to minimize self-implementation.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
If you want to swing to the "minimal on your own," the easiest way is to use [[IdP Broker]] to federate with an external OP (JPKI/MINAR). On the application side, only the standard library is available.
Recommended configuration (in order of ease of operation)
- [[Managed IdP]] ([[Auth0]] / [[Okta]] / [[Azure AD B2C]] / [[Cognito]])
    - Register the Digital Agency's OP (=Miner Certification) as an "External OIDC IdP" there.
    - Passkeys and normal logins are on the Managed IdP side, and redirected to JPKI only when stepping up.

I'm thinking of creating a personal, Vercel, miner-authenticable experimental project, how easy is it to do?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
- Play right away without application → [[PocketSign]] sandbox
    - You can use the sandbox on the same day by simply registering by e-mail. You can experience a simulated JPKI flow without real data, and you can embed it in the SDK/REST.
- Try it out close to production specifications → Digital Agency "Digital Authentication App" Sandbox
    - Official OP (OIDC) is provided, with /authorize /token /userinfo /jwks etc.
    - Endpoint for Sandbox is open (sb-auth-and-sign.go.jp). Flow is Auth Code + PKCE only, token is private_key_jwt authentication.
    - With the test card alternative function, responses can be pseudo-generated and checked all the way through without a card (for users of the authentication API).
    - However, prior application is required (client registration, key submission, etc.). ID token signature is ES256.

> 3.2. Procedures to become a platform operator
>  When introducing services as a PF service provider, you must first obtain technical specifications, etc. from [[J-LIS]], and then proceed with the certification procedures of the competent minister. After obtaining accreditation, it is necessary to prepare a system environment for signature verification, etc.
>  It takes from 6 months to 1 year from obtaining the technical specifications to obtaining certification from the competent minister. For an overview of the entire procedure, please refer to the guidelines published by the Ministry of Internal Affairs and Communications and the Digital Agency below.
[https://www.digital.go.jp/policies/mynumber/private-business/jpki-introduction#guidance3.2](https://www.digital.go.jp/policies/mynumber/private-business/jpki-introduction#guidance3.2)

> 3.3. Public Personal Certification Service Usage Fees
> Only the electronic certificate verification fee to J-LIS is required.
> The fee for using the Public Personal Certification Service is a pay-as-you-go system based on the number of validity checks, and is 20 yen per digital certificate for signatures and 2 yen per digital certificate for user certificates.
> The purpose is to lower the cost of service use for PF service providers and to encourage the introduction of services. For details, please refer to the following.

Very...

---
This page is auto-translated from [/nishio/マイナ認証したい](https://scrapbox.io/nishio/マイナ認証したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.