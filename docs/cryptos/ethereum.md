---
title: "Ethereum"
parent: Cryptos
---

# Ethereum

{: .friendly}
Official Website: [ethereum.org](https://ethereum.org/){:target="_blank"}

Ethereum is a decentralized, open-source blockchain that enables smart contracts. Unlike Bitcoin, which is primarily a digital currency, Ethereum provides a more versatile platform allowing developers to build various types of decentralized applications (dApps), and supports token standards such as ERC-20.

## Addresses

In Cake Wallet's Ethereum wallet, there is only one address per wallet, which is standard for the Ethereum ecosystem. Keep in mind that this will have lesser privacy compared to some other assets, where new addresses are automatically generated.

Your Ethereum address will start with `0x` followed by a series of alphanumeric characters.

## Seed Format

Cake Wallet uses a 12-word BIP39 seed format for Ethereum wallets. When creating or restoring a wallet, you'll need to use this 12-word seed phrase or the private key. The derivation path used is `m/44'/60'/0'/0/0`.

## Fee Levels

Transaction fees are a necessary part of sending Ether or ERC-20 tokens. 

Ether (ETH) is consumed as a 'gas' fee when making any transaction from an Ethereum wallet. This also applies to sending ERC-20 tokens. For example, to send USDT, you need to pay a network fee in ETH, not USDT. Thus, sending 10 USDT will cost a certain amount of ETH, and the recipient will receive the full 10 USDT.

Cake Wallet offers three fee levels for transactions:

1. **Slow**: Cheaper but may take longer to confirm.
2. **Medium**: Recommended for most transactions. Balanced speed and cost.
3. **Fast**: Expensive but confirms quickly.

These fee levels are determined automatically using current network fee rates.

We recommend using the `Medium` fee level under normal conditions for a good balance of speed and cost.

Ethereum has two components to fees: the `base` component set as the network minimum, and the `priority` component. By changing the Cake Wallet fee level, you add or remove from this `priority` value. The `base` fee component does not change.

## Tokens

Cake Wallet's Ethereum wallet can store ERC-20 tokens in addition to ETH. Some common ERC-20 tokens such as USDC, USDT, and DAI are displayed by default. To show other ERC-20 tokens, you'll need to navigate to the Home Screen Settings (shown to the right of `Ethereum` on the main screen) and enable them.

Other token types, as well as NFTs, are not currently supported; expanded support is planned for the future.

### Adding a new token

You can add a new ERC-20 token by navigating to the Home screen settings (shown to the right of `Ethereum` on the main screen), then search for your desired token. Click to enable it.

If the token does not appear, then you can add the token by contract address. Paste the address of the custom token you wish to add, then click the `+` button.

## Transaction history

Transaction history is populated using the Etherscan API. You can enable or disable this API lookup in Privacy settings.
