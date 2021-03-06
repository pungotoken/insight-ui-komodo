![Pungo Token](https://i.ibb.co/T0cFLpx/token-regular-small.png)

# Insight UI

A Bitcoin blockchain explorer web application service for [Bitcore Node](https://github.com/pungotoken/bitcore-node-komodo.git) using the [Insight API](https://github.com/pungotoken/insight-api-komodo.git).

## Development Resources

- PungoToken Website: [https://pungotoken.com](https://pungotoken.com/)
- PungoToken Blockexplorer: [https://explorer.pungotoken.com](https://explorer.pungotoken.com)
- PungoToken Telegram: [https://t.me/pungotalk](https://t.me/pungotalk)
- PungoToken Node Addresses:  190.114.254.103, 190.114.254.104
- PungoToken Electrum Servers Addresses: electrum1.pungo.cloud:10002 electrum2.pungo.cloud:10002

## Getting Started

### Dependencies

You must run PGT coin see [https://github.com/pungotoken/komodo](https://github.com/pungotoken/komodo)

To manually install all of the necessary components, you can run these commands:

```bash
sudo -s apt-get -yq install nodejs-legacy npm libzmq3-dev  
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash 
export NVM_DIR="$HOME/.nvm" 
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" 
nvm install v4 
npm install https://github.com/pungotoken/bitcore-node-komodo.git
npm install http-signature
nvm use v4; node_modules/bitcore-node-komodo/bin/bitcore-node create mainnet
cd mainnet && npm install --save fs-extra && npm install --save http-signature har-validator 
../node_modules/bitcore-node-komodo/bin/bitcore-node install https://github.com/pungotoken/insight-api-komodo.git https://github.com/pungotoken/insight-ui-komodo.git
```

```bash
npm install -g bitcore
bitcore create mynode
cd mynode
bitcore install insight-api
bitcore install insight-ui
```

### Quick Start

Please see the guide at [https://bitcore.io/guides/full-node](https://bitcore.io/guides/full-node) for information about getting a block explorer running. This is only the front-end component of the block explorer, and is packaged together with all of the necessary components in [Bitcore](https://github.com/bitpay/bitcore).

Create config:

```
cat <<EOF > mynode/bitcore-node.json
{
  "network": "livenet",
  "port": 3001,
  "services": [
    "bitcoind",
    "insight-api",
    "insight-ui",
    "web"
  ],
  "servicesConfig": {
    "bitcoind": {
      "connect": [
        {
          "rpchost": "127.0.0.1",
          "rpcport": 8232,
          "rpcuser": "<<<YOU RPC USER>>>",
          "rpcpassword": "<<<YOU RPC PASSWORD>>>",
          "zmqpubrawtx": "tcp://127.0.0.1:8332"
        }
      ]
    }
  }
}
EOF
```

Run Insight:
```
../node_modules/bitcore-node-komodo/bin/bitcore-node start
```

Open a web browser to `http://localhost:3001/insight/`

