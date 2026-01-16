# One NFT to Configure them all 
![one ring to rule them all](https://github.com/user-attachments/assets/0e6c353e-4aa2-4113-b0f1-77657d28d3aa)


> Demo - https://www.loom.com/share/feb45b0c20a4462ca8d05756ded5a25d

> Product Spec - https://www.notion.so/Confyg-xyz-63c77c11d9454d7784567e6f3655ea24

> Built at **Polygon Fellowship – Class of 2022**.



## The problem Confyg solves
Have you felt the difficulty of setting up a new social account - the process of copying or changing your existing preferences and settings throughout all platforms. What if there’s a single stop to change your preferences and it gets automatically reflected everywhere else? 

This is what Confyg aims to solve using decentralized identifier NFTs and offchain datastores.

Sensitive user-centric data shouldn’t be on a centralized server and it offers a poor user experience by forcing users to recreate the same data on every application.


An alternative method would be to use resolvers in ENS to store user-centric data, but why should your personal preferences be on-chain?



## Overview

Confyg is a configuration layer for web3 applications.

Instead of re‑creating settings in every new app, a user configures their preferences once, mints a **configuration NFT**, and then compatible apps can read and respect those preferences. This gives:

- **Users**: a single place to manage preferences (theme, language, notifications, content filters, etc.).
- **Developers**: an easy way to onboard users with sensible defaults and shared state across dapps.


## Solution

Confyg introduces a **portable configuration profile** for web3 users.

- A user mints a **Confyg NFT** which acts as a **decentralised identifier (DID)** for their preferences.
- Their preferences are stored in an **off‑chain datastore**, referenced by the NFT.
- Any integrated dapp can read from this config and adapt its UI/behaviour accordingly.

### Key ideas

- **Single‑time setup**: configure once, reuse everywhere.
- **User‑owned config**: preferences are tied to a wallet + NFT, not a centralised account.
- **Composable layer**: apps can opt‑in to Confyg and map their settings to a shared config schema.

## How it works

### For users

1. **Connect wallet** to Confyg.
2. **Mint a Confyg NFT** that represents your configuration identity.
3. **Set your preferences** (e.g. theme, language, notification and safety settings).
4. **Use supported apps** – they can read your Confyg and apply those preferences automatically.

### For developers

1. Integrate Confyg’s **config reading API / contract calls**.
2. Map your app’s settings (e.g. `dark_mode`, `language`, `nsfw_filter`) to Confyg’s schema.
3. On wallet connect, fetch the user’s Confyg and apply defaults.
4. Optionally, write back changes so the user’s global profile stays up to date.

## Architecture (high level)

- **On‑chain**
  - Confyg NFT contract (DID‑style NFT per user).
  - Stores references (e.g. URI / hash) to the off‑chain configuration data.

- **Off‑chain**
  - Datastore holding structured configuration (JSON) keyed by the user’s Confyg identifier.
  - API/service for reading and (optionally) updating preferences.

- **Frontend**
  - Web app where users mint their Confyg NFT and manage preferences.
  - Basic documentation for developers integrating Confyg.

## Tech stack

- **Frontend**: Vue.js
- **Smart contracts**: Solidity (Confyg NFT / DID contract)
- **Blockchain**: Polygon (testnet/mainnet)
- **Tooling**: Hardhat/Truffle, ethers.js/web3.js
- **Off‑chain store**: IPFS / JSON store / custom API (describe your current choice)

