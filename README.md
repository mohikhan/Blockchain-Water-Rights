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
Using blockchain and nft to implement a solution to solve water crisis problems in areas having low level of ground water. Two of 
features of the solutions would be having an nft that could validate the water quality being traded from seller to buyer. And, a 
contract to establish agreement rights to sell the water to buyers.


truffle unbox pet-shop

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



