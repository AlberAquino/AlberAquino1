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

contract Alber  {

    address public minter;
    mapping (address    =>  uint)   public balances;



    event   Sent(address    from,   address to, uint    amount);



    constructor()   {
        minter  =   msg.sender;

    }

    function mint(address receiver,uint amount) public {
        require(msg.sender  ==  minter   ,'Only owner can do it' );
        balances[receiver]  +=  amount;

    }

    error InsufficientBalance(uint requested,   uint    available);

    function send(address receiver,uint amount)public { 
            if(amount > balances[msg.sender])
           revert InsufficientBalance({
            requested:  amount,
            available:  balances[msg.sender]
           });
           
        balances[msg.sender] -= amount;
        balances[receiver] += amount;
        emit Sent(msg.sender, receiver, amount);

    }
}
```




# Authors



. Alber C Aquino  
. https://www.facebook.com/DBGTK


## License

This project is licensed under the [SPDX-MIT] License - see the LICENSE.md file for details
