# ETHBegProj
This is a Solidity Program that simulates the minting and burning of tokens. The purpose of this project is to demonstrate my current knowledge of the programming language, and to further enhance in the future.

# Description
This program mints and burns a singular token, using variable and functions from the Solidity programming language. For the mint function, it adds value to the token, while the burn functions reduces the value of the token. A conditional statement is also added to the burn function so that the token has sufficient value.

# Getting Started
# Executing Program
To run this program, you have to use the online Remix IDE, which accepts and compiles Solidity code. 
Here is the website address as well as the code used for this project:

Remix IDE Website: https://remix.ethereum.org/

Program Code:
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
    string public tokenName = "Ultima";
    string public tokenAbbreviation = "ult";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balance;

    // mint function
    function mintToken(address _address, uint _value) public{
        totalSupply += _value;
        balance[_address] += _value;
    }

    // burn function
    function burnToken(address _address, uint _value) public{
        
        //If statement to make sure that the provided address's balance is sufficient before burning token
        if(balance[_address] >= _value){
            totalSupply -= _value;
            balance[_address] -= _value;
        }
    }
}
```
