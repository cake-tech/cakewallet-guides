---
title: 'URI scheme'
parent: Glossary
---

# URI scheme

Cake Wallet supports the standard URI schemes for opening up links in the wallets. A URI scheme is a special URL that is meant to convey transaction or wallet restore information. These include links that start with the following:

* `monero`
* `monero-wallet`
* `bitcoin`
* `bitcoin-wallet`
* `litecoin`
* `litecoin-wallet`
* `haven`
* `haven-wallet`
* `cakewallet`
* `monerocom`

## Universal sending format

When sending transactions, the sceme is as follows:

> scheme `(monero / bitcoin / litecoin / haven)` ":" ["//" authority `(empty)`] path `(address)` ["?"  query `(all parameters)`] ["#" fragment `(empty)`]

Examples and descriptions:

*This will open the Send screen for a Monero wallet for 1.64191753 XMR:*

`monero:8Byke9ZxeRQaFe1cVFT5yvMXJ6LorQGgm9BSXGVkCkPqMLYhvdLnymJJytngt6321BBYS5L5W39pzMwFzJjfjTUKSZ3pyk4?tx_amount=1.64191753`

*This will open the Send screen for a Bitcoin wallet for 0.00999496 BTC:*

`bitcoin:bc1q3vuzard8eake3lq8crpegzqu2lk27hxew0zv57?amount=0.00999496`

## Universal wallet restore format

When restoring a wallet, the default sceme created in the app is as follows:

> scheme `(monero-wallet / bitcoin-wallet / litecoin-wallet / haven-wallet)` ":" ["//" authority `(empty)`] path `(address / empty)` ["?"  query `(all parameters)`] ["#" fragment `(empty)`]

*Note: the address is mandatory for the Monero / Haven key restore option, but optional (and thus not provided by default) for seed restores.*

Examples and descriptions:

*This will allow restoring a Monero wallet using a seed and txids*:

`monero-wallet:?seed=iceberg+ascend+soil+goat+yoga+technical+newt+sample+remedy+threaten+arrow+school+negative+sneeze+wiggle+bite+feline+efficient+depth+wife+winter+egotistic+sneeze+taxi+ascend&txid=f8477b831a028f07d5638157afc0fbf0897066b4caa29dc48f885fba79cec814;bd20081e0d1abf05b275bcc06bc7e315bc03c57870e247c82c8a45b30f4d1b34;cdbed9b4b2f56de7cce9255610d0cae702aefb36f9a4ff15698ea448f29f6188`

*This will allow restoring a Monero wallet using keys and a block height:*

`monero-wallet:467iotZU5tvG26k2xdZWkJ7gwATFVhfbuV3yDoWx5jHoPwxEi4f5BuJQwkP6GpCb1sZvUVB7nbSkgEuW8NKrh9KKRRga5qz?spend_key=029c559cd7669f14e91fd835144916009f8697ab5ac5c7f7c06e1ff869c17b0b&view_key=afaf646edbff3d3bcee8efd3383ffe5d20c947040f74e1110b70ca0fbb0ef90d&height=100000`

*This will allow restoring a Litecoin wallet:*

`litecoin-wallet:?seed=rather+maximum+insect+bleak+pride+sand+stomach+anger+brass+sound+lady+section+frame+silent+busy+strategy+tray+science+quantum+cost+inner+appear+sad+resemble`

## App-specific formats

If you want to command that Cake Wallet or Monero.com should open the URI specifically, not another app, then you should use the `cakewallet` and `monerocom` URIs.

### Cake sending format

> scheme `(cakewallet / monerocom)` ":" ["//" authority `(empty)`] path `(monero / bitcoin / litecoin / haven)` ["?"  query `(all parameters)`] ["#" fragment `(empty)`]

Examples and descriptions:

*This will open the Monero.com Send screen for a Monero wallet for 1.64191753 XMR:*

`monerocom:monero?address=8Byke9ZxeRQaFe1cVFT5yvMXJ6LorQGgm9BSXGVkCkPqMLYhvdLnymJJytngt6321BBYS5L5W39pzMwFzJjfjTUKSZ3pyk4&tx_amount=1.64191753`

*This will open the Cake Wallet Send screen for a Bitcoin wallet for 0.00999496 BTC:*

`cakewallet:bitcoin?address=bc1q3vuzard8eake3lq8crpegzqu2lk27hxew0zv57&amount=0.00999496`

### Cake restore format

> scheme `(cakewallet / monerocom)` ":" ["//" authority `(empty)`] path `(monero-wallet / bitcoin-wallet / litecoin-wallet / haven-wallet)` ["?"  query `(all parameters)`] ["#" fragment `(empty)`]

*Note: the address is mandatory for the Monero / Haven key restore option, but optional for seed restores.*

Examples and descriptions:

*This will allow restoring a Monero wallet using a seed and txids in Monero.com*:

`monerocom:monero-wallet?seed=iceberg+ascend+soil+goat+yoga+technical+newt+sample+remedy+threaten+arrow+school+negative+sneeze+wiggle+bite+feline+efficient+depth+wife+winter+egotistic+sneeze+taxi+ascend&txid=f8477b831a028f07d5638157afc0fbf0897066b4caa29dc48f885fba79cec814;bd20081e0d1abf05b275bcc06bc7e315bc03c57870e247c82c8a45b30f4d1b34;cdbed9b4b2f56de7cce9255610d0cae702aefb36f9a4ff15698ea448f29f6188`

*This will allow restoring a Monero wallet using keys and block height in Cake Wallet:*

`cakewallet:monero-wallet?address=467iotZU5tvG26k2xdZWkJ7gwATFVhfbuV3yDoWx5jHoPwxEi4f5BuJQwkP6GpCb1sZvUVB7nbSkgEuW8NKrh9KKRRga5qz&spend_key=029c559cd7669f14e91fd835144916009f8697ab5ac5c7f7c06e1ff869c17b0b&view_key=afaf646edbff3d3bcee8efd3383ffe5d20c947040f74e1110b70ca0fbb0ef90d&height=100000`

*This will allow restoring a Litecoin wallet in Cake Wallet:*

`cakewallet:litecoin-wallet?seed=rather+maximum+insect+bleak+pride+sand+stomach+anger+brass+sound+lady+section+frame+silent+busy+strategy+tray+science+quantum+cost+inner+appear+sad+resemble`
