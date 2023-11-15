---
title: "Authentication and 2FA"
parent: Advanced features
---

# Authentication and 2FA

Cake Wallet supports optional biometric authentication on supported devices. You can enable this in settings.

## Cake 2FA

{: .warning}
Read this entire section carefully to understand the benefits and risks of the Cake 2FA feature. Cake 2FA is a **nontraditional TOTP implementation**, since there are no Cake Wallet servers to verify your app authentication attempts.

{: .friendly}
For a basic introduction and setup tutorial for Cake 2FA, watch our [video tutorial here](https://www.youtube.com/watch?v=21ZhWCwvfxw)

In security settings, you can optionally enable Cake 2FA. **Cake 2FA serves as a secondary line of defense for your wallets, but it is a defense that is ONLY useful for casual cases. It will NOT protect your wallet from sophisticated attackers.**

When enabled, Cake 2FA requires a user to provide a [TOTP](https://wikipedia.org/wiki/Time-based_one-time_password) 8-digit code after successfully authenticating with their PIN or biometrics, every time that an authentication challenge is triggered.

Cake 2FA protects against these kinds of attacks:

* You are sleeping, and a friend uses your fingerprint to get into your phone and wallet. They would not have a TOTP code.
* Your phone is unlocked as you are using it, and a thief takes it. They could try to guess your PIN, but it would be a lot harder for them to bypass the TOTP code.

**Cake 2FA does NOT protect against these kinds of attacks, to a sufficient degree:**

* Your phone is taken by a sophisticated attacker or nation-state who can write custom software to interact with your wallet files. They may be able to find weaknesses in the implementation to brute force the TOTP attempts.
* Your wallet mnemonic seed is stolen. The seed is enough to restore the wallet on its own.

**You should assume that Cake 2FA provides some defense against basic attacks, but NO defense against sophisticated attackers. Your best defense against sophisticated attackers is an encrypted device.**

{: .warning}
If you lose both your mnemonic seed and your TOTP code, then you will lose access to your funds! Always have a secure backup of your seed phrases!

## Brute force mitigations and remaining risks

In a typical TOTP implementation, a server maintains a user account that is protected with TOTP (and usually other options, like a password). In this case, the server will track login attempts, and if there are repeated TOTP failures, they should lock the account.

In Cake Wallet, there are no servers that can serve this purpose. Thus, brute force prevention is extremely difficult, and there is no way to guarantee that the wallet app will be able to fully protect against brute force attempts.

A casual attacker who is interacting with the unmodified Cake Wallet user interface will be unable to make enough guesses to reliably bypass the TOTP code. The Cake Wallet UI will restrict further authentication attempts for three minutes if there are three consecutive TOTP failures. Thus, for a 50% chance of success, a casual attacker will need to continuously type in codes this way for [over 200 years](https://security.stackexchange.com/questions/185905/maximum-tries-for-2fa-code/185917#185917).

However, sophisticated attackers won't necessarily be limited by this UI. A sophisticated attacker (depending on the security of the device or operating system) could potentially take the Cake Wallet files, export them, and then interact with them using custom software that bypasses these rate limits. If an attacker was able to fully bypass these limits, then the time to brute-force the TOTP code could be only [a matter of hours](https://security.stackexchange.com/questions/185905/maximum-tries-for-2fa-code/185917#185917).

Cake Wallet developers have taken steps to make these tasks as challenging as possible, but we cannot account for every single case.

## Why offer Cake 2FA with these limitations?

Cake 2FA isn't perfect, and it isn't as strong as traditional TOTP applications. Some people will ask: why implement it then?

The answer is that Cake Wallet users have a huge number of threat models. In our opinion, Cake 2FA substantially reduces the risks for most people's threat models.

When Cake 2FA is enabled, it requires thieves to have a sophisticated technical understanding to be able to sensitively extract data from your device and to then manipulate that data with custom software.

As TOTP becomes more and more common, we feel that it is important to provide users with a security option that closely meets the user experience that they are already familiar with. And despite its limitations, this TOTP implementation is more secure than a user-set PIN of `123456` (or any other 6-digit PIN).

## Enabling Cake 2FA

{: .note}
Cake 2FA's TOTP implementation requires a [compatible authenticator](/docs/advanced-features/authentication/#what-totp-applications-do-you-recommend)  with support for [SHA-512](/docs/advanced-features/authentication/#why-are-you-using-sha512-my-app-doesnt-support-sha512).

To set up Cake 2FA, click on the upper right hamburger menu, then `Security and backup`, then `Set up Cake 2FA`.

You will see a series of warnings. After understanding the limitations, click `Set up TOTP`.

You will be presented with a QR code, a TOTP Secret Code, and a TOTP Auth URI. We recommend scanning the QR code with an open-source TOTP application on another device, but you can click to copy the code or URI as well. When added to your desired TOTP app, click `Continue`.

You will be prompted to provide the 8-digit TOTP code. Type in the current code, then click `Continue`.

If correct, you will be presented with a success message. A TOTP code will now be required in addition to your PIN, password, or biometrics every time there is an authentication challenge.

## Cake 2FA presets and access control settings

After enabling Cake 2FA, you will be presented with presets and access control settings. You can edit these later by clicking on `Security and backup`, then `Modify Cake 2FA`.

There are three access control presets available:

* **Narrow**. Allows opening the wallet and sending/exchanging to your own Cake Wallet addresses and addresses saved in the Address Book without needing a TOTP code. A TOTP code is required to create a new wallet or to add a contact.
* **Normal** (default). Requires a TOTP code for the most sensitive actions, but not for opening the wallet.
* **Aggressive**. Requires a TOTP code to access the wallet.

We recommend using one of these presets; however, you can manually enable or disable individual access control settings as you wish.

## Disabling Cake 2FA

Click on the upper right hamburger menu, then `Security and backup`, then `Modify Cake 2FA`.

You will be prompted for authentication, including a TOTP code. Then, you will be shown an option to disable Cake 2FA. If you wish to generate a new TOTP code, then disable Cake 2FA, and then enable it again after to generate a new code with a new setup process.

## Is Cake 2FA a replacement for a hardware wallet?

No, Cake 2FA is not a replacement for a hardware wallet. Well-designed hardware wallets will provide better protection against sophisticated attackers.

## Is Cake 2FA a replacement for a multisig wallet?

No, Cake 2FA is not a replacement for a multisig wallet. Well-designed multisig wallet implementations will provide much better protection against sophisticated attackers. The Cake 2FA process is independent from any wallet signing process.

## Does this work with FIDO2 and my Yubikey?

FIDO2 requires a server to communicate with. When you open Cake Wallet, you don't talk to our (or anyone's) servers. Thus, FIDO2 doesn't really make sense for this application. Unless you want Cake to have a record of each time you access your wallet (we don't have, and we don't want, this info), we can't get around this.

If you want to use your Yubikey, you can pair your Yubikey with [Yubico Authenticator](https://www.yubico.com/products/yubico-authenticator/). This app requires you to have your Yubikey to display TOTP codes in the app.

## What TOTP applications do you recommend?

We recommend the following: [Yubico Authenticator](https://www.yubico.com/products/yubico-authenticator/) (requires Yubikey), [Bitwarden](https://bitwarden.com/pricing/) (requires premium account), [KeePassXC](https://keepassxc.org/) (free and open-source), [1Password](https://1password.com/) (paid and closed-source), [Ente Auth](https://github.com/ente-io/auth) (free and open-source) and [Aegis](https://getaegis.app/) (free and open-source). Many common TOTP applications such as Google Authenticator, Microsoft Authenticator, and Authy are incompatible with Cake 2FA.

## Why are you using SHA512? My app doesn't support SHA512.

SHA1 is the most common implementation of TOTP, but SHA512 is safer, particularly for this nontraditional implementation. Thus, we have decided to choose the safer algorithm. This has the downside of not working with some common TOTP applications, such as Google Authenticator and Microsoft Authenticator.

## Why are you using a 30 second code timeout period?

Using a time other than the default 30 seconds will lead to user experience issues. Users are more likely to come across blocked legitimate authentication attempts, and many TOTP user applications [do not support](https://wikipedia.org/wiki/Comparison_of_OTP_applications) a timeout period other than 30 seconds. Further, shorter timeout periods do not increase security for this application.

## Why are you using an 8-digit code? My app doesn't support 8-digit codes.

6-digit codes are the most common implementation of TOTP, but 8-digit codes are safer, particularly for this nontraditional implementation. 8-digit codes are 100 times as difficult to brute-force than 6-digit codes. Thus, we have decided to choose the safer digit length. This has the downside of not working with some common TOTP applications, such as Google Authenticator and Microsoft Authenticator.

## Will you support HOTP?

We have not yet determined if we want to support HOTP or not.
