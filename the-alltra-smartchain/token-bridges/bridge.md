---
description: This tutorial explains how to transfer
---

# Bridge between Alltra chain & Ethereum

The bridge, based on POA's bridge implementation, is used to transfer Alltra tokens between the Alltra chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network \(whether it's Alltra or Ethereum\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender.

The validators of the bridge on both network are the Alltra chain validators. This means that validators, as part of their governance responsibilities, also need to validate bridge transactions and therefore hold Alltra tokens to "approve" bridge transactions on Alltra chain and hold ETH to "approve" transactions on Ethereum.

Each bridge transaction must be approved by a majority \(over 50%\) of the validators in order to be processed successfully.

The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of Alltra tokens between the two networks, the bridge is also responsible for network core functionality events:

**Mint block reward distributed on the Alltra chain on Ethereum**

Each cycle the total block reward distributed on Alltra chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on Alltra chain, waiting for all bridge validators on Alltra chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

**Update Alltra chain validators on Ethereum**

Each cycle the Alltra chain validators are selected from a random snapshot of pending validators.

Those validators, being also the bridge validators, need to be updated on Ethereum as well.

This works by listening to the \`InitiateChange\` event emitted by the Consensus contract on Alltra chain, waiting for all bridge validators on Alltra chain to sign it, and eventually sending a transaction to set the bridge validators on Ethereum \(by the last signing validator\).

{% hint style="info" %}
Alltra chain bridge - [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://alltra.global/address/0xd617774b9708f79187dc7f03d3bdce0a623f6988)

Ethereum bridge - [0x2aC1a9CaE1E1edBE4Ffd9134342a25C96283B07e](https://etherscan.io/address/0x2aC1a9CaE1E1edBE4Ffd9134342a25C96283B07e)

Alltra token on Ethereum - [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.io/token/0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d)
{% endhint %}

**Using the bridge**

**Transfering from Ethereum mainnet to Fusenet** - send your erc20 Alltra tokens to the Ethereum bridge for them to be released from the Alltra chain bridge and be avaliable in your native Alltra wallet.

**Transfering from Fusenet to Ethereum mainnet** - send your Native Alltra tokens to the Alltra chain bridge for them to be released from the mainnet bridge and be avaliable in your Mainnet wallet. _Note: there is currently a minimum transfer amount of 30000 Alltra across the Alltra chain bridge_

