
## Blockchain Monitor

## Installation

    npm install --save blockchain-account-monitor

## Usage

    const blockchain = require('blockchain-account-monitor');

    const monitor = new blockchain.AccountMonitor({
      blockchainClient:  new blockchain.Client({
        host: "You.Daemon.Host.here",
        port: 18823,
        user: "someRpcUser",
        pass: "sup3rstr0ngRpCP@ssw0rd",
        confirmations: 3,
        type: 'newyorkcoin'
      }),
      onBlock: function(block, next) {
        console.log('FOUND '+block.length+ ' transactions');
        console.log('block', block);
        next();
      },  
      timeout: 1000
    });

    monitor.lastBlockHash = '23e1b5d9c4258352e6d34728816cde2d46968072cf8d8545184b832149bdb94b';

    monitor.start();

