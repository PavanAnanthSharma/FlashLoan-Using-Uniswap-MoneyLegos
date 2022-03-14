## Flashloan Example using Money Legos      
  
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In this example we will use the [Money Legos Library](https://money-legos.studydefi.com/#/) to create a flashloan and arbitrage accross several DEXs.
 
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Test Uniswap Exchanges

This example uses a couple of exchanges set up and maintained by @robsjr and @ggviana. The are forks of Uniswap and published on the Kovan network to help test arbitrage smart contracts like this one. The two exchanges are:

* [Uniswap Exchange A](https://kovan-uniswap.netlify.app/swap)  
* [Uniswap Exchange A](https://kovan-uniswap2.netlify.app/swap) 

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Usage

Below are high level instructions to try out this example using the **Kovan Testnet**.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Setup

Rename env to '.env' and complete the missing values for your project.

Connect your truffle console to the Kovan network like so:

```
truffle console --network kovan
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Compile / Deploy

Compile and deploy the contract to the Kovan network. From within your truffle console instance do the following:

```
compile
migrate --reset
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Interact via Truffle Console

Interact with the contract via the truffle console:

```
let f = await FlashloanMoneyLego.deployed()
let assetToFlashLoan = '0xFf795577d9AC8bD7D90Ee22b6C1703490b6512FD' // DAI
let amountToLoan = web3.utils.toWei('1') // 1 'unit' of the 'assetToFlashLoan' (DAI)
Object.keys(f)
f.addressesProvider()
f.initateFlashLoan(assetToFlashLoan, amountToLoan)
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Interact via Typescript app

There is a Typescript file that runs the same above arbitrage. This can be run as folllows.

Install Typescript and `ts-node`

```
npm install -g typescript
npm install -g ts-node
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Now run the script as follows:

```
ts-node src/execFlashloanMoneyLego.ts
```
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Verify

Confirm the transaction output in [Kovan Etherscan]

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
