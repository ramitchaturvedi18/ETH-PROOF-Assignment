# ETH-PROOF-Assignment
The purpose of the 'MyToken' smart contract is to show the features of a  cryptocurrency token on the Ethereum network. Users can keep track of balances, burn existing tokens, and mint new tokens.

# Description
A simple token named "Ramit Chaturvedi"—abbreviated "Ra_Ch"—is defined under the MyToken smart contract. The contract has features that allow tokens to be burned from any address, lowering the total supply, and minted new tokens to any address, increasing the total supply. The involved addresses' balances are updated by each token transaction and are kept in a publicly accessible mapping. This project is a great way to understand the fundamentals of token operations and smart contract development.

# Getting Started
# Installing
No installation needed

# Executing Programm
How to run the programm
1) Open Remix
2) Compile
3) Deploy

Contract
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public TokenName = "Ramit Chaturvedi";
    string public TokenAbr = "Ra_Ch";
    uint public TokenSupply=0; 

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint_Tokens(address _address, uint _value) public{
        TokenSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn_Tokens(address _address, uint _value) public{
        if(balances[_address]>= _value){
            TokenSupply -= _value;
            balances[_address] -= _value;
        }
       
    }
}
```

# 

