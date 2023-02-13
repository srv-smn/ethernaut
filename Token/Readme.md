****************** Problem Statement ******************

The goal of this level is for you to hack the basic token contract below.

You are given 20 tokens to start with and you will beat the level if you somehow manage to get your hands on any additional tokens. Preferably a very large amount of tokens.

  Things that might help:

What is an odometer?

CONTRACT 

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.6.0;

contract Token {

  mapping(address => uint) balances;
  uint public totalSupply;

  constructor(uint _initialSupply) public {
    balances[msg.sender] = totalSupply = _initialSupply;
  }

  function transfer(address _to, uint _value) public returns (bool) {
    require(balances[msg.sender] - _value >= 0);
    balances[msg.sender] -= _value;
    balances[_to] += _value;
    return true;
  }

  function balanceOf(address _owner) public view returns (uint balance) {
    return balances[_owner];
  }
}

```


*********************** Solution ********************

1. To solve this problem you need know about underflow and overflow.
2. Initially you have balance of 20, You need to transfer any amount more than 20 
    to any address. Lets say you transfer 21.
3. This will create underflow and it will set your balance 255.
4. Congrats you Hacked !!!! the token you have more balance 😉.