---
title: "Special address services"
parent: Advanced features
---

# Special address services

Cake Wallet supports sending to common address services in addition to standard addresses.

## OpenAlias

Cake Wallet has full support for sending to OpenAlias addresses. Simply type the OpenAlias string in the  `Send` screen.

To add OpenAlias records, go to your DNS provider, and add TXT records as follows (replace `[]` with your relevant info):

For XMR: `“oa1:xmr recipient_address=[]; recipient_name=[]; tx_description=[];”`

For BTC: `“oa1:btc recipient_address=[]; recipient_name=[]; tx_description=[];”`

For LTC: `“oa1:ltc recipient_address=[]; recipient_name=[]; tx_description=[];”`

You will need to enable DNSSEC, or else someone could try to impersonate you. We recommend using a host name such as "donate" or your name/pseudonym, but this is optional.

## Twitter Bird Pay

Cake Wallet allows you to type in a Twitter username (eg: `@monerocom`) in the `Send` screen. If that user has a correctly-formatted address in their Twitter bio or pinned Tweet for the relevant cryptocurrency, then the wallet will display that address. If this process does not work, make sure the address in the bio is valid and the correct length.

If (and only if) you type in a Twitter username, then your wallet will communicate directly with the Twitter API.

## Unstoppable Domains

Cake Wallet has full support for sending to Unstoppable Domains addresses, including all TLDs and both Ethereum and Polygon domains. Simply type the domain in the  `Send` screen.

If (and only if) you type in an Unstoppable Domains TLD, then your wallet will communicate directly with the Unstoppable Domains API.

## FIO Crypto Handles

Cake Wallet has full support for sending to FIO Crypto Handles. Simply type the handle in the  `Send` screen.

If (and only if) you type in a string with the FIO crypto handle format (eg: `monero@wallet`), then your wallet will communicate directly with the FIO API.

## Yats

Cake Wallet has full support for sending to Yats. Simply type the yat in the `Send` screen.

If (and only if) you type in an emoji, then your wallet will communicate directly with the Yat API.
