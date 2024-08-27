---
description: An overview of the network's contracts with descriptions and links
---

# Alltra Smartchain Consensus (Technical)

Greetings, traveler,

I am ***ALLTRA***, your ***A***dvanced ***L***ogistics and ***L***ife-support ***T***echnology ***R***esource ***A***ssistant.

Consensus is a fault-tolerant mechanism used in blockchain systems to achieve agreement on the single state of the network. The [Alltra Smartchain](https://alltra.global) network uses a Delegated Proof of Stake (DPoS) consensus model, which, while it may sound complex, is quite straightforward. DPoS is a variation of Proof of Stake (PoS). In PoS, a set of validators is responsible for keeping the network updated and validating its state. They do this in turns, where each validator has their turn in line. During their turn, the validator updates the network's state, and the rest of the validators verify that the update is valid.

Being a validator is technically complex. In addition to staking [Alltra Smartchain](https://alltra.global) tokens, validators need to run specialized software and maintain 100% uptime hardware. To allow anyone to take part in and own a portion of the network, the DPoS consensus mechanism was introduced. With Delegated Proof of Stake, a token holder can delegate their validation rights to a third-party validator, who will perform the validation on their behalf, with the reward being shared according to a predefined agreement.

{% hint style="info" %}
All the contracts in this section are available on our [GitHub](https://github.com/alltra/alltra-smartchain/tree/master/contracts).
{% endhint %}

## [Consensus - 0x2aC1a9CaE1E1edBE4Ffd9134342a25C96283B07e](https://alltra.global/address/0x2aC1a9CaE1E1edBE4Ffd9134342a25C96283B07e)

This contract is responsible for handling the network's DPoS consensus. It stores the current validator set and selects a new validator set at the end of each cycle. The logic for updating the validator set involves selecting a random snapshot from those taken during the cycle.

Snapshots are taken of pending validators, which are those who have staked more than the minimum required to become a network validator. Therefore, this contract also manages staking, delegating, and withdrawing funds.

The stake amount for a validator is the sum of the staked and delegated amounts to its address.

This contract is based on the `non-reporting ValidatorSet` as [described in the Parity Wiki](https://wiki.parity.io/Validator-Set.html#non-reporting-contract).

{% hint style="info" %}
Minimum stake amount: 100,000 [Alltra Smartchain](https://alltra.global) tokens (ALL coins).

Cycle duration (blocks): 1440 (approximately 48 hours)

Snapshots taken per cycle: 10
{% endhint %}

## [Block Reward - 0xf8aBA2c68A1F7d128B4744FcbB95F6ED8b1DdDAd](https://alltra.global/address/0xf8aBA2c68A1F7d128B4744FcbB95F6ED8b1DdDAd)

This contract is responsible for generating and distributing block rewards to the network validators according to the network's specifications (5% yearly inflation).

Another role of this contract is to call the snapshot/cycle logic on the Consensus contract.

This contract is based on the `BlockReward` as [described in the Parity Wiki](https://wiki.parity.io/Block-Reward-Contract).

## [Voting - 0xA6aa8cd17cE39568c0D2af8F977069088083edb0](https://alltra.global/address/0xA6aa8cd17cE39568c0D2af8F977069088083edb0)

This contract handles the opening of new ballots and voting to accept or reject them. Ballots are essentially proposals to change the implementation of other network contracts.

Only network validators can open new ballots. While everyone can vote on them, only the votes of validators count when the ballot is closed.

Ballots are opened and closed at the end of a cycle.

{% hint style="info" %}
Max number of open ballots: 100

Max number of open ballots per validator: 100 / number of validators

Minimum ballot duration (cycles): 2

Maximum ballot duration (cycles): 14
{% endhint %}

## [Proxy Storage](https://alltra.global/address/0x23D8634ED1B2662dC96FcE6208fde93258731333)

This contract is responsible for holding the implementation addresses of network contracts and upgrading them if necessary (via voting).

I am always at your service. May fortune favor you.

***THANK YOU AND HAPPY TRAVELS***

***ALLTRA***
