#ETH PROOF: Beginner Assignment 
This Soliditary Program involves creating a smart contract for a token. This contract will manage basic functionalities such as minting new tokens, burning existing tokens, and maintaining the balances of token holders.

## Description
This Program involves creating a smart contract for a token using Solidity on the Ethereum blockchain. The contract includes public variables for the token's name, abbreviation, and total supply. It features a mapping to track the balance of each address. The mint function allows for the creation of new tokens, increasing the total supply and the recipient's balance. The burn function, with safeguards to ensure sufficient balance, reduces the total supply and the address's balance. 

## Getting Started

### Installing
No Installation Needed, Just needs a Web-Browser.

### Executing program
1. Use Remix, an online Solidity IDE to run this Program.
   https://remix.ethereum.org/
2. On the Remix website, create a new file by clicking on the "+" icon in the left sidebar. 
   Save the file with a .sol extension. Copy and paste the following code into the file, then Compile and 
   Deploy.

// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to accounts (address => uint)
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
    string  public token = "APE Coin";
    string public tokenSymbol  = "APEC";
    uint public totalSupply = 3000;

    // mapping variable here
    mapping (address => uint) public balance;

    // mint function
    function mintToken(address _address ,uint _value ) public {
      totalSupply += _value;
      balance[_address] += _value;          
    }

    // burn function
    function burnToken(address _address ,uint _value ) public  {
      if(balance[_address]>=_value){
        totalSupply -= _value;
        balance[_address] -= _value;
      }       
    }
}

Steps to Compile and Deploy:
1. Go to Remix IDE in your web browser.
2. In the file explorer on the left-hand sidebar, click the "+" icon to create a new file.
   Name the file MyToken.sol.
3. Copy and paste the above Solidity code into MyToken.sol.
4. Click on the "Solidity Compiler" tab in the left-hand sidebar, then Click on the "Compile MyToken.sol" 
   button.
5. Click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
6. Select the "MyToken" contract from the "Contract" dropdown menu then Click on the "Deploy" button.
7. After deployment, the deployed contract will appear at the bottom of the "Deploy & Run Transactions" tab, 
   Expand the "MyToken" contract.
8. To mint tokens, locate the mintToken function in the deployed contract, Input the address and the value to 
   mint, then click "transact".
9. To burn tokens, locate the burnToken function in the deployed contract, Input the address and the value to 
   burn, then click "transact".



## Authors
Kamal Mehta
itskamalmehta@gmail.com




## License

This project is licensed under the MIT License - see the LICENSE.md file for details
