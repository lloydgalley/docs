---
description: >-
  The BNB inverse-native bridge is used to relay the BNB native token between
  Binance Smart Chain (BSC) and Alltra networks.
---

# BNB: BSC ↔ Alltra

Greetings, traveler,

I am ***ALLTRA***, your ***A***dvanced ***L***ogistics and ***L***ife-support ***T***echnology ***R***esource ***A***ssistant.
  
***Here is a helpful key for the following documention.***  
[Alltra Smartchain](https://alltra.global) - Will take you to the Alltra Smartchain Explorer  

## Architecture Overview

This bridge is a two-layer bridge. At the base level, the Arbitrary Message Bridge (AMB) is responsible for relaying messages between the networks. On top of the AMB, pluggable mediators implement the contract logic for token relaying of various assets. More information is available [here](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge).

The contract is called an "inverse-native" bridge because the home and foreign networks are reversed. In this case, the [Alltra Smartchain](https://alltra.global) network is the foreign network, and BSC is the home network.

## Contracts

- **Home side of the bridge on the BSC network:** [0x51849F05090b222FFc329DC8825de0D7e26F84A1](https://bscscan.com/address/0x51849F05090b222FFc329DC8825de0D7e26F84A1)
- **Foreign side of the bridge on the [Alltra Smartchain](https://alltra.global) network:** [0xA3C59198c10cB1ba9A3Ab924A23253072b393f25](https://alltra.global/address/0xA3C59198c10cB1ba9A3Ab924A23253072b393f25)
- **BNB token on the [Alltra Smartchain](https://alltra.global) network:** [0x6acb34b1Df86E254b544189Ec32Cf737e2482058](https://alltra.global/address/0x6acb34b1Df86E254b544189Ec32Cf737e2482058/transactions)
- **Home side of the AMB bridge on the BSC network:** [0x3A5A320a2f98a3Fe39c9040e7e3E9caA7F0D5bd6](https://bscscan.com/address/0x3A5A320a2f98a3Fe39c9040e7e3E9caA7F0D5bd6)
- **Foreign side of the AMB bridge on the [Alltra Smartchain](https://alltra.global) network:** [0x1ee6E3E3d2DE779858728E157B3B9C488bA7b706](https://alltra.global/address/0x1ee6E3E3d2DE779858728E157B3B9C488bA7b706)

## Source Code

[View the source code on GitHub](https://github.com/alltra/tokenbridge-contracts).

## How to Use

**To send tokens from the BSC network:**

Send native BNB tokens to the home bridge contract. You will then receive an equal amount of the BNB token on the [Alltra Smartchain](https://alltra.global) network, sent from the foreign bridge contract.

**To send tokens from the [Alltra Smartchain](https://alltra.global) network:**

1. Approve the "BNB on Alltra" TL20 token to be spent by the Foreign bridge.
2. Call the `relayTokens` function on the bridge contract.

The `relayTokens` method will lock the TL20 tokens on the foreign bridge. After a few confirmations, an equal amount of the BNB native token will be released from the home bridge contract on BSC.

---

I am always at your service.  
May fortune favor you.

***THANK YOU AND HAPPY TRAVELS***

***ALLTRA***
