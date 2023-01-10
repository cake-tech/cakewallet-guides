---
title: "Why did I get this error?"
parent: Bugs and service status
---

# Why did I get this error?  

### Exception: not enough money to transfer, available only XXXXXX, sent amount XXXXX.

This error means that your Available balance is locked.  After the Monero blockchain confirmed your change, you will be able to send the rest of your XMR.  

[![Not enough money](/images/error1.jpg)](/images/error1.jpg)

### Error: the wallet is not synced  

This error means that your wallet is synchronizing. Please leave the wallet open and wait until it has synchronized. If you are having trouble with sync speed, you may need to connect to a WiFi network, rather than using data. If the sync state is stuck on a specific amount of blocks remaining for an extended period of time, open the menu in the top-right, tap "Nodes", and select a node with a green dot to the right of it.

[![Wallet not synced](/images/error2.jpg)](/images/error2.jpg)

### New Wallet Exception: Format exception: Unexpected extension byte   

You may have gotten this error while restoring a wallet. Please make sure that you input the entire seed/recovery phrase (25 for XMR, 12 for Bitcoin (Electrum)).

[![Unexpected extension byte](/images/error3.jpg)](/images/error3.jpg)

### Trade not created error: None of the provided exchanges can make this exchange

This error is shown when the wallet is unable to successfully initiate an exchange across any of the supported (and selected) exchange providers.

This could be because of any/all of the following:

1. The only exchange(s) that offer this pair have taken this pair down for maintenance. It should be back up later.
2. The only exchange(s) that offer this pair do not offer it in your region/country.
3. You have manually deselected the only exchanges that offer this pair.
4. An exchange is announcing the best rate, but that exchange is unable to offer that pair when attempting to proceed.
5. No exchanges offer this specific pair. This is unlikely except for extremely uncommon pairs.

We recommend going one-by-one through all the exchanges to see if that solves the issue. If you notice that an exchange advertises rates that it does not actually offer, please contact Cake Wallet support to let us know! This is a known issue for ZZEC pairs in Cake Wallet version 4.4.6 and Monero.com version 1.1.0; you must manually enable ShapeShift only for these trades. We plan to address this ASAP.

### Error: Exception for Cake Pay

You may see a generic "Error: Exception" message when using XMR for Cake Pay, if you make a second Cake Pay purchase within a few moments after completing another Cake Pay purchase. Please wait for the previous Monero transaction to appear in your transactions list, and then try again. If the error persists, please make a screen recording and send it to our support staff.

### Error: Load failed

You may see a "Load failed" error when using Onramper. This is a general error for connection issues with Onramper. Please try another connection (such as not using a VPN), and try again later. If the issue persists, please email Cake Wallet support with as many details about your connection as possible.

### Error: transaction <> was rejected by daemon with status <error>

This is a rare Monero wallet-daemon communication error. Please first try using a different node and restarting the app.

You may see this error while using a Monero view-only wallet. If this is the case, then you are getting this error because you cannot properly construct an outgoing transaction without a private spend key.

If the issue persists for a wallet that has the private spend key (if it is NOT a view-only wallet), please contact Cake Wallet support with as much information as you have. They will guide you through [rescanning your wallet](/docs/advanced-features/rescan-wallet) and [restoring from seed](/docs/basic-features/restore-wallet-from-keys-or-seed).
