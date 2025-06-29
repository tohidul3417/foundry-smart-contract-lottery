# Foundry Smart Contract Lottery

[![CI](https://github.com/tohidul3417/foundry-smart-contract-lottery/actions/workflows/test.yml/badge.svg)](https://github.com/tohidul3417/foundry-smart-contract-lottery/actions/workflows/test.yml)

## Table of Contents

- [About The Project](#about-the-project)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation & Setup](#installation--setup)
- [Usage](#usage)
  - [Building](#building)
  - [Testing](#testing)
  - [Deployment](#deployment)
- [Continuous Integration](#continuous-integration)
- [Contributing](#contributing)
- [License](#license)

---

## About The Project

This project implements a decentralized smart contract lottery system using the [Foundry](https://github.com/foundry-rs/foundry) development framework. The smart contract is designed to allow users to enter a lottery with a specific fee, and a provably random winner is chosen using [Chainlink VRF](https://docs.chain.link/vrf).

This repository serves as a learning exercise and was completed as a part of **Foundry Fundamentals** course's (offered by Cyfrin Updraft) *Foundry Smart Contract Lottery* section.

## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing.

### Prerequisites

You will need to have [Foundry](https://book.getfoundry.sh/getting-started/installation) installed. Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.

-   **Foundry (Forge & Anvil)**
    ```sh
    curl -L [https://foundry.paradigm.xyz](https://foundry.paradigm.xyz) | bash
    foundryup
    ```

### Installation & Setup

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/tohidul3417/foundry-smart-contract-lottery.git
    cd foundry-smart-contract-lottery
    ```

2.  **Build the project:**
    This single command will install all necessary dependencies and compile the contracts.
    ```sh
    forge build
    ```

## Usage

Foundry's `forge` is the primary tool for interacting with the contracts.

### Building

If you've already run the setup, you can re-compile the smart contracts at any time by running:
```sh
forge build
```
This will compile the contracts and place the artifacts in the `out/` directory, as specified in `foundry.toml`.

### Testing

This project comes with a comprehensive test suite. To run all tests:
```sh
forge test
```

For more detailed test output, you can use the `-vvv` flag:
```sh
forge test -vvv
```

### Deployment

To deploy the contracts, you can use `forge script`. You will need to set up environment variables for your private key and RPC URL.

1.  **Start a local node (optional, for local testing):**
    ```sh
    anvil
    ```

2.  **Deploy the contract:**
    Create a `.env` file and populate it with your `PRIVATE_KEY` and an `RPC_URL` (e.g., from Infura or Alchemy).

    Then, run the deployment script (assuming your script is named `DeployLottery.s.sol` in the `script/` directory):
    ```sh
    forge script script/DeployLottery.s.sol --rpc-url $YOUR_RPC_URL --private-key $YOUR_PRIVATE_KEY --broadcast
    ```

## Continuous Integration

This repository has a CI pipeline configured in `.github/workflows/test.yml`. The workflow is triggered on every `push` and `pull_request` and performs the following checks:
1.  Installs Foundry.
2.  Runs the formatter (`forge fmt --check`).
3.  Builds the project (`forge build --sizes`).
4.  Runs the full test suite (`forge test -vvv`).

This ensures that the codebase remains consistent and that all tests pass before merging new changes.

## Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.
