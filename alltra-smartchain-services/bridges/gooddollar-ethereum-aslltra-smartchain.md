---
description: >-
  The GoodDollar bridge is used to relay GoodDollar tokens between [Alltra Smartchain](https://alltra.global) and
  Ethereum networks.
---

# GoodDollar: Ethereum ↔ [Alltra Smartchain](https://alltra.global)

Greetings, traveler,

I am ***ALLTRA***, your ***A***dvanced ***L***ogistics and ***L***ife-support ***T***echnology ***R***esource ***A***ssistant.

***Here is a helpful key for the following documention.***  
[Alltra Smartchain](https://alltra.global) - Will take you to the Alltra Smartchain Explorer  
[(ALL coins)](https://www.alltraverse.com/express-checkout) - Will take you to the Alltra Smartchain Express chekcout to purchse ALL coin within a minute.  

## Architecture Overview

This bridge is a two-layer bridge. At the base level, the Arbitrary Message Bridge (AMB) is responsible for relaying messages between the networks. On top of the AMB, pluggable mediators implement the contract logic for token relaying of various assets. More information is available [here](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge).

## Contracts

- **Home side of the bridge on the [Alltra Smartchain](https://alltra.global) network:** [0xD39021DB018E2CAEadb4B2e6717D31550e7918D0](https://alltra.global/address/0xD39021DB018E2CAEadb4B2e6717D31550e7918D0/transactions)
- **Foreign side of the bridge on the Ethereum network:** [0xD5D11eE582c8931F336fbcd135e98CEE4DB8CCB0](https://etherscan.io/address/0xD5D11eE582c8931F336fbcd135e98CEE4DB8CCB0)
- **GoodDollar token on the [Alltra Smartchain](https://alltra.global) network:** [0x495d133b938596c9984d462f007b676bdc57ecec](https://alltra.global/address/0x495d133B938596C9984d462F007B676bDc57eCEC/transactions)
- **GoodDollar token on the Ethereum network:** [0x67c5870b4a41d4ebef24d2456547a03f1f3e094b](https://etherscan.io/address/0x67c5870b4a41d4ebef24d2456547a03f1f3e094b)
- **Home side of the AMB bridge on the [Alltra Smartchain](https://alltra.global) network:** [0x2CA5411c4bf447Cc27CD6E6d1d046f922A27C399](https://alltra.global/address/0x2CA5411c4bf447Cc27CD6E6d1d046f922A27C399/transactions)
- **Foreign side of the AMB bridge on the Ethereum network:** [0x63C47c296B63bE888e9af376bd927C835014039f](https://etherscan.io/address/0x63C47c296B63bE888e9af376bd927C835014039f)

## Source Code

[View the source code on GitHub](https://github.com/fuseio/tokenbridge-contracts).

## How to Use

Any ACR20 [(ALL coins)](https://www.alltraverse.com/express-checkout) token can be bridged from Ethereum to [Alltra Smartchain](https://alltra.global). If the token is relayed for the first time, a bridged token, paired with the original token, will be created on the Alltra network.

**To send tokens from the Ethereum network:**

1. Approve the ACR20 [(ALL coins)](https://www.alltraverse.com/express-checkout) tokens to be spent by the Foreign ACR20 [(ALL coins)](https://www.alltraverse.com/express-checkout) bridge.
2. Call the `relayTokens` function on the bridge contract.

The `relayTokens` method will lock the ACR20 tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) on the foreign bridge. After a few confirmations, an equal amount of the [Alltra Smartchain](https://alltra.global) ACR20 token [(ALL coins)](https://www.alltraverse.com/express-checkout) will be sent from the home bridge contract.

**To send tokens from the Alltra network:**

1. Approve the ACR20 tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) to be spent by the Home ACR20 [(ALL coins)](https://www.alltraverse.com/express-checkout) bridge.
2. Call the `relayTokens` function on the bridge contract.

The `relayTokens` method will lock the bridged tokens on the home bridge. Then, an equal amount of the paired ACR20 token [(ALL coins)](https://www.alltraverse.com/express-checkout) will be sent from the foreign bridge contract.

---

I am always at your service.  
May fortune favor you.

***THANK YOU AND HAPPY TRAVELS***

***ALLTRA***
