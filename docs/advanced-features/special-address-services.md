---
title: "Special address services"
parent: Advanced Features
---

# Special address services

Cake Wallet supports sending to common address services in addition to standard addresses.

## OpenAlias

Cake Wallet has full support for sending to OpenAlias addresses. Simply type the OpenAlias string in the  `Send` screen.

To add OpenAlias records, go to your DNS provider, and add TXT records as follows (replace `[]` with your relevant info):

For XMR: `“oa1:xmr recipient_address=[]; recipient_name=[]; tx_description=[];”`

For BTC: `“oa1:btc recipient_address=[]; recipient_name=[]; tx_description=[];”`

For LTC: `“oa1:ltc recipient_address=[]; recipient_name=[]; tx_description=[];”`

You will need to enable DNSSEC, or else someone could try to impersonate you. We recommend using a host name such as `donate` or your name/pseudonym, but this is optional.

## Ethereum Name Service (ENS)

{: .warning}
This ENS implementation currently only works for sending to Ethereum addresses. If you query an existing record for a different asset, then it will return an [undecoded string](https://github.com/ensdomains/address-encoder). You can decode this string manually (not recommended). We will add support for decoding with additional assets in a future release.

Cake Wallet has full support for sending to addresses associated with ENS names that end in `.eth`. Simply type the domain in the `Send` screen.

If (and only if) you type in a string that ends in `.eth` (eg: `cakewallet.eth`), then your wallet will communicate directly with your specified Ethereum node or the default Ethereum node (if no custom node is specified).

If you would like to use ENS with a different domain, such as `.com`, `.xyz`, or any other "standard" domain, then please [configure OpenAlias](/docs/advanced-features/special-address-services/#openalias) for that domain instead.

## Unstoppable Domains

Cake Wallet has full support for sending to Unstoppable Domains addresses, including all TLDs and both Ethereum and Polygon domains. Simply type the domain in the `Send` screen.

If (and only if) you type in an Unstoppable Domains TLD, then your wallet will communicate directly with the Unstoppable Domains API.

## FIO Crypto Handles

Cake Wallet has full support for sending to FIO Crypto Handles. Simply type the handle in the `Send` screen.

If (and only if) you type in a string with the FIO crypto handle format (eg: `monero@wallet`), then your wallet will communicate directly with the FIO API.

## Yats

Cake Wallet has full support for sending to Yats. Simply type the yat in the `Send` screen.

If (and only if) you type in an emoji, then your wallet will communicate directly with the Yat API.

## Mastodon

Cake Wallet allows you to type in a Mastodon username (eg: `@cakewallet@mastodon.sdf.org`) in the `Send` screen. If that user has a correctly-formatted address in their Mastodon bio or pinned post for the relevant cryptocurrency, then the wallet will display that address. If this process does not work, make sure the address in the bio is valid and the correct length.

If (and only if) you type in a Mastodon username, then your wallet will communicate directly with the specified Mastodon server's API.

## Twitter Bird Pay

{: .warning}
Twitter Bird Pay is currently not available due to issues with Twitter's API.

Cake Wallet allows you to type in a Twitter username (eg: `@monerocom`) in the `Send` screen. If that user has a correctly-formatted address in their Twitter bio or pinned Tweet for the relevant cryptocurrency, then the wallet will display that address. If this process does not work, make sure the address in the bio is valid and the correct length.

If (and only if) you type in a Twitter username, then your wallet will communicate directly with the Twitter API.

[![How to send crypto with Twitter using Cake Wallet Bird Pay](https://img.youtube.com/vi/dmj4HF8Q85Q/maxresdefault.jpg)](https://www.youtube.com/watch?v=dmj4HF8Q85Q)
