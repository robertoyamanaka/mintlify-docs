# Chipi SDK: The Fastest Way to Ship on StarkNet

Chipi SDK combines invisible wallet creation with social login and Avnu's gasless to streamline dApp development on StarkNet. Users log in with familiar accounts (Google, X, Meta), and a wallet is generated behind the scenes—no manual key management needed. Focus on building features instead of dealing with blockchain complexities.

## Features

- 🔐 **Invisible Wallet Creation**: Generate wallets automatically with social login
- 💸 **Gasless Transactions**: Integration with Avnu Gasless
- 🔄 **Simple Transfers**: Simplified API for token transfers
- ⚡ **Optimized for StarkNet**: Designed specifically for the StarkNet network

## Live Demo

https://chipi-sdk-clerk-demo.vercel.app/

## Installation

### Create an Org in the Dashboard

https://dashboard.chipipay.com/

### Bring your own Auth Provider

Next, head to https://dashboard.chipipay.com/configure and add your JWKS Endpoint from your Auth Provider. 

We will use this to verify the Bearer Tokens from your Auth Provider used in your frontend.

After adding the JWKS Endpoint, you will get a Public Key (pk_prod_xxxx). You will need this to initialize the SDK.

### Install the SDK

```bash
npm install @chipi-pay/chipi-sdk
```


## API

If you need to do something more customized, you can check our API

https://api.chipipay.com/v1

## Types

```typescript
interface ChipiSDKConfig {
  apiKey: string;
  rpcUrl: string;
  argentClassHash?: string;
  activateContractAddress?: string;
  activateContractEntryPoint?: string;
  network: "mainnet" | "sepolia";
}

interface WalletData {
  publicKey: string;
  encryptedPrivateKey: string;
}

interface TransferParams {
  encryptKey: string;
  wallet: WalletData;
  contractAddress: string;
  recipient: string;
  amount: string | number;
  decimals?: number;
}
```
