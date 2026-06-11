# BeeHive-Wallet

BeeHive-Wallet is a SmartCash 3.0.0 SAPI light wallet. It does not
run a local SmartCash daemon and does not sync the blockchain.

## Download

Release downloads are published here:

```text
https://github.com/SmartCashCMTY/BeeHive-Wallet/releases
```

Expected release assets:

- `BeeHive.SmartCash.3-3.0.0.AppImage` for Linux
- `BeeHive.SmartCash.3-3.0.0.zip` for Windows
- `SHA256SUMS`

## Build From Source

Ubuntu 24.04 example:

```bash
sudo apt update
sudo apt install -y git curl build-essential nodejs npm
git clone https://github.com/SmartCashCMTY/BeeHive-Wallet.git
cd BeeHive-Wallet
npm install --legacy-peer-deps
npm run build:linux
npm run build:win
```

Build artifacts are created in `dist/`.

## Network

- SmartCash 3.0.0 SAPI port: `28080`
- Explorer: `http://151.252.59.32/explorer/`
- SAPI nodes are configured in `src/application/config/smartcash3.js`

## Complete Guide

Read:

```text
BEEHIVE_DESKTOP_3.0.0_INSTALL_GUIDE.md
```
