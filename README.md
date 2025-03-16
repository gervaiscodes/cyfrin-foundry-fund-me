# FundMe Solidity Project

## Overview

FundMe is a Solidity-based crowdfunding smart contract project utilizing Chainlink oracles to fetch price data for accurate ETH to USD conversion. The project is structured with Foundry for smart contract development, testing, and deployment.

## Features

- **Funding Mechanism**: Users can fund the contract with ETH.
- **Owner Withdrawal**: The contract owner can withdraw funds.
- **Price Conversion**: Utilizes Chainlink's `MockV3Aggregator` for price feeds.
- **Automated Tests**: Uses Foundry for Solidity testing.

## Project Structure

```
- src/
  - FundMe.sol              # Main contract for funding
  - PriceConverter.sol      # Library for ETH to USD conversion
  - MockV3Aggregator.sol    # Mock price feed for testing

- script/
  - DeployFundMe.s.sol      # Deployment script
  - Interactions.s.sol      # Script for interacting with deployed contract
  - HelperConfig.s.sol      # Configuration script

- test/
  - FundMeTest.t.sol        # Unit tests for FundMe contract
  - InteractionsTest.t.sol  # Tests for interactions

- foundry.toml              # Foundry configuration
- Makefile                  # Build automation script
```

## Installation & Setup

### Prerequisites

- [Foundry](https://getfoundry.sh/) installed
- Node.js and npm installed
- `.env` file with necessary RPC URLs

### Installation

1. Clone the repository:

```sh
git clone <repo-url>
cd FundMe
```

2. Install dependencies:

```sh
forge install
```

3. Configure Foundry:

```sh
cp foundry.toml.example foundry.toml
```

   Modify `foundry.toml` to include your RPC endpoints.

## Usage

### Compile Contracts

```sh
forge build
```

### Run Tests

```sh
forge test
```

### Deploy to Sepolia Testnet

```sh
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast
```

### Interact with Deployed Contract

```sh
forge script script/Interactions.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast
```

## Contributing

1. Fork the repository.
2. Create a feature branch.
3. Submit a pull request.

## License

MIT License.
