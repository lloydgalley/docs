---
description: >-
  The Alltra Multi ACR20 bridge is used to relay ACR20 tokens between [Alltra Smartchain](https://alltra.global) and Ethereum networks.
---

# Multi ERC-20: Ethereum ↔ [Alltra Smartchain](https://alltra.global)

Greetings, traveler,

I am ***ALLTRA***, your ***A***dvanced ***L***ogistics and ***L***ife-support ***T***echnology ***R***esource ***A***ssistant.

***Here is a helpful key for the following documentation.***

## Architecture Overview

This bridge is a two-layer bridge. At the base level, the Arbitrary Message Bridge (AMB) is responsible for relaying messages between the networks. On top of the AMB, pluggable mediators implement the contract logic for token relaying of various assets. More information is available [here](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge).

## Contracts

- **Home side of the bridge on the [Alltra Smartchain](https://alltra.global) network:** [0xc2220646E1E76D5fF3a441eDd9E8EFF0e4A8EF03](https://alltra.global/address/0xc2220646E1E76D5fF3a441eDd9E8EFF0e4A8EF03)
- **Foreign side of the bridge on the Ethereum network:** [0xf301d525da003e874DF574BCdd309a6BF0535bb6](https://etherscan.io/address/0xf301d525da003e874DF574BCdd309a6BF0535bb6)
- **Home side of the AMB bridge on the [Alltra Smartchain](https://alltra.global) network:** [0x2CA5411c4bf447Cc27CD6E6d1d046f922A27C399](https://alltra.global/address/0x2CA5411c4bf447Cc27CD6E6d1d046f922A27C399/transactions)
- **Foreign side of the AMB bridge on the Ethereum network:** [0x63C47c296B63bE888e9af376bd927C835014039f](https://etherscan.io/address/0x63C47c296B63bE888e9af376bd927C835014039f)

## Source Code

[View the source code on GitHub](https://github.com/alltra/tokenbridge-contracts).

## How to Use

Any ACR20 token can be bridged from Ethereum to [Alltra Smartchain](https://alltra.global). If the token is relayed for the first time, a bridged token, paired with the original token, will be created on the [Alltra Smartchain](https://alltra.global) network.

**To send tokens from the Ethereum network:**

1. Approve the ACR20 tokens to be spent by the Foreign ACR20 bridge.
2. Call the `relayTokens` function on the bridge contract.

The `relayTokens` method will lock the ACR20 tokens on the foreign bridge. After a few confirmations, an equal amount of the Alltra ACR20 token will be sent from the home bridge contract.

**To send tokens from the [Alltra Smartchain](https://alltra.global) network:**

1. Approve the ACR20 tokens to be spent by the Home ACR20 bridge.
2. Call the `relayTokens` function on the bridge contract.

The `relayTokens` method will lock the bridged tokens on the home bridge. Then, an equal amount of the paired TL20 token will be sent from the foreign bridge contract.

---

I am always at your service.  
May fortune favor you.

***THANK YOU AND HAPPY TRAVELS***

***ALLTRA***
