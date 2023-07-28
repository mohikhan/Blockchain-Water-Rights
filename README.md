# Blockchain-Water-Rights
We have implemented a blockchain based solution to address water scarcity problem.
In that there will be a water distributor that will be selling water through blockchain. In
current situation, water is being distributed by government bodies or private
organizations. The buyer does not have the enough information about the water quality
and authenticity of the distributor. Using the blockchain solution, buyers can view all
the information pertaining to the water quality offered by the distributor and whether
the distributor is authorized to sell the water. Our blockchain based solution prevents
misinformation or tampering of records about water quality and approvers.
Our smart contract has three user groups: voters, buyers and seller.
Seller is the owner of the smart contract and is responsible for registering voters. Smart
contract function used for registering voters is register Once voters are registered by
seller, each voter can approve or reject the water license by casting vote. Each voter
has a weight assigned, once the total number of votes approved equals 3, the license
will get automatically approved and buyers can start purchasing water.

# URL of website: https://cse526blockchain-water-license.web.app/

# Running Instructions:

Steps for Deployment to local test chain Ganache:
1. Change directory to ‘Water-License-Contract’
2. Connect to ganache and import all the accounts using menomics:
LITERATE-BOTTLE
arrive insect wedding cactus rebel agent pink main build sibling become design
INrr20221104!
3. nvm use v18: to use truffle to migrate smart contract or use node version less
than or equal to 18 if nvm is not installed
4. npm install: to install openzeppelin packages
5. truffle migrate –reset
6. If the contract is not able to connect to ganache: 127.0.0.1:7545, restart the
workspace once and repeat step 5
7. Copy WaterLicense.json file from Water-License-Contract/build/contracts to
Water-License-App/src
8. Change directory to ‘Water-License-App’
9. npm install
10. npm start




Deployment to Sepolia and firebase
We have deployed our Smart Contract to Sepolia test network and Dapp/front-end to
Firebase
Deployment steps:
Deployment on Infura:
1. Create an account on infura
2. Create an .env file with following information in Water-License-Contract folder:
MNEMONIC=add approve fold pole lab dish typical rail open promote drastic joy
PROJECT_ID=c2cc5b9ee76b478e8c1627d2d00b10df
3. Edit truffle-config.js file to include below:
require('dotenv').config();
const { MNEMONIC, PROJECT_ID } = process.env;
const HDWalletProvider = require('@truffle/hdwallet-provider');
sepolia: {
provider: () => new HDWalletProvider(MNEMONIC,
`https://sepolia.infura.io/v3/${PROJECT_ID}`),
 network_id: 11155111, // Sepolia's id
confirmations: 2, // # of confirmations to wait between deployments.
(default: 0)
timeoutBlocks: 200, // # of blocks before a deployment times out
(minimum/default: 50)
skipDryRun: true // Skip dry run before migrations? (default: false for public
nets )
 },
4. Modify Water-License-App/src/app.js file to include below in initializeContract
function:
const web3 = new
Web3("https://sepolia.infura.io/v3/c2cc5b9ee76b478e8c1627d2d00b10df");
5. Comment below in initializeContract function:
//const web3 = new Web3("HTTP://127.0.0.1:7545");
6. Run “npm install” in Water-License-Contract folder
7. Run “truffle compile” in Water-License-Contract folder
8. Run “truffle migrate --network sepolia” in Water-License-Contract folder



Deployment to Firebase:
1. Run “firebase login” in Water-License-App folder
2. Copy waterLicense.json from Water-License-Contract/build/contracts folder to
Water-License-App/src folder
3. Run “npm install” in Water-License-App folder
4. Run “npm run build” in Water-License-App folder
5. Run “firebase init” in Water-License-App folder
   Select hosting: Configure files for Firebase Hosting
   Select “use an existing project”
   Select the project
   Type “build”
   Type “y”
 Type “N”
6. Change firebase.json file in in Water-License-App folder
{
 "hosting": {
 "public": "build",
 "site": "cse526blockchain-water-license",
 "ignore": [
 "firebase.json",
 "**/.*",
 "**/node_modules/**"
 ]
 }
}
7. Run “firebase deploy” in Water-License-App folder
8. Deployed website URL: https://cse526blockchain-water-license.web.app


