---
title: "Hardening your Cake Wallet mobile installation"
parent: Tutorials
---

# Hardening your Cake Wallet mobile installation

Cake Wallet includes many strong protections by default, but there are some steps you can take to further improve your privacy and security.

## Factory reset your phone and consider a custom operating system

In the best case, you should use a **dedicated, modern phone** that is still receiving software updates. **Factory reset** the phone and only use it as your Cake Wallet phone. Don't use a work phone. Leave the phone off if you aren't using it, so that the encryption is enforced.

Some people prefer using an operating system such as [CalyxOS](https://calyxos.org/) or [GrapheneOS](https://grapheneos.org/) for Android. Typically, first-party phone providers such as Google and Apple provide faster security updates, at the expense of weaker privacy protections by default. If going with a custom ROM, we recommend ROMs that maintain security features like maintaining [verified boot.](https://source.android.com/docs/security/features/verifiedboot)

If you are overwhelmed, start with a modern, factory reset phone from Apple or Google that is still getting software updates. Don't let perfection get in the way of at least starting there.

Avoid using a SIM if you can. Otherwise, get a SIM from [Silent Link](https://silent.link/), [Mint Mobile](https://www.mintmobile.com/) (prepaid card picked up in store), or [Twilio](https://www.twilio.com/en-us/iot/super-sim-card) (advanced and out of scope for this guide).

## Configure phone security settings

You may want to turn off facial and fingerprint phone login. Select a strong login password.

Make sure device encryption is enabled. This is enabled by default on most devices now.

The University of Texas at Austin has good phone hardening guides:

* [Google Android](https://security.utexas.edu/handheld-hardening-checklists/android)
* [Apple iOS](https://security.utexas.edu/handheld-hardening-checklists/ios)

On Android, it is recommended to perform the following additional steps after enabling a IVPN, Orbot, Invizible Pro, etc.

1. Open Android Settings
2. Search for `VPN` and open the `VPN` or `More connections` setting from the search results.
3. Either tap the gear next to the in-use VPN, or tap and hold > edit it
4. Enable the toggles for `Always-on VPN` and `Only allow connections through this VPN`

### Custom DNS provider

You may want to change your DNS provider in your phone to one you trust. Common privacy-friendly DNS providers are [IVPN](https://www.ivpn.net/knowledgebase/troubleshooting/what-is-the-ip-address-of-your-dns-servers/) and [1.1.1.1](https://1.1.1.1/) (Cloudflare), or using InviZible Pro (more on that later).

## Install applications

You generally will want a few apps:

* **[Cake Wallet](https://cakewallet.com) and/or [Monero.com](https://monero.com)**. Obviously :)
* **[Orbot](https://guardianproject.info/apps/org.torproject.android/)**. This is your mobile gateway to Tor.
* **[InviZible Pro](https://invizible.net)** (Android only). This is an alternative to Orbot that will automatically handle Tor/onion connections and clearnet connections simultaneously.
* **VPN**. You may wish to use a VPN. Choose one recommended by [Privacy Guides](https://www.privacyguides.org/en/vpn/). Pay with XMR. VPNs have [limitations](https://www.consumerreports.org/vpn-services/vpn-testing-poor-privacy-security-hyperbolic-claims-a1103787639/).

You can install apps from your phone's respective app store or from their APKs.

## Keeping Cake Wallet and other applications updated

We recommending finding a workflow, either through automatic or manual updates, to ensure you're receiving the latest security updates for applications. If a vulnerability is ever patched, you want to receive it as quickly as possible. Additionally, it's not uncommon for applications like Cake Wallet to introduce new security features you can benefit from.

Some users prefer automatic updates to receive the newest updates automatically, and some users prefer manual updates to verify new software. Regardless of your preference, make sure you're finding a workflow that works for you.

* [To enable/disable iOS Automatic Updates](https://support.apple.com/en-us/102629)
* [To enable/disable Android Automatic Updates](https://support.google.com/googleplay/answer/113412)
* [Many users enjoy Obtainium as a way to fetch updates regardless of source](https://github.com/ImranR98/Obtainium)

## You should run your own node(s)

For best privacy, you really should run your own Monero, Bitcoin, etc. nodes.

We have a guide for running your own Monero node [here](https://guides.monero.com/docs/tutorials/monero-node).

## Using Cake Wallet for the first time

1. Open Cake Wallet or Monero.com
2. On wallet setup, click "Advanced Privacy Settings"
3. Change the Fiat API and Exchange settings from "Enabled" to "Tor only" (recommended) or "Disabled"
4. Add a custom node
    * We recommend adding **your own clearnet** node here.
    * Alternatively, use our Monero onion node:
        * Node Address: `cakexmrl7bonq7ovjka5kuwuyd3f7qnkz6z6s6dmsy3uckwra7bvggyd.onion`
        * Node port: `18081`
        * Login: (blank)
        * Password: (blank)
        * Use SSL: (unticked)
5. We recommend enabling [Cake 2FA](/docs/advanced-features/authentication#cake-2fa).

If you are running your own node, you can connect to it without needing Tor, which allows for significantly faster syncing.

We recommend using **your own clearnet** node in most cases for best performance. Learn more about [using Tor with Cake Wallet](/docs/advanced-features/tor-with-orbot).

You can change these settings later in "Privacy settings" and "Connection and sync".

## Using Orbot

You will need to use Orbot in full device VPN mode. You will want to toggle off Tor while syncing, but enable it for sending transactions.

### Syncing

For Monero, we recommend syncing to **your own clearnet** node for practical purposes. Disable Tor with Orbot for syncing. If you must use a different node, you can sync entirely over Tor, but it will take a *long* time for more than a few days of blocks (hours / days).

If you are using iOS, we recommend force closing Cake Wallet before switching to enable/disable Orbot to reduce the chance of [iOS VPN leaks](https://protonvpn.com/blog/apple-ios-vulnerability-disclosure/).

### Sending

We recommend sending through your own node. This can be done over clearnet or Tor. If you use someone else's node, we recommend using Tor.

It's convenient to have fiat spot pricing data, so we recommend turning on Orbot after your wallet is synced and using the "Tor only" fiat API setting. Sending transactions over Tor is slower than clearnet, but it's not unbearably slow.

### Exchanging

We recommend exchanging using the "Tor only" setting. Exchanging over Tor has reasonably good performance. After your wallet shows as "SYNCHRONIZED" at the top of the home page, enable Tor with Orbot.

## Using InviZible Pro

Use InviZible Pro for simultaneous encrypted DNS for clearnet + Tor for .onion connections.

1. Install and run InviZible Pro
2. Enable the toggles on Invizible's homescreen for `Hide IP with Tor` and `Protect DNS with DNSCRYPT` and tap `Start`.
3. Open the Menu and select `Fast Settings`
4. Turn on `Start on boot` toggles for DNSCrypt and Tor
5. Turn off `Route all traffic through Tor`. If you leave this on, then all traffic will go through Tor and wallet syncing will be very slow.
6. (Optional) Use the `Select DNSCrypt servers` setting (located just above the setting from #5) to change the preselected DNS server(s) to those of your choosing.

Configuring Cake Wallet for use with Invizible

1. Open "Menu > Connection and Sync"
2. Add and select a Trusted Clearnet Node (recommended that you use your own node, or one where you personally know and trust the operator)
3. Open "Menu > Privacy Settings" and ensure Tor only is selected for Fiat-api and Exchange

This will send Tor/onion requests for exchange rates and exchanges APIs through Tor, while allowing clearnet connections for communicating with your own node.

We do not recommend sending transactions over the clearnet to someone else’s node.
