
```
## Smart Contract
Write a smart contract that implements a voting system, with functions to
- add candidates, 
- start the voting process by admin,
- vote for a candidate, 
- end the voting process by admin,
- retrieve the number of votes for each candidate,
- retrieve the winning candidate.

Also write tests using ethers.js (or any other library of your choice) that verifies the following cases:
only the admin can start and end the voting process
once voting is done, it is reflected for the right candidate

## Frontend or Script
Create a basic frontend, which displays the candidates and the number of votes for each candidate, and allows users to vote. Connect the smart contract with the frontend using Ethers.js.
OR
Write a separate script with Ethers.js to interact with the smart contract functions.

```

## Setup the repo



Change to the project directory:
  ```bash
  cd Voting
  ```

Install the required dependencies using npm:
  ```bash
  npm install
  ```

To run the project's unit tests and ensure everything is functioning correctly, run the following:
  ```bash
  npx hardhat test
  ```

## Running a local hardhat node

Launch a local Ethereum node using Hardhat in a separate terminal:
```bash
npx hardhat node
```

This will start the local node, and you should see the creation of several test accounts with preloaded funds.

## Running the frontend

In a separate terminal, again `cd voting` and run:
```bash
npm start
```
This should print out something like this:
```
You can now view the application in the browser.

  Local:            http://localhost:3000
  On Your Network:  http://192.168.0.14:3000
```




## Voting system contract

The contract that handles the voting logic is located at `contracts/VotingSystem.sol`. This contract contains the necessary information required to implement the voting process:

 - It keeps track of the state of the voting process using `started/finished` flags.
 - The contract maintains a mapping called `candidateVotes` to track the votes received by each candidate.
 - To ensure that each voter can only vote once, the contract keeps a record of `voters`.
 - The contract efficiently recomputes and stores the winner on every vote using `winnerVotes` and `winner` variables.
 - Additionally, the `candidates` are stored separately to facilitate visualization since it is not possible to iterate through the keys of the `candidateVotes` mapping in Solidity.

The voting logic implemented in the contract is straightforward and easy to understand.



# Misc HOW-TOs
## Basic hardhat commands

### Run hardhat node
```
npx hardhat node
```
### Deploy the contract
```
npx hardhat run scripts/deploy.js --network localhost
```
### Run the frontend
```
npm start
```
Runs the app in the development mode.
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.
You may also see any lint errors in the console.

## How to set the repo from scratch
```
npm init
npm install --save-dev hardhat
npx hardhat
```
This will install all npm and hardhat configs. But if you're checking out this repo you should only run:
```
npm install
```
## Create frontend
How to add a frontend from scratch
```
npx create-react-app frontend
cd frontend

npm install --save-dev @nomiclabs/hardhat-waffle ethereum-waffle chai @nomiclabs/hardhat-ethers ethers

npm install @ethersproject/providers @openzeppelin/contracts
```
