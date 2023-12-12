---
title: "Custom node"
parent: Advanced Features
---

# Custom node

You can manually specify a node in settings. This custom node will be used for all wallets of that type (eg: all Monero wallets).

On the home screen, click on the hamburger menu in the upper right, then click `Nodes`. You can instead click on the top sync status bar on the home screen.

## Add new custom node

You can add a custom node in app settings, or in advanced privacy settings during wallet creation.

### Add new custom node in settings

To add a new custom node, click on `Add new node +`. Type in a Node Address, Node port (usually 18081 or 18089), a login (optional; only if needed), and a password (optional; only if needed). Tick `Use SSL` only if instructed or if you know SSL is used.

Here is an example using Seth for Privacy's Monero node:

* Node Address: `node.sethforprivacy.com`
* Node port: `18089`
* Login: (blank)
* Password: (blank)
* Use SSL: (unticked)
* Trusted: (unticked)

ONLY tick "Trusted" if you are running your own node and trust that it is secure! This will make the connection more efficient.

### Add new custom node in advanced privacy settings

When creating a wallet, first select the wallet asset type you want. Then, in the same screen where you are prompted for a wallet name, click `Advanced Privacy Settings`. Add your custom node there. Save the settings, choose a wallet name, and proceed with setup as normal.

## Node lists

We run a service uptime tracker and list of Monero nodes at [**nodes.monero.com**](https://nodes.monero.com). We also have an [official onion node](/docs/advanced-features/tor-with-orbot/#connect-to-an-onion-node).

We strongly recommend [running your own node](https://guides.monero.com/docs/tutorials/monero-node)!

## Remove a node

You can remove any node except the current node. For a stored node that isn't in current use, swipe right to left on that node to display a Delete icon; click `Delete`. You will be asked to confirm to remove the node; click `Remove`.
