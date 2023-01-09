---
title: "Monero"
---

# Monero

## Syncing

**The most common issue with Monero is an unsynchronized wallet.**

To perform most interactions with your wallet, your wallet must be fully synchronized. There will be a green dot at the top of your home screen.

If you are stuck on the same block while syncing for a while, or it says disconnected, you should [try another node](/docs/advanced-features/custom-node) or another internet connection.

If your wallet is not fully synced, your wallet balance may be incorrect, and you won't be able to send transactions. You will need to wait until your wallet is fully synced before proceeding. Keep the app open with the screen on to keep syncing.

## Accounts and subaddresses

[![Monero addresses](/assets/images/monero-addresses.png)](/assets/images/monero-addresses.png)

### Monero subaddresses

A Monero subaddress is a unique, unlinkable address that can be generated on-demand. Coins sent to it will still arrive in your main wallet, but the person sending the coins cannot determine your wallet's main address. To create a new subaddress, tap on `Accounts and subaddresses`, then tap on `Addresses` and create a name for this address, then tap `Create`. Subaddresses always start with `8`. Your main address starts with `4`.

[![New address](/assets/images/receive-4.jpg){:width="32%"}](/assets/images/receive-4.jpg)
[![New address name](/assets/images/receive-5.jpg){:width="32%"}](/assets/images/receive-5.jpg)
[![Copy address](/assets/images/receive-6.jpg){:width="32%"}](/assets/images/receive-6.jpg)

### Monero accounts

Each Monero wallet can have several accounts. We recommend this feature for advanced users only. Within your Monero wallet, click `Receive`, then click `Accounts and subaddresses`. Click on `Accounts` to change between your different accounts. You can have unlimited accounts, and each account can have unlimited subaddresses. The first indexed address of each account (besides the main account) starts with an `8`.

Balances and transactions for each Monero account are shown separately. While in one account, you can't see the balance and transactions of another account. You need to switch between accounts to see the balances and transactions of each.

## View-only wallet

It's possible to create a Monero view-only wallet. You need the following information:

* Main Monero address (`4...`)
* Private view key
* Restore height (recommended, not required)

 Restore from keys following [these steps](/docs/basic-features/restore-wallet-from-keys-or-seed/). Leave the `Spend key (private)` field blank. Let the blockchain sync fully. After syncing, you should see all incoming transactions (*including* incoming change). View-only wallets usually do not show an accurate balance (they cannot be relied upon for this purpose), and they will not show some types of outgoing transactions.

## Monero fee levels

Cake Wallet follows the standard wallet2 fee levels. We recommend leaving your Cake Wallet fee for Monero as `Automatic`.

| Cake Wallet name | wallet2 priority value | CLI name | GUI Name | Multiplier |
| --- | --- | --- | --- | --- |
| Automatic | 0 | default | Automatic | x1 or x5, depending on network activity |
| Slow | 1 | unimportant | Slow | x1 |
| Medium | 2 | normal | Normal | x5 |
| Fast | 3 | elevated | Fast | x25 |
| Fastest | 4 | priority | Fastest | x1000 |

## Monero save recipient addresses

Monero addresses (unlike Bitcoin) are never stored on the blockchain. When you send Monero to a recipient, the address that you send to is only recorded locally, not on the blockchain. Thus, if you restore a Monero wallet from mnemonic seed or from keys, you will not see the Monero addresses that you sent funds to.

Additionally, Cake Wallet can be configured to discard the Monero recipient address. In settings, untick `Save recipient address`. If you send XMR while this option is disabled, then addresses are no longer retained. The record of which address(es) you send to are lost forever.

Disabling this feature is only recommended for advanced users who know what they're doing. Please leave it enabled if you are unsure.
