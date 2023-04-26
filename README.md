Bank Contract and Attacker Contract Tests
This is a test suite for the Bank contract and the Attacker contract. The tests are written using the Chai Assertion Library and the Hardhat framework for Ethereum development.

Installation
To install the dependencies required for the tests, run:

sh
Copy code
npm install chai hardhat @nomiclabs/hardhat-ethers ethers
Usage
To run the tests, run:

sh
Copy code
npx hardhat test
This will execute all the tests in the suite.

Test Descriptions
The test suite consists of three tests that cover the deposit and withdrawal functionalities of the Bank contract, as well as the attacker's ability to drain funds from the contract through a vulnerability.

Test 1: Should accept deposits
This test checks whether the Bank contract accepts deposits. The deployer and user accounts deposit 100 and 50 ether respectively into the contract, and the test confirms that the balance of the contract matches the sum of the deposits.

Test 2: Should accept withdrawals
This test checks whether the Bank contract accepts withdrawals. The deployer account withdraws all the ether from the contract, and the test confirms that the deployer's balance is updated accordingly while the user's balance remains unchanged.

Test 3: Allows attacker to drain funds from #withdraw()
This test exploits a vulnerability in the Bank contract that allows an attacker to drain all the funds from the contract. The Attacker contract is deployed and given the address of the Bank contract as an argument. The attacker then invokes a function in the Attacker contract that transfers 10 ether to the Bank contract, triggering the vulnerability. The test confirms that the Bank contract balance is zeroed out, indicating a successful attack.
