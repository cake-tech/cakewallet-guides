---
title: "Tails"
parent: Tutorials
---

# Tails

To use Cake Wallet on Tails, you must run Cake Wallet with extra arguments to store the wallet and preferences in your Persistent volume.

Tails is an amnesic operating system. Everytime Tails is shutdown, it loses any extra programs or files you downloaded. In order to use Cake Wallet on Tails, you must setup `Persistent Storage`. This allows you to save the Cake Wallet installation and not need to set it up everytime you restart your Tails install.

To create Persistent Storage, please see [here](https://tails.net/doc/persistent_storage/create/index.en.html).

It is recommended to put the entire Cake Wallet installation under the Persistent volume to avoid re-downloading everytime Tails is started up.

## Installation

Open the Tor Browser, go to `https://github.com/cake-tech/cake_wallet/releases/`, and download the latest release. Example: `Cake_Wallet_v4.11.0_Linux.tar.xz`

The download will be stored at `/home/amnesia/Tor Browser`. Click the Download icon on the top-right, then click the `Open in Folder` icon to access the download folder.

[![Open In Folder](./image.png){:width=75%"}](./image.png)

Extract the Cake_wallet.tar.xz into the Persistent volume at `/home/amnesia/Persistent`.

Example video for extracting the Cake Wallet files into a custom `cake_wallet` Persistent directory.

<iframe width="480" height="360" src="./extract.webm" frameborder="0"> </iframe>

## Running

Open the `cake_wallet` folder (or whichever folder you chose) in the Persistent volume.

Right-click on a blank area and click `Open in Terminal`.

[![Open in Terminal](./image2.png){:width=75%"}](./image2.png)

Run Cake Wallet using this command.

`CAKE_WALLET_DIR=$HOME/Persistent/cake_wallet/ XDG_DATA_HOME=$CAKE_WALLET_DIR/preferences ./cake_wallet`

This will place the wallets under `/home/amnesia/Persistent/cake_wallet/wallets` and the preferences file under `/home/amnesia/Persistent/cake_wallet/preferences/`

You can change the `CAKE_WALLET_DIR` and `XDG_DATA_HOME` to any other directory, as long as they are somewhere in your Persistent volume!

[![Run Cake Wallet](./image3.png){:width=75%"}](./image3.png)
