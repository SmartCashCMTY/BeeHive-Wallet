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
SmartCash Core is released under the MIT License. See COPYING for details.
Third-party components and libraries retain their respective licenses.
If the license of any component cannot be clearly determined, please check the original project.

## Disclaimer
This software is provided "as is", without warranty of any kind, express or implied. Use at your own risk.
The authors and contributors assume no liability for:
- Direct or indirect damages
- Data loss or corruption
- Financial losses
- Loss of access to wallets or private keys
- Misconfiguration or operator error
- Network or blockchain issues
- Software bugs or security vulnerabilities

## Cryptocurrency Risks
Cryptocurrencies involve substantial risk of loss and are not suitable for all investors.
- The value of digital assets can be highly volatile and may result in total loss
- Node operation, staking, and mining carry technical and financial risks
- You are solely responsible for securing your wallets and private keys
- You are responsible for compliance with local laws and tax obligations
- Past performance does not guarantee future results

## Legal Notice
Use of this software must comply with all applicable local, national, and international laws and regulations.
- You are responsible for regulatory, tax, and legal compliance in your jurisdiction
- No legal, tax, or financial advice is provided
- This software does not constitute an offer or solicitation of any kind
- All trademarks and logos remain the property of their respective owners