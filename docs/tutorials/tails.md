---
title: "Tails"
parent: Tutorials
---

# Tails

To use Cake Wallet on Tails, you must run Cake Wallet with extra arguments to store the wallet and preferences in your Persistent volume.

To create Persistent Storage, please see [here](https://tails.net/doc/persistent_storage/create/index.en.html).

It is recommended to put the entire Cake Wallet installation under the Persistent volume to avoid re-downloading everytime Tails is started up.

## Installation

Open the Tor Browser and go to `https://github.com/cake-tech/cake_wallet/releases/` and download the latest release. Example: `Cake_Wallet_v4.12.0_Linux.tar.xz`

Extract the `Cake_Wallet.xz` to the Persistent volume

[![Extract to Persistent volume](./image1.png){:width=75%"}](./image1.png)

## Running

Open the `cake_wallet` folder in the Persistent volume

Right-click on a blank area and click `Open in Terminal`

[![Open in Terminal](./image2.png){:width=75%"}](./image2.png)

Run Cake Wallet using this command

`CAKE_WALLET_DIR=$HOME/Persistent/cake_wallet/ XDG_DATA_HOME=$CAKE_WALLET_DIR/preferences ./cake_wallet`

This will place the wallets under `/home/amnesia/Persistent/cake_wallet/wallets` and the preferences file under `/home/amnesia/Persistent/cake_wallet/preferences/`

You can change the `CAKE_WALLET_DIR` and `XDG_DATA_HOME` to any other directory, as long as there are somewhere in your Persistent volume!

[![Run Cake Wallet](./image3.png){:width=75%"}](./image3.png)
