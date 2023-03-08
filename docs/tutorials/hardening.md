---
title: "Hardening your Cake Wallet mobile installation"
parent: Tutorials
---

# Hardening your Cake Wallet mobile installation

Cake Wallet includes many strong protections by default, but there are some steps you can take to further improve your privacy and security.

## Factory reset your phone and consider a custom operating system

In the best case, you should use a **dedicated, modern phone** that is still receiving software updates. **Factory reset** the phone and only use it as your Cake Wallet phone. Don't use a work phone. Leave the phone off if you aren't using it, so that the encryption is enforced.

Some people prefer using an operating system such as [CalyxOS](https://calyxos.org/) or [GrapheneOS](https://grapheneos.org/) for Android. Typically, first-party phone providers such as Google and Apple provide faster security updates, at the expense of weaker privacy protections by default.

If you are overwhelmed, start with a modern, factory reset phone from Apple or Google that is still getting software updates. Don't let perfection get in the way of at least starting there.

Avoid using a SIM if you can. Otherwise, get a SIM from [Silent Link](https://silent.link/), [Mint Mobile](https://www.mintmobile.com/) (prepaid credit picked up in store), or [Twilio](https://www.twilio.com/en-us/iot/super-sim-card) (advanced and out of scope for this guide).

## Configure phone security settings

You may want to turn off facial and fingerprint phone login. Select a strong login password.

Make sure device encryption is enabled. This is enabled by default on most devices now.

The University of Texas at Austin has good phone hardening guides:

* [Google Android](https://security.utexas.edu/handheld-hardening-checklists/android)
* [Apple iOS](https://security.utexas.edu/handheld-hardening-checklists/ios)

### Custom DNS provider

You may want to change your DNS provider in your phone to one you trust. Common privacy-friendly DNS providers are [IVPN](https://www.ivpn.net/knowledgebase/troubleshooting/what-is-the-ip-address-of-your-dns-servers/) and [1.1.1.1](https://1.1.1.1/) (Cloudflare).

## Install applications

You generally will want a few apps:

* **[Cake Wallet](https://cakewallet.com) and/or [Monero.com](https://monero.com)**. Obviously :)
* **[Orbot](https://guardianproject.info/apps/org.torproject.android/)**. This is your mobile gateway to Tor.
* **VPN**. You may wish to use a VPN. Choose one recommended by [Privacy Guides](https://www.privacyguides.org/en/vpn/). Pay with XMR. VPNs have [limitations](https://www.consumerreports.org/vpn-services/vpn-testing-poor-privacy-security-hyperbolic-claims-a1103787639/).

You can install apps from your phone's respective app store or from their APKs.

## You should run your own node(s)

For best privacy, you really should run your own Monero, Bitcoin, etc. nodes.

We have a guide for running your own Monero node [here](/docs/tutorials/monero-node).

## Using Cake Wallet for the first time

1. Open Cake Wallet or Monero.com
2. On wallet setup, click "Advanced Privacy Settings"
3. Change the Fiat API and Exchange settings from "Enabled" to "Tor only" (recommended) or "Disabled"
4. Add a custom node
    * We recommend adding your **own** node here.
    * Alternatively, use our Monero onion node:
        * Node Address: `cakexmrl7bonq7ovjka5kuwuyd3f7qnkz6z6s6dmsy3uckwra7bvggyd.onion`
        * Node port: `18081`
        * Login: (blank)
        * Password: (blank)
        * Use SSL: (unticked)

If you are running your own node, you can connect to it without needing Tor, which allows for significantly faster syncing.

We recommend using your own **clearnet** node in most cases. This way, you can turn off Orbot, sync the Monero blockchain quickly, then turn Orbot on after it is synced and you are ready to send or exchange your Monero. Learn more about [using Tor with Cake Wallet](/docs/advanced-features/tor-with-orbot).

You can change these settings later in "Privacy settings" and "Connection and sync".

## Syncing

For Monero, we recommend syncing to your own node over **clearnet** for practical purposes. Disable Tor with Orbot for syncing. If you must use a different node, you can sync entirely over Tor, but it will take a *long* time for more than a few days of blocks (hours / days).

## Sending

We recommend sending through your own node. This can be done over clearnet or Tor. If you use someone else's node, we recommend using Tor.

It's convenient to have spot fiat pricing data, so we recommend turning on Orbot after your wallet is synced and using the "Tor only" fiat API setting. Sending transactions over Tor is slower than clearnet, but it's not unbearably slow.

## Exchanging

We recommend exchanging using the "Tor only" setting. Exchanging over Tor has reasonably good performance. After your wallet shows as "Synchronized" at the top of the home page, enable Tor with Orbot.
