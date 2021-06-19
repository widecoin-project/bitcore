# Widecore
  
**Infrastructure to build Widecoin and blockchain-based applications for the next generation of financial technology.**

## Getting Started

### Requirements

- Trusted P2P Peer
- MongoDB Server >= v3.4
- make g++ gcc 

### Checkout the repo


```sh
git clone git@github.com:bitpay/Widecore.git
git checkout master
npm install
```

## Setup Guide

### 1. Setup Widecore config

<details>
<summary>Example Widecore.config.json</summary>
<br>

```json
{
  "WidecoreNode": {
    "chains": {
      "BTC": {
        "mainnet": {
          "chainSource": "p2p",
          "trustedPeers": [
            {
              "host": "127.0.0.1",
              "port": 20008
            }
          ],
          "rpc": {
            "host": "127.0.0.1",
            "port": 20009,
            "username": "username",
            "password": "password"
          }
        },
        "regtest": {
          "chainSource": "p2p",
          "trustedPeers": [
            {
              "host": "127.0.0.1",
              "port": 20020
            }
          ],
          "rpc": {
            "host": "127.0.0.1",
            "port": 20021,
            "username": "username",
            "password": "password"
          }
        }
      },
      "BCH": {
        "mainnet": {
          "parentChain": "BTC",
          "forkHeight": 478558,
          "trustedPeers": [
            {
              "host": "127.0.0.1",
              "port": 30008
            }
          ],
          "rpc": {
            "host": "127.0.0.1",
            "port": 30009,
            "username": "username",
            "password": "password"
          }
        },
        "regtest": {
          "chainSource": "p2p",
          "trustedPeers": [
            {
              "host": "127.0.0.1",
              "port": 30020
            }
          ],
          "rpc": {
            "host": "127.0.0.1",
            "port": 30021,
            "username": "username",
            "password": "password"
          }
        }
      }
    }
  }
}
```

</details>

### 2. Setup Widecoin Node

<details>
<summary>Example Widecoin Mainnet Config</summary>

```sh
whitelist=127.0.0.1
txindex=0
listen=1
server=1
irc=1
upnp=1

# Make sure port & rpcport matches the
# Widecore.config.json ports for BTC mainnet

# if using Widecoin Core v0.17+ prefix
# [main]

port=20008
rpcport=20009
rpcallowip=127.0.0.1

rpcuser=username
rpcpassword=password
```

</details>

### 3. Run Widecoin node

<details>
<summary>Example Starting a Widecoin Node</summary>

```sh
# Path to your Widecoin application and path to the config above
/Applications/Widecoin-Qt.app/Contents/MacOS/Widecoin-Qt -datadir=/Users/username/blockchains/Widecoin-core/networks/mainnet/
```

</details>

### 4. Start Widecore

```sh
npm run node
```

## Applications

- [Widecore Node](packages/Widecore-node) - A full node with extended capabilities using Widecoin Core
- [Widecore Wallet](packages/Widecore-wallet) - A command-line based wallet client
- [Widecore Wallet Client](packages/Widecore-wallet-client) - A client for the wallet service
- [Widecore Wallet Service](packages/Widecore-wallet-service) - A multisig HD service for wallets
- [Bitpay Wallet](https://github.com/bitpay/copay) - An easy-to-use, multiplatform, multisignature, secure Widecoin wallet
- [Insight](packages/insight) - A blockchain explorer web user interface

## Libraries

- [Widecore Lib](packages/Widecore-lib) - A pure and powerful JavaScript Widecoin library
- [Widecore Lib Cash](packages/Widecore-lib-cash) - A pure and powerful JavaScript Widecoin Cash library
- [Widecore Message](https://github.com/bitpay/Widecore-message) - Widecoin message verification and signing
- [Widecore Mnemonic](packages/Widecore-mnemonic) - Implements mnemonic code for generating deterministic keys
- [Widecore P2P](packages/Widecore-p2p) - The peer-to-peer networking protocol for WCN
- [Crypto Wallet Core](packages/crypto-wallet-core) - A coin-agnostic wallet library for creating transactions, signing, and address derivation

## Extras

- [Widecore Build](packages/Widecore-build) - A helper to add tasks to gulp
- [Widecore Client](packages/Widecore-client) - A helper to create a wallet using the Widecore-v8 infrastructure

## Contributing

See [CONTRIBUTING.md](https://github.com/bitpay/bitcore/blob/master/Contributing.md) on the main bitcore repo for information about how to contribute.

## License

Code released under [the MIT license](https://github.com/bitpay/bitcore/blob/master/LICENSE).

Copyright 2013-2019 BitPay, Inc. Bitcore is a trademark maintained by BitPay, Inc.
Copyright 2020-2021 Widecoin.
