---
title: "Solana"
parent: Cryptos
---

# Solana

{: .friendly}
Official Website: [solana.com](https://solana.com/){:target="_blank"}

## Addresses

In Cake Wallet's Solana wallet, there is only one address per wallet, which is standard for the Solana ecosystem. Keep in mind that this will have lesser privacy compared to some other assets, where new addresses are automatically generated.

## Seed Format

Cake Wallet uses a 12-word BIP39 seed format for Solana wallets. When creating or restoring a wallet, you'll need to use this 12-word seed phrase or the private key. The derivation path used is `m/44'/60'/0'/0/0`.

## Fee Levels

Transaction fees are a necessary part of sending SOL or SPL tokens. 

Solana (SOL) is required as a fee when making any transaction from a Solana wallet. This also applies to sending SPL tokens. For example, to send USDT, you need to pay a network fee in SOL, not USDT. Thus, sending 10 USDT will cost a certain amount of SOL, and the recipient will receive the full 10 USDT.

Cake Wallet offers three fee levels for transactions:

1. **Slow**: Cheaper but may take longer to confirm.
2. **Medium**: Recommended for most transactions. Balanced speed and cost.
3. **Fast**: Expensive but confirms quickly.

These fee levels are determined automatically using current network fee rates.

We recommend using the `Medium` fee level under normal conditions for a good balance of speed and cost.

Solana has two components to fees: the `base` component set as the network minimum, and the `priority` component. By changing the Cake Wallet fee level, you add or remove from this `priority` value. The `base` fee component does not change.

## Tokens

Cake Wallet's Solana wallet can store SPL tokens in addition to SOL. Some common ERC-20 tokens such as USDC, USDT, and DAI are displayed by default. To show other ERC-20 tokens, you'll need to navigate to the Home Screen Settings (shown to the right of `Solana` on the main screen) and enable them.

Other token types, as well as NFTs, are not currently supported; expanded support is planned for the future.

### Adding a new token

You can add a new ERC-20 token by navigating to the Home screen settings (shown to the right of `Solana` on the main screen), then search for your desired token. Click to enable it.

If the token does not appear, then you can add the token by contract address. Paste the address of the custom token you wish to add, then click the `+` button.