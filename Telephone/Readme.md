********************* Problem Statement ********************
Claim ownership of the contract below to complete this level.

  Things that might help

See the Help page above, section "Beyond the console"

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Telephone {

  address public owner;

  constructor() {
    owner = msg.sender;
  }

  function changeOwner(address _owner) public {
    if (tx.origin != msg.sender) {
      owner = _owner;
    }
  }
}

```

****************** solutions is present is solidity file *******

Note :
1. To understand the solution we need to first understand difference between 
    tx.origin and msg.sender.
2. We need to create and Attack contract and import this contract on that contract.
3. Now claim the ownership from attak contract.