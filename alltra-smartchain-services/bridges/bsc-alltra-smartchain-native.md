---
description: >-
  The [Alltra Smartchain](https://alltra.global) native bridge is used to relay the [Alltra Smartchain](https://alltra.global) native token [(ALL coin)](https://www.alltraverse.com/express-checkout) between [Alltra Smartchain](https://alltra.global) and
  Binance Smart Chain (BSC) networks.
---

# Alltra Native: BSC ↔ [Alltra Smartchain](https://alltra.global)

Greetings, traveler,

I am ***ALLTRA***, your ***A***dvanced ***L***ogistics and ***L***ife-support ***T***echnology ***R***esource ***A***ssistant.

***Here is a helpful key for the following documention.***  
[Alltra Smartchain](https://alltra.global) - Will take you to the Alltra Smartchain Explorer  

## Architecture Overview

This bridge is a two-layer bridge. At the base level, the Arbitrary Message Bridge (AMB) is responsible for relaying messages between the networks. On top of the AMB, pluggable mediators implement the contract logic for token relaying of various assets. More information is available [here](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge).

## Contracts

- **Home side of the bridge on the [Alltra Smartchain](https://alltra.global) network:** [0xf9b276A1A05934ccD953861E8E59c6Bc428c8cbD](https://alltra.global/address/0xf9b276A1A05934ccD953861E8E59c6Bc428c8cbD/transactions)
- **Foreign side of the bridge on the BSC network:** [0x61A8287fA7a9f4D10F4699BC2aE77f962DC508B6](https://bscscan.com/address/0x61A8287fA7a9f4D10F4699BC2aE77f962DC508B6)
- **Alltra token [(ALL coins)](https://www.alltraverse.com/express-checkout) on the BSC network:** [0x5857c96DaE9cF8511B08Cb07f85753C472D36Ea3](https://bscscan.com/token/0x5857c96dae9cf8511b08cb07f85753c472d36ea3)
- **Home side of the AMB bridge on the [Alltra Smartchain](https://alltra.global) network:** [0x1ee6E3E3d2DE779858728E157B3B9C488bA7b706](https://alltra.global/address/0x1ee6E3E3d2DE779858728E157B3B9C488bA7b706)
- **Foreign side of the AMB bridge on the BSC network:** [0x3A5A320a2f98a3Fe39c9040e7e3E9caA7F0D5bd6](https://bscscan.com/address/0x3A5A320a2f98a3Fe39c9040e7e3E9caA7F0D5bd6)

## Source Code

[View the source code on GitHub](https://github.com/alltra/tokenbridge-contracts).

## How to Use

**To send tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) from the [Alltra Smartchain](https://alltra.global) network:**

Send native Alltra tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) to the home bridge contract. You will then receive an equal amount of the Alltra token [(ALL coins)](https://www.alltraverse.com/express-checkout) on the BSC network, sent from the foreign bridge contract.

**To send tokens from the BSC network:**

1. Approve the Alltra ACR20 tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) to be spent by the Foreign ACR20 bridge.
2. Call the `relayTokens` function on the bridge contract.

The `relayTokens` method will lock the ACR20 tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) on the foreign bridge. After a few confirmations, an equal amount of the Alltra ACR20 token [(ALL coins)](https://www.alltraverse.com/express-checkout) will be released from the home bridge contract on BSC.

---

I am always at your service.  
May fortune favor you.

***THANK YOU AND HAPPY TRAVELS***

***ALLTRA***
