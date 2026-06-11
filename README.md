# BeeHive-Wallet

SmartCash 3.0.0 SAPI light wallet update for desktop users.

## What It Does
- Builds the BeeHive desktop wallet for Linux and Windows
- Connects to SmartCash SAPI nodes
- Does not run a local SmartCash daemon

## Quick Start
```bash
git clone https://github.com/SmartCashCMTY/BeeHive-Wallet.git
cd BeeHive-Wallet
npm install --legacy-peer-deps
npm run build:linux
```

## System Requirements
- Ubuntu 24.04 LTS or similar Linux build host
- Node.js and npm
- Git, build tools, and a working internet connection

## Installation
```bash
sudo apt update
sudo apt install -y git curl build-essential nodejs npm
npm install --legacy-peer-deps
npm run build:linux
```

## Configuration
- SAPI nodes: `src/application/config/smartcash3.js`
- Explorer URL: `http://151.252.59.32/explorer/`

## Update
- Pull the latest source and rebuild the desktop app

## Backup
- Keep your wallet data and exported keys outside the repository

## Security
- Never commit private keys, seed phrases, passwords, or API keys
- Review release artifacts before distribution

## Credits
Original SmartCash Project: https://github.com/smartcash
This repository is an Update 3.0.0 based on the open-source work of the SmartCash project.
All rights to original components, trademarks, logos, source code, and documentation remain with their respective owners.
The original creator and relevant open-source contributors should be acknowledged appropriately.

## License
SmartCash Core components are generally released under MIT. BeeHive and third-party components keep their own licenses.
Please check the original project license.

## Disclaimer
Use at your own risk. No warranty is provided for functionality, availability, or security. No liability is accepted for direct or indirect damages, data loss, wallet loss, lost private keys, misconfiguration, network issues, blockchain issues, software bugs, or security vulnerabilities.

## Cryptocurrency Risks
Cryptocurrencies are high-risk digital assets. Losses, including total loss, are possible. Node operation and staking-related workflows may fail or behave unexpectedly. You are responsible for wallet backups, local law compliance, and tax obligations.

## Legal Notice
Use this software in accordance with the laws and regulations that apply in your jurisdiction. You are responsible for regulatory, tax, and legal compliance in your country. No legal, tax, or financial advice is provided.

## TODO
Please check the original project license for any additional third-party components.
