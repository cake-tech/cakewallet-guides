---
title: "Tor with Orbot"
parent: Advanced Features
---

# Tor with Orbot

It's possible to use Cake Wallet with [Tor](https://www.torproject.org/) using [Orbot](https://guardianproject.info/apps/org.torproject.android/)! This works for both iOS and Android.

## Performance

Tor is noticeably slower than clearnet, so some operations will take a super long while.

### Fast enough

* Sending transactions. Expect it to take up to 60 seconds, but it should normally take 30 seconds.
* Syncing Bitcoin and Litecoin wallets.
* Fiat price API lookups. This should be less than 5 seconds.
* Cake Pay. Loading various functions should take less than 15 seconds.
* Staying up to date with an already synced Monero wallet.

### Not recommended

* Syncing more than 100 Monero blocks. Syncing over Tor is extremely slow, and could take several days or even weeks. It's much more realistic to create a clearnet connection to your own Monero node, sync using that, and then re-connect over Tor after your wallet is fully synced.

### Not available

Some third-party services may not be available if you are using Tor. These may include:

* Exchange (some providers)
* Buy
* Sell

## Requirements

* [Cake Wallet](https://cakewallet.com) or [Monero.com](https://monero.com) app
* Orbot
    * F-Droid: [https://guardianproject.info/fdroid/](https://guardianproject.info/fdroid/)
    * Google Play: [https://play.google.com/store/apps/details?id=org.torproject.android](https://play.google.com/store/apps/details?id=org.torproject.android&referrer=utm_source%3Dguides.cakewallet.com%26utm_medium%3Dwebsite)
    * App Store: [https://apps.apple.com/us/app/orbot/id1609461599](https://apps.apple.com/us/app/orbot/id1609461599)

## Setting up Orbot

First, set up Orbot. We recommend using VPN mode for the entire device (it will say `Full Device VPN`), but you can optionally configure Cake Wallet as the only Tor-Enabled App. Make sure to use VPN mode.

Click start and wait a few seconds for it to connect. If you are unable to connect to Tor because your network is blocking access, you will need to enable bridges. You can use choose to connect through community servers or use snowflake.

## Switch back to Cake Wallet

Now, connections over Cake Wallet should use Tor with Orbot.

### Connect to an onion node

You can use Tor to connect to either clearnet or onion nodes, but we recommend connecting to an onion node. If an onion node is selected, you will not accidentally sync or send transactions if Orbot is not configured properly, since you cannot make a clearnet connection to an onion address.

To add an onion node, simply [add a custom node](/docs/advanced-features/custom-node) that is an onion node. It will end in `.onion`.

Our official onion node is:

* Node Address: `cakexmrl7bonq7ovjka5kuwuyd3f7qnkz6z6s6dmsy3uckwra7bvggyd.onion`
* Node port: `18081`
* Login: (blank)
* Password: (blank)
* Use SSL: (unticked)

Please note that running your own node over clearnet is usually better (for *both* performance and privacy) than connecting to someone else's onion node. We recommend you run your own onion node!

## Note on DNS

We recommend manually setting a DNS provider that you trust in your Android / iOS operating system settings, especially if you only occasionally use Tor.
