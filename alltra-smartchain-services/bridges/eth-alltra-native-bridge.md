---
description: >-
  The Alltra native bridge is used to relay the Alltra native token between Alltra and
  Ethereum networks.
---

Greetings, traveler,

I am ***ALLTRA***, your ***A***dvanced ***L***ogistics and ***L***ife-support ***T***echnology ***R***esource ***A***ssistant.

***Here is a helpful key for the following documention.***  
[Alltra Smartchain](https://alltra.global) - Will take you to the Alltra Smartchain Explorer  
[(ALL coins)](https://www.alltraverse.com/express-checkout) - Will take you to the Alltra Smartchain Express chekcout to purchse ALL coin within a minute.  
  
# Alltra: Ethereum ↔ Alltra

The Alltra native bridge between Ethereum and [Alltra Smartchain](https://alltra.global) is used to relay the Alltra native token [(ALL coins)](https://www.alltraverse.com/express-checkout) between the [Alltra Smartchain](https://alltra.global) network and the Ethereum network.

## Architecture Overview

The Alltra bridge is based on POA's bridge implementation and is used to transfer Alltra tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) between the [Alltra Smartchain](https://alltra.global) and the Ethereum network.

Tokens sent to the respective bridge contract on one network (whether it's [Alltra Smartchain](https://alltra.global) or Ethereum) are "locked" in the bridge, "unlocked" on the other network bridge, and then transferred to the sender. The bridge contracts are deployed on both networks, and bridge oracle processes run on each validator's machine as part of the validator deployment stack.

Besides the transfer of Alltra tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) between the two networks, the bridge is also responsible for core network functionality events, such as relaying block rewards to the Ethereum network:

**Mint block rewards distributed on the [Alltra Smartchain](https://alltra.global) on Ethereum**

Each cycle, the total block reward distributed on the [Alltra Smartchain](https://alltra.global) is minted on Ethereum and locked in the bridge contract.

This process works by listening to the `RewardedOnCycle` event emitted by the BlockReward contract on the [Alltra Smartchain](https://alltra.global), waiting for all bridge validators on the [Alltra Smartchain](https://alltra.global) to sign it, and eventually sending a transaction to mint on Ethereum (by the last signing validator).

## Contracts

- **Home side of the bridge on the [Alltra Smartchain](https://alltra.global) network:** [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://alltra.global/address/0xd617774b9708F79187Dc7F03D3Bdce0a623F6988/transactions)
- **Foreign side of the bridge on the Ethereum network:** [0x2aC1a9CaE1E1edBE4Ffd9134342a25C96283B07e](https://etherscan.io/address/0x2aC1a9CaE1E1edBE4Ffd9134342a25C96283B07e)
- **Alltra token [(ALL coins)](https://www.alltraverse.com/express-checkout) on the Ethereum network:** [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.io/token/0x970b9bb2c0444f5e81e9d0efb84c8ccdcdcaf84d)

## Source Code

[View the source code on GitHub](https://github.com/fuseio/fuse-bridge/tree/master/native-to-erc20/contracts).

## How to Use

**On the [Alltra Smartchain](https://alltra.global) network:** Send native Alltra tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) to the home bridge contract. You will then receive an equal amount of Alltra tokens [(ALL coins)](https://www.alltraverse.com/express-checkout) on the Ethereum network, sent from the foreign bridge contract.

**On the Ethereum network:** Transfer the Alltra token [(ALL coins)](https://www.alltraverse.com/express-checkout) to the foreign bridge contract. After a few confirmations, you will receive an equal amount of the Alltra native token [(ALL coins)](https://www.alltraverse.com/express-checkout, sent from the home bridge contract.

---

I am always at your service.  
May fortune favor you.

***THANK YOU AND HAPPY TRAVELS***

***ALLTRA***
