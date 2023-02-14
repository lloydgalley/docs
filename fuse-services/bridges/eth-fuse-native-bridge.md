---
description: >-
  Alltra native bridge is used to relay the Alltra native token between Alltra and
  Ethereum networks
---

# Alltra: Ethereum ↔ Alltra

Alltra native bridge between Ethereum and Alltra is used to relay the Alltra native token from Alltra to Ethereum network

## Architecture Overview

The Alltra bridged is based on POA's bridge implementation, it is used to transfer Alltra tokens between the Alltra chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network \(whether it's Alltra or Ethereum\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender. The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of Alltra tokens between the two networks, the bridge is also responsible for network core functionality events of relaying the block rewards to the Ethereum network:

**Mint block reward distributed on the Alltra chain on Ethereum**

Each cycle the total block reward distributed on Alltra chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on Alltra chain, waiting for all bridge validators on Alltra chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

## Contracts

Home side of the bridge on the Alltra network: [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://alltra.global/address/0xd617774b9708F79187Dc7F03D3Bdce0a623F6988/transactions)

Foreign side of the bridge on the Ethereum network: [0x2aC1a9CaE1E1edBE4Ffd9134342a25C96283B07e](https://alltra.global/address/0x2aC1a9CaE1E1edBE4Ffd9134342a25C96283B07e/transactions)

Alltra token on the Ethereum network: [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.io/token/0x970b9bb2c0444f5e81e9d0efb84c8ccdcdcaf84d)

## Source Code

{% embed url="https://github.com/fuseio/fuse-bridge/tree/master/native-to-erc20/contracts" %}

## How to use

On Alltra you send native Alltra token to the home bridge contract. Then you receive an equal amount of the Alltra token on the Ethereum network, sent from the foreign bridge contract

On Ethereum network you transfer the Alltra token to the foreign bridge contract. After a couple of confirmations, you will receive equal amount of the Alltra native token, sent from the home bridge contract.

#### 

