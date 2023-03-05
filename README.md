# ETH Denver 2023 - Mercury Protocol

In this hackathon submission, we implemented data DAOs on top of the Filecoin Virtual Machine, and a front-end that makes it more convenient for data buyers to create buy orders on the Mercury Protocol.

### Data DAOs on top of the FVM
Membership in a data DAO is gated by soulbound token ownership. The admins mint the tokens, and by doing so they grant access to the DAO. The DAO members can create data deals in the contract on Filecoin, plus they can record in the contract the deal IDs and CIDs of their data stored on filecoin. By doing so they contribute their data to the offering of the DAO.

In this project we implemented the recording and monetization of sequenced genomic data.
- The encrypted data is stored on Filecoin
- The Mercury smart contracts are deployed on top of the FVM
- The DAO interacts directly with the Mercury Protocol and the data stored on Filecoin

Once the deal is finalized and the machine learning model training on the data is complete, the payment for the data can be withdrawn from the Mercury Protocol into the DAO smart contract. The DAO admins can distribute all the money in the contract evenly between all DAO members.

### Data buyer front-end
We implemented a simple and intuitive front-end interface that makes it easy for data buyers to create buy orders on the Mercury Protocol. We use Cypher Wallet to let our app configure the necessary tokens to have before connecting to the user to the app. We use Wallet Connect to let our users connect to any wallet regardless of which chain they are using (Ethereum or Filecoin Virtual Machine).

### Intel SGX Attestation Verification on-chain on Scroll L2
In our original architecture for the Mercury Protocol, we used Starknet and Cairo for the layer-2 verification of Intel Attestation Reports. Cairo is a very young and sometimes troublesome language, so we were happy to discover and try out Scroll, where we can use Solidity. So for this hackathon we rewrote our Cairo contracts in Solidity, and deployed them on Scroll L2.