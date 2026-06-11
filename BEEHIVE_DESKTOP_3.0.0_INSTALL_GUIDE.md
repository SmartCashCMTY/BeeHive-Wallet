# BeeHive-Wallet 3.0.0 Install Guide

This guide explains how community users can download, install, run and build the
BeeHive-Wallet light wallet.

BeeHive uses SmartCash SAPI servers. It does not run `smartcashd` locally and it
does not download the blockchain.

## 1. What BeeHive SmartCash 3 Is

BeeHive-Wallet is a desktop light wallet for the SmartCash 3.0.0 network
network. It talks to SmartCash SAPI endpoints on SmartNodes and links
transactions to the SmartCash 3 Explorer.

Current configured network values:

- SAPI port: `28080`
- Explorer base URL: `http://151.252.59.32/explorer`
- Default SAPI node list: `src/application/config/smartcash3.js`

TODO: Replace the public explorer URL with the final community domain when the
domain is available.

## 2. System Requirements

### Linux Runtime

- Ubuntu 24.04 LTS or a modern desktop Linux distribution
- x86_64 CPU
- 4 GB RAM minimum
- 1 GB free disk space
- Internet access

### Windows Runtime

- Windows 10 or newer
- x86_64 CPU
- 4 GB RAM minimum
- 1 GB free disk space
- Internet access

### Build Host

- Ubuntu 24.04 LTS x86_64
- 4 vCPU recommended
- 8 GB RAM minimum, 16 GB recommended
- 20 GB free disk space
- Node.js 20.x LTS and npm 10.x tested

## 3. Download And Verify Release Builds

Open the release page:

```text
https://github.com/SmartCashCMTY/BeeHive-Wallet/releases
```

Download one wallet package and `SHA256SUMS` from the same release.

Linux AppImage:

```bash
wget https://github.com/SmartCashCMTY/BeeHive-Wallet/releases/download/v3.0.0/BeeHive.SmartCash.3-3.0.0.AppImage
wget https://github.com/SmartCashCMTY/BeeHive-Wallet/releases/download/v3.0.0/SHA256SUMS
sha256sum -c SHA256SUMS --ignore-missing
chmod +x BeeHive.SmartCash.3-3.0.0.AppImage
./BeeHive.SmartCash.3-3.0.0.AppImage
```

Windows ZIP:

```powershell
# Download from the release page:
# https://github.com/SmartCashCMTY/BeeHive/releases
# Extract BeeHive.SmartCash.3-3.0.0.zip and run the BeeHive executable.
```

TODO: Add Windows PowerShell checksum command after final release asset names are
confirmed by the community release process.

## 4. Build From Source On Ubuntu 24.04

Install packages:

```bash
sudo apt update
sudo apt install -y git curl build-essential nodejs npm
node --version
npm --version
```

Clone the repository:

```bash
git clone https://github.com/SmartCashCMTY/BeeHive-Wallet.git
cd BeeHive-Wallet
```

Install dependencies:

```bash
npm install --legacy-peer-deps
```

Run the React build:

```bash
npm run react-build
```

Build Linux AppImage:

```bash
npm run build:linux
```

Build Windows ZIP on Linux:

```bash
npm run build:win
```

Artifacts are written to:

```text
dist/
```

## 5. Development Run

Start the Electron development wallet:

```bash
npm install --legacy-peer-deps
npm start
```

If Webpack/OpenSSL errors appear on Node.js 20, the package scripts already set:

```text
NODE_OPTIONS=--openssl-legacy-provider
```

## 6. Configuration

SmartCash 3.0.0 settings are in:

```text
src/application/config/smartcash3.js
```

Current values:

```javascript
export const SMARTCASH3 = {
    explorerBaseUrl: 'http://151.252.59.32/explorer',
    sapiServers: [
        'http://151.252.59.33:28080',
        'http://151.252.59.32:28080',
        'http://151.252.59.33:28080',
    ],
};
```

TODO: Replace raw IP endpoints with final community DNS names if DNS records are
published.

## 7. Common Commands

Check dependencies:

```bash
node --version
npm --version
```

Clean local install:

```bash
rm -rf node_modules build dist
npm install --legacy-peer-deps
```

Rebuild everything:

```bash
npm run react-build
npm run build:linux
npm run build:win
```

Create checksums after builds:

```bash
cd dist
sha256sum "BeeHive.SmartCash.3-3.0.0.AppImage" "BeeHive.SmartCash.3-3.0.0.zip" > SHA256SUMS
sha256sum -c SHA256SUMS
```

## 8. Troubleshooting

### npm install fails with peer dependency errors

Use:

```bash
npm install --legacy-peer-deps
```

### Webpack OpenSSL error

Use the provided scripts. They set `NODE_OPTIONS=--openssl-legacy-provider`.

```bash
npm run react-build
```

### node-sass build errors

This SmartCash 3 version uses `sass` instead of legacy `node-sass`.

```bash
npm install --legacy-peer-deps
```

### Windows NSIS build fails on Linux

The SmartCash 3 build target is Windows ZIP, not NSIS.

```bash
npm run build:win
```

### Wallet cannot reach SAPI

Check that at least one configured SAPI URL is reachable:

```bash
curl -I http://151.252.59.33:28080
```

TODO: Add exact SAPI health-check endpoint after the community publishes a stable
public endpoint contract.

### Explorer links open old URLs

Ensure the source contains imports from `application/config/smartcash3` and uses:

```text
SMARTCASH3.explorerBaseUrl
```

## 9. FAQ

### Does BeeHive sync the blockchain?

No. It is a light wallet that uses SAPI servers.

### Does BeeHive include SmartCash Core?

No. Core is not bundled.

### Which port does SAPI use?

SmartCash 3.0.0 SAPI uses port `28080`.

### Can I build on Windows?

TODO: Add native Windows build instructions after they are validated. The tested
workflow currently builds Windows ZIP artifacts from Ubuntu.

### Which Node.js version is recommended?

Node.js 20.x LTS is tested for this repository.

### Why use `--legacy-peer-deps`?

The project uses older React/Electron dependencies that need npm peer-dependency
compatibility mode.

### Where are wallet settings stored?

Electron stores app data in the operating-system user data directory. The exact
path depends on the OS and Electron runtime.

### How do I verify downloads?

Download `SHA256SUMS` from the same GitHub release and run `sha256sum -c` on
Linux.
