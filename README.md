# Insight UI

A Bitcoin blockchain explorer web application service for [Bitcore Node](https://github.com/bitpay/bitcore-node) using the [Insight API](https://github.com/supernetorg/insight-api-komodo).

## Quick Start

Please see the guide at [https://bitcore.io/guides/full-node](https://bitcore.io/guides/full-node) for information about getting a block explorer running. This is only the front-end component of the block explorer, and is packaged together with all of the necessary components in [Bitcore](https://github.com/bitpay/bitcore).

## Getting Started

To manually install all of the necessary components, you can run these commands:

```bash
npm install -g bitcore-node
bitcore-node create mynode
cd mynode
bitcore-node install insight-api
bitcore-node install insight-ui
bitcore-node start
```

Open a web browser to `http://localhost:3001/insight/`

## Development

To run Insight UI locally in development mode:

Install bower dependencies:

```
$ bower install
```

To compile and minify the web application's assets:

```
$ grunt compile
```

There is a convenient Gruntfile.js for automation during editing the code

```
$ grunt
```

* * *
