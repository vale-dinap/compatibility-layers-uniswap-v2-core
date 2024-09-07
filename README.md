# Uniswap V2 Core – Compatibility Layer

## Overview
This repository contains a fork of the [Uniswap V2 Core](https://github.com/Uniswap/v2-core) protocol, designed to ensure compatibility with the latest Solidity versions. The primary focus of this fork is to facilitate interaction and integration testing with external smart contracts, while avoiding any modifications to the core logic of Uniswap V2, aside from necessary adjustments for Solidity compiler compatibility.

## Purpose
This compatibility layer has been created with two goals in mind:
- **Ensure Compatibility**: Update the Uniswap V2 core contracts to work seamlessly with Solidity 0.8.x and newer versions, ensuring that external projects do not face version incompatibility issues.
- **Enable Testing**: Provide an environment where developers can test their smart contracts against the Uniswap V2 protocol, using modern Solidity tooling, without needing to modify the protocol's fundamental behavior.

## What’s Included
The repository includes:
- Updated Solidity contracts for compatibility with version 0.8.x and above.
- Key components from the Uniswap V2 core:
  - **UniswapV2Factory**
  - **UniswapV2Pair**
  - **UniswapV2ERC20**

## What’s Not Changed
In keeping with the goal of maintaining the integrity of the original protocol:
- No changes have been made to the core logic or functionality of Uniswap V2, except for those required to ensure compatibility with newer Solidity compiler versions.
- The operational and fee structures remain the same as in the original Uniswap V2 Core.

## Directory Structure
```bash
compatibility-layers/
└── uniswap/
    └── v2-core/
        ├── contracts/
        │   ├── interfaces/
        │   │   ├── IERC20.sol
        │   │   ├── IUniswapV2Callee.sol
        │   │   ├── IUniswapV2ERC20.sol
        │   │   ├── IUniswapV2Events.sol
        │   │   ├── IUniswapV2Factory.sol
        │   │   └── IUniswapV2Pair.sol
        │   ├── libraries/
        │   │   ├── Math.sol
        │   │   ├── SafeMath.sol
        │   │   └── UQ112x112.sol
        ├── test/
        │   ├── ERC20.sol
        │   ├── UniswapV2ERC20.sol
        │   ├── UniswapV2Factory.sol
        │   └── UniswapV2Pair.sol
        ├── .gitattributes
        ├── .gitignore
        ├── .mocharc.json
        ├── .prettierrc
        ├── .waffle.json
        ├── CITATION.cff
        ├── LICENSE
        ├── package.json
        ├── README.md
        ├── tsconfig.json
        └── yarn.lock
```

## Key Folders
**contracts/interfaces/**: Contains the core interfaces for ERC20 and Uniswap V2, including the factory, pair, callee, and event interfaces.
**contracts/libraries/**: Includes helper libraries for mathematical operations, such as SafeMath and UQ112x112.
**test/**: Contains Solidity test files to verify Uniswap V2 functionality in external projects.

## Installation
To use this compatibility layer for testing or integrating external projects:

### 1. Clone the Repository:
```bash
git clone https://github.com/vale-dinap/uniswap-v2-core.git
```

### 2. Install Dependencies:
Make sure you have installed the necessary dependencies by running:
```bash
yarn install
```

### 3. Compile Contracts:
Ensure the Solidity compiler version is compatible with the updated contracts:
```bash
forge build
```

### 4. Run Tests:
Test the contracts using Foundry or your preferred testing framework:
```bash
forge test
```

## Contributing
Contributions are welcome, especially if they help to further improve compatibility or testing capabilities. Please open an issue or a pull request if you encounter bugs, or if you have suggestions for improvements.

## License
This project is licensed under the same terms as the original Uniswap V2 Core, which is available under the GPL-3.0 License. All rights to the original Uniswap V2 Core code remain with [Uniswap Labs](https://uniswap.org/).
