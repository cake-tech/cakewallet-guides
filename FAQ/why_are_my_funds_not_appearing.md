---
title: "Why are my funds not appearing?"
parent: FAQ
---

# Why are my funds not appearing?  

Your wallet must be fully synchronized before it displays the correct balance. You should see a `SYNCHRONIZED` label in the rounded bar at the top of your screen.

[![Synchronized](/images/funds-1.jpg)](/images/funds-1.jpg)

If you see "XXXX blocks remaining" this means that your wallet is still synchronizing. Please wait until it is fully synchronized. If your wallet already displays `SYNCHRONIZED`, you can try [rescanning](/docs/advanced-features/rescan-wallet/) by opening the menu at the top-right, tapping `Rescan`, and setting a date from about a week before the wallet's first transaction.

{: .warning}
[Rescanning](/docs/advanced-features/rescan-wallet/) will remove any saved transaction keys and destination addresses, which may be useful for proving payments.

[![Syncing](/images/funds-2.jpg)](/images/funds-2.jpg)

If the wallet says `SYNCHRONIZED` at the top and you don't see your transactions, first try force closing and re-opening your wallet, which forces a rescan.

### I did not receive funds from an exchange  

If you created an exchange using the built-in exchange within the Cake Wallet app and are not seeing your expected balance, go to the Trade Details screen and check the status of the exchange. If your status is `Waiting` or `Fetching`, this means that your trade is processing. Please wait a few more minutes.

If the status is `Finished`, and your wallet is synchronized but you do not see an incoming transaction, please contact our support team at [support@cakewallet.com](mailto:support@cakewallet.com).

### I did not receive funds from another wallet

If you see an incoming transaction and your `Available Balance` and `Full Balance` differ, please wait for up to ~20 minutes while your transaction is confirmed on the Monero blockchain or 3 confirmations on the Bitcoin blockchain. If your wallet is synchronized, and the incoming transaction is not displaying, please contact our support team at [support@cakewallet.com](mailto:support@cakewallet.com).

### How can I speed up Monero syncing?

Follow [this tutorial on how to sync a Monero wallet faster](https://guides.monero.com/docs/tutorials/sync-faster/).
