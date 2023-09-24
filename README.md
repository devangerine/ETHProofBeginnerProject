# ETHProofBeginnerProject

The purpose of this project is to simulate minting and burning of tokens. 

## Description

This project mints tokens using the mintToken function which accepts an address and a value as parameters. This will then increase the balance of the provided address as well as increase the total supply by updating the totalSupply state variable. This project also burns tokens using the burnToken function which accepts an address and a value as parameters. However unlike the mintToken function, the burnToken function has a balance check on the address provided. If the balance of the address provided is greater than or equal to the amount of token to be burned then the burning of tokens will proceed otherwise nothing will happen but the transaction will be shown as completed. 


## Authors

Drennix Guerrero @ 201812805@fit.edu.ph

