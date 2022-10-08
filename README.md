# Supply chain & data auditing

This repository containts an Ethereum DApp that demonstrates a Supply Chain flow between a Seller and Buyer. The user story is similar to any commonly used supply chain process. A Seller can add items to the inventory system stored in the blockchain. A Buyer can purchase such items from the inventory system. Additionally a Seller can mark an item as Shipped, and similarly a Buyer can mark an item as Received.

The DApp User Interface when running should look like...

![truffle test](images/ftc_product_overview.png)

![truffle test](images/ftc_farm_details.png)

![truffle test](images/ftc_product_details.png)

![truffle test](images/ftc_transaction_history.png)


## Project Aim

This project helps farmers, retailers, distributors, and consumers handling the supply chain of coffee. By tracking the origin of the products from the farm to the consumer.

## UML

![Activity Diagram](images/UML/FairTrade_Activity%20-%20Flowchart%20with%20swimlanes.png)
![Sequence Diagram](images/UML/Fair%20Trade%20Coffee_%20Sequence.png)
![State Diagram](images/UML/Coffee%20State%20Diagram.png)
![Class Diagram](images/UML/Fair%20Trade_%20Class%20Diagram.png)


### Prerequisites and libraries

Please make sure you've already installed ganache-cli, Truffle and enabled MetaMask extension in your browser.

The project is built using:

```
nodejs v16.14.2
Truffle v4.1.14 (core: 4.1.14)
Solidity v0.4.24 (solc-js)
```

Change directory to ```project-6``` folder and install all requisite npm packages (as listed in ```package.json```):

```
cd project-6
nvm use 16.14.2
npm install
```

Launch Ganache:

```
ganache-cli -m "spirit supply whale amount human item harsh scare congress discover talent hamster"
```

Your terminal should look something like this:

![truffle test](images/ganache-cli.png)

In a separate terminal window, Compile smart contracts:

```
truffle compile
```

Your terminal should look something like this:

![truffle test](images/truffle_compile.png)

This will create the smart contract artifacts in folder ```build\contracts```.

Migrate smart contracts to the locally running blockchain, ganache-cli:

```
truffle migrate
```

Your terminal should look something like this:

![truffle test](images/truffle_migrate.png)

Test smart contracts:

```
truffle test
```

All 10 tests should pass.

![truffle test](images/truffle_test.png)

In a separate terminal window, launch the DApp:

```
npm run dev
```

## Dotenv

To store safely the wallet mnemonic and infura key add a `.env` file to `project-6` dir:

It should look like

```
INFURA_KEY = '<key from infura>'
MNEMONIC = '<wallet mneomic from metamask>'
```

## Metamask setup

Note that the owner address that deploys the contract will have all the various roles
(Farmer, Distributor etc) owing to the fact that in the role constructors we have

```  
constructor() public {
     _addConsumer(msg.sender);
  }
```

for this reason it should be the same address you use in Metamask for testing 
(the first in the ganache-cli output...import the private key to metamask)


## Built With

* [Ethereum](https://www.ethereum.org/) - Ethereum is a decentralized platform that runs smart contracts
* [IPFS](https://ipfs.io/) - IPFS is the Distributed Web | A peer-to-peer hypermedia protocol
to make the web faster, safer, and more open.
* [Truffle Framework](http://truffleframework.com/) - Truffle is the most popular development framework for Ethereum with a mission to make your life a whole lot easier.


## Authors

See also the list of [contributors](https://github.com/your/project/contributors.md) who participated in this project.

## Acknowledgments

* Solidity
* Ganache-cli
* Truffle
* IPFS
