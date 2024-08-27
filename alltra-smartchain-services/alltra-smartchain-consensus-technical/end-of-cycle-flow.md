---
description: >-
  This document describes the End-of-Cycle flow that completes the cycle, handles rewards, and enforces consensus within the Alltra ecosystem.
---

# End-of-Cycle Flow

Greetings, traveller,

I am ***ALLTRA***, your ***A***dvanced ***L***ogistics and ***L***ife-support ***T***echnology ***R***esource ***A***ssistant.  

***Here is a helpful key for the following documention.***  
[Alltra Smartchain](https://alltra.global) - Will take you to the Alltra Smartchain Explorer  
[(ALL coins)](https://www.alltraverse.com/express-checkout) - Will take you to the Alltra Smartchain Express chekcout to purchse ALL coin within a minute.  

### Overview

1. The `BlockReward.reward` function is called every block. When the cycle ends, it calls the `Consensus.cycle`.
2. The `Consensus.cycle` function is responsible for several actions, including:
   1. Setting the boolean `Consensus.ShouldEmitInitiateChange` to `true`.
   2. Calling `BlockReward.onCycleEnd`, which sets the boolean `BlockReward.shouldEmitRewardedOnCycle` to `true` as well.
3. The `alltra-smartchain-validator-app` (located in the `alltrasmartcahinapp` container on validator VMs) checks the values of these two booleans. When both are `true`, it triggers the following two functions (via separate transactions):
   1. `Consensus.emitInitiateChange`
   2. `BlockReward.emitRewardedOnCycle`

Only one validator can successfully make these calls. The first validator to do so will succeed, and all others will fail. However, since these are 0-gas transactions, the failure of subsequent validators is not an issue. The validator next in line to validate a block is the one that successfully makes these calls.

### Emitted Events

1. The above calls emit the following events:
   1. `Consensus.InitiateChange`
   2. `BlockReward.RewardedOnCycle`
2. The bridge oracles, `alltraoracle-initiate-change` and `alltraoracle-rewarded-on-cycle`, are responsible for listening to these events.
3. These oracles run on all validators and call `submitSignature` on the `HomeBridgeNativeToErc` contract in the [Alltra Smartchain](https://alltra.global) network. Each validator submits a signature for each of the events.
4. Once a majority of validators have submitted their signatures, an event `CollectedSignatures` is emitted by the home bridge (one event for each of the previous events).
5. The bridge oracle `alltraoracle-collected-signatures` listens for the `CollectedSignatures` event. The validator responsible for transmitting the transaction to [ALL mainnet](https://alltra.global) is the last one to submit a signature in this cycle. Its address is included in the event details, so other validator oracles know it’s not their turn and will skip the event. If a validator is down, out of funds, or facing connectivity issues, the next one in line (as per the `ValidatorSet`) takes responsibility for transmitting to ALL mainnet.
6. On [ALL mainnet](https://alltra.global), we should see two transactions to the `ForeignBridgeNativeToErc` each cycle:
   1. One updating the new validators.
   2. One minting the ALL coins created during this cycle on [Alltra Smartchain](https://alltra.global).

### Important Notes

If the new validator set transaction fails on [ALL mainnet](https://alltra.global), there’s a chance the minting will fail as well. This is because the process checks if all signatures are valid before transmission. A situation could arise where new validators submit their signatures on Alltra Smartchain’s end-of-cycle transactions, but aren’t updated on ALL mainnet due to the failure of the initial transactions. In this case, the second transaction may contain “invalid” signatures from the perspective of ALL mainnet.

### Example of a Successful Flow (from 7/6/2020)

1. `Consensus.emitInitiateChange` transaction on [Alltra Smartchain](https://alltra.global) - [View Transaction](https://alltra.global/tx/0x441e2cb5f4aa20948c51020ebd8f7fba7c33cf909e31c66d0aff4a11e79ce13d)
2. `BlockReward.emitRewardedOnCycle` transaction on [Alltra Smartchain](https://alltra.global) - [View Transaction](https://alltra.global/tx/0x34cf4ddfc8afa6154e8c0d5f1de3b7d756b1b0517e8f0efd5794bde40983ba64)
3. Successful validators update transaction on [Ethereum mainnet](https://etherscan.io) - [View Transaction](https://etherscan.io/tx/0xf43b2abebd64537dbd7d834c9ac7a42ce8a925da5cb5278002ce0687187c8882)
4. Successful Alltra Smartchain minting transaction on [Ethereum mainnet](https://etherscan.io) - [View Transaction](https://etherscan.io/tx/0x2bd70ecbff6e84c18306701eb380e558a7340fab61aadf1af7690021aeeef5ce)

---
  
I am always at your service.  
May fortune favor you.  
  
***THANK YOU AND HAPPY TRAVELS***  
  
***ALLTRA***
