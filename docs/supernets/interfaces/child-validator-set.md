---
id: child-validator-set
title: ChildValidatorSet
sidebar_label: ChildValidatorSet
description: "Validator set genesis contract for Polygon PoS v3. This contract serves the purpose of storing stakes."
keywords:
  - docs
  - polygon
  - pos
  - module
  - child-validator-set
---

## Overview

`IChildValidatorSetBase` is an interface that provides a standardized way for developers to interact with the ChildValidatorSet contract in the Polygon PoS v3. The ChildValidatorSet contract stores validator stakes, manages staking, epoch committing, and reward distribution.

## Structs

The following structs are used in the ChildValidatorSet contract:

### `Epoch`

Struct containing data for an epoch.

*```solidity
struct Epoch {
    bytes32 epochRoot;
    uint256 startBlock;
    uint256 endBlock;
    uint256 totalStake;
    uint256[2] nextValidatorSet;
    uint256[2] validators;
    uint256 fee;
    uint256[2] parentAggSig;
    uint256[2][] sigs;
    bytes32 blockHash;
}
*```

### `Uptime`

Struct containing uptime data for an epoch.

*```solidity
struct Uptime {
    bytes bitmap;
    uint256 startBlock;
    uint256 endBlock;
}
*```

### `DoubleSignerSlashingInput`

Struct containing information about a double signer to be slashed.

*```solidity
struct DoubleSignerSlashingInput {
    uint256 epochId;
    bytes32 eventRoot;
    bytes32 currentValidatorSetHash;
    bytes32 nextValidatorSetHash;
    bytes32 blockHash;
    bytes bitmap;
    bytes signature;
}
*```

## Functions

The following functions are provided by the `IChildValidatorSetBase` interface:

### `commitEpoch`

Allows the v3 client to commit epochs to the ChildValidatorSet contract.

*```solidity
function commitEpoch(uint256 id, Epoch calldata epoch, Uptime calldata uptime) external;
*```

### `commitEpochWithDoubleSignerSlashing`

Allows the v3 client to commit epoch and slash double signers.

*```solidity
function commitEpochWithDoubleSignerSlashing(
    uint256 curEpochId,
    uint256 blockNumber,
    uint256 pbftRound,
    Epoch calldata epoch,
    Uptime calldata uptime,
    DoubleSignerSlashingInput[] calldata inputs
) external;
*```

### `getCurrentValidatorSet`

Gets addresses of active validators in this epoch, sorted by total stake (self-stake + delegation).

*```solidity
function getCurrentValidatorSet() external view returns (address[] memory);
*```

### `getEpochByBlock`

Look up an epoch by block number. Searches in O(log n) time.

*```solidity
function getEpochByBlock(uint256 blockNumber) external view returns (Epoch memory);
*```

### `totalActiveStake`

Calculates total stake of active validators (self-stake + delegation).

*```solidity
function totalActiveStake() external view returns (uint256);
*```

## Events

The following events are emitted by the ChildValidatorSet contract:

### `NewEpoch`

Emitted when a new epoch is committed.

*```solidity
event NewEpoch(uint256 indexed id, uint256 indexed startBlock, uint256 indexed endBlock, bytes32 epochRoot);
*```

### `DoubleSignerSlashed`

Emitted when a double signer is slashed.

*```solidity
event DoubleSignerSlashed
