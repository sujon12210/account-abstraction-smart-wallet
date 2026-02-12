# Account Abstraction Smart Wallet (EIP-4337)

This repository provides a high-quality implementation of a Smart Contract Wallet based on the ERC-4337 standard. It allows users to interact with the blockchain using programmable logic rather than a simple private key (EOA).

## Features
- **Social Recovery**: Designate "guardians" who can reset your wallet access if you lose your key.
- **Batching**: Execute multiple transactions (e.g., Approve + Swap) in a single atomic step to save gas.
- **Paymaster Support**: Enables dApps to sponsor gas fees for their users.
- **Signature Abstraction**: Support for alternative signature schemes like Secp256r1 (WebAuthn/FaceID).



## Core Concepts
- **UserOperation**: A pseudo-transaction object that describes a transaction to be sent.
- **Bundler**: A node that packages UserOperations from a mempool and submits them to the EntryPoint.
- **EntryPoint**: A singleton contract that handles the verification and execution logic for all compliant wallets.

## Getting Started
1. Deploy the `SimpleAccountFactory`.
2. Generate a `UserOperation` and sign it with your owner key.
3. Submit the operation to an EIP-4337 Bundler on a supported L2 (Arbitrum, Polygon, etc.).
