# Fomo3D Contract

## Overview
Fomo3D is a decentralized application (DApp) implemented as a Solidity smart contract. It is a game that operates on the Ethereum blockchain and involves users betting Ether to participate in a round with the hope of winning the pot.

## Contract Details
- **Solidity Version:** ^0.8.0
- **Current State:** INACTIVE
- **Contract State:**
  - INACTIVE: Initial state where the contract is not yet active.
  - ACTIVE: State when the contract is actively running a round.
- **House Fee:** 2%
- **Key Price:** Initially set at 1 Ether, increases over time.
- **Round Duration:** Each round lasts for 30 seconds.
- **Hard End:** 24 hours after the start of each round.

## Contract Functions
- `kickStart()`: Transition the contract from INACTIVE to ACTIVE state and start a new round.
- `bet()`: Allows users to bet by sending Ether to the contract. If the round's end time is reached, or the hard end time is exceeded, the function distributes the pot and starts a new round.
- `getKeyPrice()`: Returns the current price of a key based on the elapsed time since the start of the round.
- `_distribute()`: Internal function to distribute the pot to the winners and the house.
- `_createRound()`: Internal function to reset the state for a new round.

## Usage
1. Deploy the contract to the Ethereum blockchain.
2. Call `kickStart()` to start the game and transition to the ACTIVE state.
3. Users can then call `bet()` to participate in the round by sending Ether.
4. After each round ends, winners are determined, and the pot is distributed.
5. The contract automatically starts a new round after distribution.

## Modifiers
- `inState(State state)`: Ensures that a function can only be called when the contract is in the specified state.

