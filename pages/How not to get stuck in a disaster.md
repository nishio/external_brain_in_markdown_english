---
title: "How not to get stuck in a disaster"
---

["Less Password" Era Account Disaster Prevention Training | blog.jxck.io](https://blog.jxck.io/entries/2025-01-27/account-recovery.html)

[[1Password]] Secret Key can be checked without PC by ticking [[dog tag]].
- Care for cases where PCs are destroyed in a disaster
    - Even if you save it in a secret location that requires a login, you can't see it because you can't log in there.
    - <img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>Yes, that understanding is almost correct.
        - The purpose is to ensure that the Secret Key is visible even in the worst-case scenario of "no trusted devices" due to disaster, loss, device failure, etc.
        - Advantages of engraving on dog tags (metal plates)
            - More fire, water and abrasion resistant than paper. Easier to remain after house damage or submersion in water.
            - No terminal, power supply, or internet required. You can start signing in immediately even with a new device/borrowed PC.
            - Resistant to deterioration even on a decade-by-decade basis.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Is it OK if only the Secret Key is stolen?
    - <img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>1Password cannot be opened with only a Secret Key. The Master Password (Account Password) is also required. The decryption key is derived only when both are combined on the terminal.
        - master password
            - (Account Password) A "knowledge factor" that you remember. It does not remain in plain text on the server or device. It cannot be recovered by 1Password. If you are a family/team, you can request the recovery procedure from the administrator or use the Recovery Code issued in advance.
            - Secret Key Terminal-generated 34 characters, stored only in the Emergency Kit or on the terminal where you signed in. Without it, you will not be able to sign in on a new terminal. Master Password is not enough.

To avoid being locked out of GitHub
- <img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>GitHub is moving forward with the 2FA mandate starting in 2023 and has already expanded its recovery options at the same time.
- Only one [[TOTP]] = [[SPOF]].

Copying and pasting passwords is vulnerable to phishing
- It is important to use a password autofill mechanism and think it is strange when it is not autofilled.
Passkey
WebAuthn
- Passkey account (new option after 2024)


Apple putting private keys into iCloud
- Transition will be easier and less jammed.
- Discussion of whether or not private keys should be taken out of the device.
    - More phishing damage by copying and pasting strings than there strictness

---
This page is auto-translated from [/nishio/災害時に詰まない方法](https://scrapbox.io/nishio/災害時に詰まない方法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.