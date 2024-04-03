## Flashloan Arbitrage Example using Money Legos

---

### Introduction

This example demonstrates how to utilize the [Money Legos Library](https://money-legos.studydefi.com/#/) to execute a flashloan and perform arbitrage across multiple decentralized exchanges (DEXs).

---

### Test Uniswap Exchanges

To facilitate testing of arbitrage smart contracts, this example utilizes two Uniswap exchanges deployed on the Kovan network. These exchanges, maintained by @robsjr and @ggviana, serve as reliable testing grounds. The exchanges are:

* [Uniswap Exchange A](https://kovan-uniswap.netlify.app/swap)
* [Uniswap Exchange B](https://kovan-uniswap2.netlify.app/swap)

---

### Usage

Below are step-by-step instructions to replicate this example on the **Kovan Testnet**.

---

### Setup

1. Rename the 'env' file to '.env' and fill in the required values for your project.

2. Connect your Truffle console to the Kovan network:
   ```
   truffle console --network kovan
   ```

---

### Compile and Deploy

Compile and deploy the smart contract to the Kovan network:

```
compile
migrate --reset
```

---

### Interact via Truffle Console

Interact with the deployed contract using the Truffle console:

```javascript
let f = await FlashloanMoneyLego.deployed()
let assetToFlashLoan = '0xFf795577d9AC8bD7D90Ee22b6C1703490b6512FD' // DAI
let amountToLoan = web3.utils.toWei('1') // 1 unit of the assetToFlashLoan (DAI)
Object.keys(f)
f.addressesProvider()
f.initateFlashLoan(assetToFlashLoan, amountToLoan)
```

---

### Interact via Typescript App

A Typescript file is provided to execute the same arbitrage logic:

Install Typescript and `ts-node`:

```
npm install -g typescript
npm install -g ts-node
```

Run the script:

```
ts-node src/execFlashloanMoneyLego.ts
```

---

### Verification

Verify the transaction output on [Kovan Etherscan].

---
