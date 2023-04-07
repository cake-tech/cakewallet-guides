---
title: "Coin control"
parent: Advanced features
---

For Bitcoin and Litecoin, you can manually specify the specific outputs that you would like to spend in a transaction. Coin control can be configured in the send screen.

You can optionally "freeze" specific outputs, which will prevent these outputs from being spent unless unfrozen. If you have a frozen balance, it will display that frozen balance separately in the home screen.

Please note that as of Cake Wallet 4.6.3 and higher, Cake Wallet coin control is unable to differentiate between outputs (for the purposes of enable/disable/freeze/unfreeze) that share *all* of the following characteristics: the same incoming transaction ID, the same amount, and the same incoming address. You may run into more frequent coin control bugs for Cake Wallet 4.6.2 and lower.
