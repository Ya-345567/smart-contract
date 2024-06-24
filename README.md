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
