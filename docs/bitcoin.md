---
title: "Bitcoin"
---

# Bitcoin

## Addresses

We automatically generate new Bitcoin addresses after each use for better privacy. Previous addresses continue to work.

We use the same derivation scheme as Electrum: `m/0/x` for receive addresses, and `m/1/x` for change addresses.

## Seed format

We use the Electrum seed format. We support restoring seeds generated in the Electrum seed format, not the BIP39 format or other formats.

## Bitcoin fee levels

We recommend leaving your Cake Wallet fee for Bitcoin as `Medium`.

| Cake Wallet name | estimatefee value | Description |
| --- | --- | --- |
| Slow ~24hrs | 100 | Save on fees if you can wait a full day for the transaction to be confirmed. |
| Medium | 5 | The best blend of speed and cost. You'll usually get a confirmation within 3 blocks. |
| Fast | 1 | Aggressively pursues inclusion in the next block, usually overpaying. |
