---
title: "Bitcoin"
parent: Cryptos
---

# Bitcoin

{: .friendly}
Official Website: [bitcoin.org](https://bitcoin.org/){:target="_blank"}

## Addresses

We automatically generate new Bitcoin addresses after each use for better privacy. Previous addresses continue to work.

We use the same derivation scheme as Electrum: `m/0/x` for receive addresses, and `m/1/x` for change addresses.

There are multiple address types supported.

* Segwit (P2WPKH)
* Taproot (P2TR)
* Segwit (P2WSH)
* Segwit-Compatible (P2SH)
* Legacy (P2PKH)

You can switch to a different address type by going to the `Receive` screen and clicking on the current address type at the top of the screen.

[![Click current address type](./seed.png){:width="32%"}](./seed.png)
[![Choose address type](./seed2.png){:width="32%"}](./seed2.png)

## Seed format

Bitcoin wallets only currently support being created using the Electrum seed format. We support restoring seeds generated in the Electrum and BIP-39 seed format.

BIP-39 restoring will check for multiple derivation paths, and ask you which one you would like to use if transactions are detected on multiple paths.

## Bitcoin fee levels

We recommend leaving your Cake Wallet fee for Bitcoin as `Medium`.

| Cake Wallet name | estimatefee value | Description |
| --- | --- | --- |
| Slow ~24hrs | 100 | Save on fees if you can wait a full day for the transaction to be confirmed. |
| Medium | 5 | The best blend of speed and cost. You'll usually get a confirmation within 3 blocks. |
| Fast | 1 | Aggressively pursues inclusion in the next block, usually overpaying. |

## RBF (Replace-By-Fee)

As of Cake Wallet version `4.15.4`, the Bitcoin wallet supports using RBF (Replace-by-fee), and is enabled by default for every transaction.

RBF allows you to modify the fee after you have already sent a transaction. You can do this by going to the `Transactions` screen, clicking on the desired transaction, the clicking `Bump fee`. Once you are in the `Bump fee` page, you can set your fee and click `Send`.

[![Click "Bump fee"](./rbf.png){:width="32%"}](./rbf.png)
[![Modify fee](./rbf2.png){:width="32%"}](./rbf2.png)

