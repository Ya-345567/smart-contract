#Project Title
YashToken Smart Contract

#Simple overview of use/purpose
A simple smart contract for issuing and destroying custom tokens on the Ethereum blockchain.

#Description
The YashToken smart contract is a basic implementation written in Solidity for the Ethereum blockchain. It allows for the creation, distribution, and destruction of a custom token named "Yash" with the symbol "YA". This contract is ideal for learning purposes, demonstrations, or small-scale projects requiring a token system. It features functions to issue new tokens to specific addresses and destroy tokens from holders, maintaining an accurate total supply. This project demonstrates the foundational concepts of token management on a blockchain.

#Getting Started
Installing
Clone the repository

 code:
git clone https://github.com/Ya-345567/YashToken.git
Navigate to the project directory

code:
cd YashToken
Ensure you have the required dependencies

*Solidity compiler (solc)
*Ethereum client (such as Ganache for local testing)

#Executing program
Compile the contract

 code:
solc --optimize --bin --abi YashToken.sol -o build
Deploy the contract

You can use Remix IDE .

Use a tool like Remix IDE  to call functions such as issueTokens and destroyTokens.
Step-by-step
Open Remix IDE
Load YashToken.sol file
Compile the contract
Deploy the contract using a JavaScript VM or connect to your Ethereum node
Use the deployed contract instance to call issueTokens and destroyTokens
Example commands:
javascript
 code:
// Issue tokens to an address
YashToken.issueTokens('0xAddress', 100);

// Destroy tokens from an address
YashToken.destroyTokens('0xAddress', 50);
Help
If you encounter any issues, ensure that:

You have the correct version of the Solidity compiler.
Your Ethereum client (like Ganache) is running and properly configured.
You are connected to the correct network (local, testnet, or mainnet).
For common problems or issues, refer to the Solidity and Ethereum documentation, or check community forums.

#Contributors names and contact info:
Yash 
@Ya-345567(GitHub)

#License
This project is licensed under the MIT License - see the LICENSE.md file for details.


CODE--------->

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract YashToken {
    string public name = "Yash"; 
    string public symbol = "YA";  

    uint256 public totalTokens = 0; 

    mapping(address => uint256) public tokenHoldings;

    function issueTokens(address recipient, uint256 amount) public {
        totalTokens += amount;
        tokenHoldings[recipient] += amount;
    }

    function destroyTokens(address holder, uint256 amount) public {
        require(tokenHoldings[holder] >= amount, "Insufficient token balance");
        totalTokens -= amount;
        tokenHoldings[holder] -= amount;
    }}
