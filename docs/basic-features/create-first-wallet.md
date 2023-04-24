---
title: "Create first wallet"
parent: Basic features
nav_order: 1
---

# Create first wallet

We want to welcome you to using Cake Wallet! We hope you have a wonderful experience. If you have any questions, please reach out to our support! :D

## Download the app

You first need the Cake Wallet official application.

* Apple App Store (iPhone, MacOS): [https://cakewallet.com/ios](https://cakewallet.com/ios)
* Google Play: [https://cakewallet.com/gp](https://cakewallet.com/gp)
* Android APK: [https://cakewallet.com/apk](https://cakewallet.com/apk)
* Linux: [https://github.com/cake-tech/cake_wallet/releases](https://github.com/cake-tech/cake_wallet/releases)

## Initial app configuration

### For Linux only

If you are using Linux, you can optionally change the default file location.

The default Linux file save location is `~/Documents/cake_wallet`. If you would like to specify a different location, please run the two commands, replacing `/set/your/prefered/location/here` with your preferred location:

```
export CAKE_WALLET_DIR=/set/your/prefered/location/here
export XDG_DATA_HOME=$CAKE_WALLET_DIR/preferences
```

### For all devices

Open the wallet application. You will see the option to create your first wallet. Choose only one cryptocurrency type; you can choose additional ones later (see [Create another wallet](/docs/basic-features/create-another-wallet)).

You can choose a manual wallet name, or you can click the right icon to generate a random name. This can't be changed later.

You will be asked to set an access PIN. This stays on your device. You can choose a 4 digit PIN by default, or you can click the text to change to a 6 digit PIN. You can enable biometric authentication later in settings.

## Write down your mnemonic seed!

It is ***absolutely imperative*** that you ***save your seed in a safe place***! The most common user error is forgetting to write down the seed, resulting in a loss of funds.

You need to save the seed in a safe place. The definition of "safe" depends on your use-case, but it looks like this for most users:

* Put one written copy in a home safe, and another copy in a bank safety deposit box.
* Store the seed in a password manager with a ***strong*** password.

If you need to upgrade to a higher security setup later, you can create a new wallet, back up the seed with a high degree of security, and then send your funds to the new wallet.
