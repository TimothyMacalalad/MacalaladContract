# MacalaladContract.sol 

# Description

The MemberRegistry contract allows users to register and unregister as members. It keeps track of the registered members and their addresses.

# Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:
remix.ethereum.org

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MemberRegistry {
    mapping(address => bool) public members;
    address[] public memberAddresses;

    event MemberRegistered(address indexed member);
    event MemberUnregistered(address indexed member);

    function register() public {
        require(!members[msg.sender], "Member already registered");
        
        members[msg.sender] = true;
        memberAddresses.push(msg.sender);
        
        emit MemberRegistered(msg.sender);
    }

## Authors

Metacrafter Timothy

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
