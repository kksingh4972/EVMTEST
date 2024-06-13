# EVMTEST
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables to store the details about the coin
    string public tokenName = "BETA";
    string public tokenAbbrv = "BTA";
    uint public totalSupply = 0;

    // Mapping of addresses to balances
    mapping(address => uint) public balances;

    // Mint function to increase total supply and balance of the sender
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function to decrease total supply and balance of the sender
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Balance is too low to burn.");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
