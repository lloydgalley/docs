---
description: >-
  The Alltra ↔ BSC ACR20 bridge is used to relay ACR20 tokens between [Alltra Smartchain](https://alltra.global) and
  Binance Smart Chain networks.
---

# Multi ACR20: BSC ↔ [Alltra Smartchain](https://alltra.global)

Greetings, traveler,

I am ***ALLTRA***, your ***A***dvanced ***L***ogistics and ***L***ife-support ***T***echnology ***R***esource ***A***ssistant.  

***Here is a helpful key for the following documention.***  
[Alltra Smartchain](https://alltra.global) - Will take you to the Alltra Smartchain Explorer  

## Architecture Overview

This bridge is a two-layer bridge. At the base level, the Arbitrary Message Bridge (AMB) is responsible for relaying messages between the networks. On top of the AMB, pluggable mediators implement the contract logic for token relaying of various assets. More information is available [here](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge).

The BSC bridge is a restricted bridge, meaning that only the Alltra team can add new tokens to the bridge. This is necessary because new tokens must be manually associated with their counterparts on the [Alltra Smartchain](https://alltra.global) network.

## Contracts

- **Home side of the bridge on the [Alltra Smartchain](https://alltra.global) network:** [0x93B477BA32092F5Db932003639DD5d875B2EfC94](https://alltra.global/address/0x93B477BA32092F5Db932003639DD5d875B2EfC94/transactions)
- **Foreign side of the bridge on the BSC network:** [0xc461e59276a2B03B9ebb1289C2c9Cd020677c3A9](https://bscscan.com/address/0xc461e59276a2B03B9ebb1289C2c9Cd020677c3A9)
- **Home side of the AMB bridge on the [Alltra Smartchain](https://alltra.global) network:** [0x1ee6E3E3d2DE779858728E157B3B9C488bA7b706](https://alltra.global/address/0x1ee6E3E3d2DE779858728E157B3B9C488bA7b706/transactions)
- **Foreign side of the AMB bridge on the BSC network:** [0x3A5A320a2f98a3Fe39c9040e7e3E9caA7F0D5bd6](https://bscscan.com/address/0x3A5A320a2f98a3Fe39c9040e7e3E9caA7F0D5bd6)

## Source Code

[View the source code on GitHub](https://github.com/alltra/tokenbridge-contracts).

## How to Use

Currently, only WETH is supported for this bridge, with more tokens coming soon.

**To send tokens from the BSC network:**

1. Approve the ACR20 tokens to be spent by the Foreign ACR20 bridge.
2. Call the `relayTokens` function on the bridge contract.

The `relayTokens` method will lock the ACR20 tokens on the foreign bridge. An equal amount of the [Alltra Smartchain](https://alltra.global) ACR20 token will then be sent from the home bridge contract.

**To send tokens from the Alltra network:**

1. Approve the ACR20 tokens to be spent by the Home ACR20 bridge.
2. Call the `relayTokens` function on the bridge contract.

The `relayTokens` method will lock the bridged tokens on the home bridge. An equal amount of the paired ACR20 token will then be sent from the foreign bridge contract.

---

I am always at your service.  
May fortune favor you.

***THANK YOU AND HAPPY TRAVELS***

***ALLTRA***
