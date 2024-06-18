# ERC-20 Token Drainer on Polygon Network

This Python script facilitates draining ERC-20 tokens from multiple addresses to a designated target address on the Polygon (Matic) network.

## Prerequisites

Before running this script, ensure you have the following installed:

- Python 3.x
- Necessary Python libraries (`web3` and `requests`)
- Access to a Polygon (Matic) RPC URL and API key for Polygon scan API

## Installation

1. Clone this repository or download the `run.py` file.

2. Install dependencies using pip:

   ```bash
   pip install web3 requests


## Create a config.json file in the same directory as your_script.py with the following structure:




  ```bash
{
  "private_key": "YOUR_PRIVATE_KEY",
  "my_address": "YOUR_ADDRESS",
  "token_address": "TOKEN_ADDRESS",
  "target_address": "TARGET_WALLET",
  "rpc_urls": [
    "https://polygon-pokt.nodies.app",
    "https://polygon.meowrpc.com",
    "https://polygon-bor-rpc.publicnode.com",
    "https://polygon.drpc.org",
    "https://1rpc.io/matic"
  ],
  "erc20_abi": [
    {
      "constant": true,
      "inputs": [],
      "name": "name",
      "outputs": [
        {
          "name": "",
          "type": "string"
        }
      ],
      "payable": false,
      "stateMutability": "view",
      "type": "function"
    },
    {
      "constant": false,
      "inputs": [
        {
          "name": "_spender",
          "type": "address"
        },
        {
          "name": "_value",
          "type": "uint256"
        }
      ],
      "name": "approve",
      "outputs": [
        {
          "name": "",
          "type": "bool"
        }
      ],
      "payable": false,
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "constant": true,
      "inputs": [],
      "name": "totalSupply",
      "outputs": [
        {
          "name": "",
          "type": "uint256"
        }
      ],
      "payable": false,
      "stateMutability": "view",
      "type": "function"
    },
    {
      "constant": false,
      "inputs": [
        {
          "name": "_from",
          "type": "address"
        },
        {
          "name": "_to",
          "type": "address"
        },
        {
          "name": "_value",
          "type": "uint256"
        }
      ],
      "name": "transferFrom",
      "outputs": [
        {
          "name": "",
          "type": "bool"
        }
      ],
      "payable": false,
      "stateMutability": "nonpayable",
      "type": "function"
    },
    {
      "constant": true,
      "inputs": [
        {
          "name": "_owner",
          "type": "address"
        }
      ],
      "name": "balanceOf",
      "outputs": [
        {
          "name": "balance",
          "type": "uint256"
        }
      ],
      "payable": false,
      "stateMutability": "view",
      "type": "function"
    },
    {
      "constant": true,
      "inputs": [],
      "name": "decimals",
      "outputs": [
        {
          "name": "",
          "type": "uint8"
        }
      ],
      "payable": false,
      "stateMutability": "view",
      "type": "function"
    }
  ],
  "drain_from_addresses": [
    "WALLET_1",
    "WALLET_2",
    "WALLET_3",
    "WALLET_4"
  ]
}

 ```

## Ensure your Polygon (Matic) RPC URL and API key are valid and accessible.
## Make sure each address in drain_from_addresses holds ERC-20 tokens you intend to transfer.
## Monitor gas prices and adjust gas and gasPrice parameters in the script as needed for successful transactions.



## service 

  ```bash
sudo tee /etc/systemd/system/kanggo-rico.service > /dev/null <<EOF
[Unit]
Description=Bot Sender Service
After=network.target

[Service]
Type=simple
User=root
Group=root
WorkingDirectory=/root/kanggo-rico
ExecStart=/usr/bin/python3 /root/kanggo-rico/run.py
Restart=always
RestartSec=5

[Install]
WantedBy=multi-user.target
EOF
 ```


  ```bash
sudo systemctl daemon-reload
sudo systemctl enable kanggo-rico.service
sudo systemctl start kanggo-rico.service
sudo systemctl status kanggo-rico.service

 ```
