# ETHProofBeginnerProject

This is a Solidity program that simulates the minting and burning of tokens. The purpose of this program is showcase my current understanding of Solidity as a programming language as well as serve as a referrence to those who are also new to Solidity like me. 

## Description

This program is a contract written in Solidity, an object-orientted programming language typically used for developing smart contracts on various blockchain platforms such as ethereum. The contract mints tokens using the mintToken function which accepts an address and a value as parameters. This will then increase the balance of the provided address as well as increase the total supply by updating the totalSupply state variable. This project also burns tokens using the burnToken function which accepts an address and a value as parameters. However unlike the mintToken function, the burnToken function has a balance check on the address provided. If the balance of the address provided is greater than or equal to the amount of token to be burned then the burning of tokens will proceed otherwise nothing will happen but the transaction will be shown as completed. 

## Getting Started

### Executing program

In order to run this program, you can use Remix, an online Solidity IDE which I used to develop this contract. For starters, please go to the Remix website at https://remix.ethereum.org/.
Upon reaching the website, create a new file by clicking the "New File" button around the center of the website or the button that looks like a piece of paper with the top right corner folded found on the top left corner of the website under workspaces. Save the file under the file name of your choice while making sure to use the .sol extension (e.g. MyFirstProgram.sol). Copy and then paste the following code into the file you have just created:


```Solidity
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
    string public tokenName = "Banana";
    string public tokenAbbreviation = "BNN";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mintToken(address _address, uint _value) public{
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burnToken(address _address, uint _value) public{
        
        //If statement to make sure that the provided address's balance is sufficient before burning token
        if(balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}

```
In order to compile the code, click on the "Solidity compiler" tab found in the left-hand sidebar below the button that looks like a magnifying glass. Please make sure the "Compiler is set to "0.8.18" (or any other compatible version), and then click on the "Compile MyFirstProgram.sol" assuming you named your Solidity contract as such. Otherwise, the button will say "Compile " followed by the name of your Solidity contract. For simplicity's sake I will be referring to the contract you have made as "MyFirstProgram.sol" but it will appear on the Remix IDE as how you named the contract.

After the contract has been compiled, you can now deploy the contract by clicking on the "Deploy & run transactions" tab found in the left-hand sidebar below the "Solidity compiler" tab. Select the "MyFirstProgram.sol" contract or as how you have named it. After selecting the contract, click on the "Deploy" button.

After the contract has been deployed, the contract will be found under "Deployed Contracts". Expand it by clicking the ">" button below "Deployed Contracts". You should see the following buttons: "burnToken", "mintToken", "balances", "tokenAbbreviation", "tokenName", and "totalSupply". The "burnToken" and "mintTokem" buttons have input fields beside each button. These input fields accepts an address and a positive integer value as parameters/input strictly in that order. The aforementioned parameters/input are separated by a comma (e.g. 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4,1000). You can get an address by clicking the "Copy account to clipboard" button which looks like two pieces of paper stacked on the of each other with the upper right corner folded. This button is founnd below "Account" and beside the current selected Account/Address. After clicking the "Copy account to clipboard" button you can now paste it inside the input fields beside the following buttons: "burnToken", "mintToken", or "balances". The input field beside the "balances" button only accepts an address as parameter/input. 


You can interact with contract with the following actions:
1.) Clicking the "tokenName" button to view the name of the token.
2.) Clicking the "tokenAbbreviation" button to view the abbreviation of the token.
3.) Clicking the 


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
## Authors

Drennix Guerrero @ 201812805@fit.edu.ph

