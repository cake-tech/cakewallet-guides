---
title: "Resolving connection issues"
parent: FAQ
---

# Resolving connection issues

Occasionally, you might have trouble connecting to a node while using Cake Wallet. This guide is designed to help you identify and resolve such connection problems for a smoother experience.

## Connection status

Understanding the connection status of your wallet can be the first step in resolving any issues. Below are the different types of statuses you might encounter:

- **Disconnected**: A connection issue is preventing your wallet from accessing a node.

- **Connecting**: Your wallet is currently initiating connection to the node, but has not yet established a stable connection.

- **Attempting Sync**: Your wallet has connected to a node, and is currently exchanging information before the sync begins.

- **# Blocks Remaining**: Your wallet is currently synchronizing; you should be patient and keep the wallet app open until the number reaches zero. If the number decreases very slowly, you can follow our troubleshooting steps.

- **Synchronized**: Your wallet is synced, and no further action is needed.

If your wallet ever appears to be stuck at any of these steps, it's recommended to attempt the following steps.

## WiFi & data

Some cellular data providers might block cryptocurrency-related connections. Similarly, some WiFi networks may be unstable or have firewalls that restrict your connection. If you're experiencing issues, try switching between WiFi and data to see if one connection type works better than the other.

## VPN

It's possible that a VPN may help you to connect properly if a network firewall is blocking your connection. If you have a VPN available, it can be helpful to try enabling it.

On the other hand, certain VPN providers may block or restrict access to cryptocurrency nodes, so if you are having issues connecting through a VPN, it may help to disable it.

## Nodes

If your wallet is stuck at the `Disconnected` or `Attempting Sync` status, changing nodes might help. To do this:

1. Tap the menu at the top right of the screen.
2. Select `Connection and sync`.
3. Choose `Manage nodes`.
4. Select a new node from the list. Only nodes highlighted with a green dot will work; red dots are unavailable. Alternatively, you can [add a new custom node](/docs/advanced-features/custom-node/).

## Tor

If you're ***not*** using a Tor proxy like Orbot, do not connect to `.onion` nodes. These nodes are designed for use through the Tor network and will not work properly without a Tor proxy. If you're not using such a proxy, enable Tor or switch to a different clearnet node.

---

We hope this guide helps you resolve any connection issues you're facing. If you still encounter problems, please reach out to our support team for further assistance. You can contact us using the support bubble in the lower right of this page, or by using the in-app support.
