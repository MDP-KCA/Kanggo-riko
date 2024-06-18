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
  "rpc_url": "https://rpc.maticvigil.com/v1",
  "private_key": "YOUR_PRIVATE_KEY",
  "my_address": "YOUR_ADDRESS",
  "token_address": "TOKEN_ADDRESS",
  "drain_from_addresses": ["WALLET_1", "WALLET_2", "WALLET_3", "WALLET_4"],
  "target_address": "TARGET_WALLET",
  "api_key": "YOUR_API_KEY",
  "scan_api_url": "https://api.polygonscan.com/api",
  "chain_id": 137
}
 ```

## Ensure your Polygon (Matic) RPC URL and API key are valid and accessible.
## Make sure each address in drain_from_addresses holds ERC-20 tokens you intend to transfer.
## Monitor gas prices and adjust gas and gasPrice parameters in the script as needed for successful transactions.
