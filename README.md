# Solidity Smart Contract: Understanding require(), assert(), and revert()

A basic Solidity smart contract that shows how to use the require(), assert(), and revert() statements can be found in this repository. In the creation of smart contracts, these assertions are crucial for managing special situations, verifying internal state, and imposing preconditions.

# Requirements

In order to communicate with the smart contract, you must:

An Ethereum smart contract development environment (such as Remix, Truffle, Hardhat)
An Ethereum wallet or client (e.g., MetaMask) to deploy and interact with the contract on a testnet or mainnet

## Getting Started

### Installing
To clone this repository locally, go to: https

Open the project directory by going to cd solidity-assertions.

In the Solidity development environment of your choice, open the RequireAssertRevert.sol file.

Put the smart contract together.

Install the smart contract on the Ethereum network of your choice (mainnet or testnet).

Use the supplied functions to communicate with the deployed contract, such as setNumber().


### Executing program


```
code blocks for commands
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

pragma solidity ^0.8.0;

contract Alber {
    address public owner;
    uint256 public value;
    uint256 public constant MAX_VALUE = 50000;

    constructor() {
        owner = msg.sender;
    }

    function increaseValue(uint256 _amount) external {
        require(msg.sender == owner, "Only the owner can increase the value");
        
        // Ensure that the new value doesn't exceed the maximum value
        uint256 newValue = value + _amount;
        require(newValue <= MAX_VALUE, "Value cannot exceed the maximum limit");
        
        value = newValue;
    }

    function decreaseValue(uint256 _amount) external {
        require(msg.sender == owner, "Only the owner can decrease the value");
        
        // Ensure that the value doesn't go below zero
        require(value >= _amount, "Value cannot be decreased below zero");
        
        value -= _amount;
    }

    function transferOwnership(address _newOwner) external {
        require(msg.sender == owner, "Only the owner can transfer ownership");
        require(_newOwner != address(0), "Invalid new owner address");
        
        owner = _newOwner;
    }
}
```




## Authors



. Alber C Aquino  
. https://www.facebook.com/DBGTK


## License

This project is licensed under the [SPDX-MIT] License - see the LICENSE.md file for details
