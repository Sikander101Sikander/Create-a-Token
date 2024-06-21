# Create-a-Token

This project demonstrate that how the solidity functions, conditions and operations are work and understands the basics syntax of solidity.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a multiple function. This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension(for eg:-MyToken.sol).
```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;
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
    // Public variables for token details
    string public tokenName = "META";
    string public tokenAbbrev = "MTA";
    uint public totalSupply = 0;

    // Mapping to keep track of balances
    // uint representing the balance of tokens that address holds.
    mapping(address => uint) public balances;

    // Mint function to increase total supply and balance of a given address
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
        
    // Burn function to decrease total supply and balance of a given address
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "^0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you need to enter address and value mint, burn function and balance. And then transact and now we can see total supply and final output.

## Authors

Contributors names and contact info

Sikander Singh Nanglu

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
