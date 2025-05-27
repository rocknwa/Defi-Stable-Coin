# Decentralized Stablecoin System

The Decentralized Stablecoin System is an advanced decentralized finance (DeFi) project demonstrating expertise in Solidity smart contract development. This portfolio project implements a USD-pegged stablecoin, Decentralized Stablecoin (DSC), backed by WETH and WBTC, inspired by MakerDAO’s DAI but designed to be minimal, governance-free, and fee-free. The project showcases gas optimization, security best practices, and complex integrations, positioning the developer as a skilled blockchain professional ready to contribute to innovative DeFi solutions.

---

## Project Overview

The Decentralized Stablecoin System is a robust DeFi protocol that maintains a 1:1 USD peg for the DSC token through algorithmic stability and over-collateralization (200% minimum). Users can deposit WETH or WBTC as collateral, mint DSC, redeem collateral, burn DSC, or liquidate under-collateralized positions to ensure solvency. 

**Key features include:**
- **Collateral Management:** Deposit and redeem WETH/WBTC with precise USD value tracking.
- **Stablecoin Operations:** Mint and burn DSC while enforcing health factor checks.
- **Liquidation Mechanism:** Liquidate insolvent users with a 10% bonus for liquidators.
- **Price Oracles:** Leverage Chainlink price feeds for accurate collateral valuations.
- **Testing and Deployment:** Comprehensive Foundry tests and deployment scripts for Sepolia and Anvil networks.

This project demonstrates the developer’s ability to design, test, and deploy a secure and efficient DeFi system.

---

## Skills Demonstrated

The Decentralized Stablecoin System highlights a blend of technical and transferable skills:

### Technical Skills

- **Solidity Development:** Proficient in writing modular, secure smart contracts using Solidity 0.8.19.
- **Gas Optimization:** Utilized efficient mappings, minimized state changes, and leveraged pure/view functions to reduce transaction costs.
- **Security Best Practices:** Implemented OpenZeppelin’s ReentrancyGuard, custom errors, Chainlink stale price checks, and failure case testing to mitigate risks.
- **Complex Integrations:** Integrated Chainlink price feeds, OpenZeppelin’s ERC20/Ownable, and multi-token collateral (WETH/WBTC) with precise USD conversions.
- **Testing with Foundry:** Developed extensive test suites, including unit, invariant, and failure case tests, with mocks for robust validation.
- **Scripting and Automation:** Created Forge scripts for deployment across Sepolia and Anvil, demonstrating automation proficiency.
- **Protocol Knowledge:** Deep understanding of stablecoin mechanics, over-collateralization, liquidation, and price oracles.

### Transferable Skills

- **Problem-Solving:** Addressed complex DeFi challenges, such as health factor calculations and liquidation bonuses.
- **Attention to Detail:** Ensured accurate collateral valuations and robust error handling to maintain system integrity.
- **System Design:** Architected a modular system with libraries and reusable components for scalability.
- **Adaptability:** Handled network-specific configurations and mock setups for flexible testing.

---

## Contracts

The project includes a concise set of smart contracts, each addressing critical stablecoin functionalities. Below is a recruiter-friendly overview, emphasizing their purpose and your implementation skills:

- **DecentralizedStableCoin:** An ERC20 token contract for the DSC stablecoin, with minting and burning restricted to the DSCEngine owner. Demonstrates secure token design and ownership controls.
- **DSCEngine:** The core contract managing collateral deposits, DSC minting/burning, redemptions, and liquidations. Showcases complex logic, gas-efficient mappings, and secure health factor checks.
- **OracleLib:** A library ensuring Chainlink price feeds are not stale (3-hour timeout). Highlights integration with Chainlink and security-focused price validation.
- **ERC20Mock:** A mock ERC20 token for simulating WETH/WBTC in tests. Demonstrates testing infrastructure setup.
- **MockV3Aggregator:** A mock Chainlink price feed for testing price updates. Showcases robust test environment design.
- **MockFailedMintDSC:** A mock DSC contract returning false on minting to test failure scenarios. Highlights thorough error handling.
- **MockFailedTransfer:** A mock DSC contract failing on transfer to test transfer issues. Demonstrates comprehensive testing.
- **MockFailedTransferFrom:** A mock DSC contract failing on transferFrom to test approval issues. Showcases edge case validation.
- **MockMoreDebtDSC:** A mock DSC contract crashing price feeds during burning to test debt scenarios. Highlights stress testing capabilities.

---

## Scripts and Tests

The project includes scripts and tests to automate deployment and ensure reliability, showcasing your operational and testing skills:

- **DeployDSC:** A Forge script to deploy DecentralizedStableCoin and DSCEngine, configure ownership, and support Sepolia/Anvil networks. Demonstrates automation and network adaptability.
- **HelperConfig:** A script providing network configurations (Sepolia, Anvil) with price feeds, tokens, and mocks. Highlights flexible deployment setup.
- **DSCEngineTest:** Comprehensive unit tests for DSCEngine, covering constructor, price calculations, collateral operations, minting, burning, redemptions, liquidations, and view functions. Showcases thorough validation.
- **DecentralizedStablecoinTest:** Unit tests for DecentralizedStableCoin, ensuring minting and burning restrictions. Demonstrates token security testing.
- **OracleLibTest:** Tests for OracleLib, validating stale price checks and timeout logic. Highlights Chainlink integration testing.
- **StopOnRevertHandler:** A test contract simulating user interactions (e.g., deposit, redeem, burn, liquidate) for invariant testing. Showcases dynamic testing capabilities.
- **StopOnRevertInvariants:** Defines invariants ensuring protocol solvency and getter reliability. Demonstrates advanced invariant testing.

---

## Achievements

- **Gas Optimization:** Designed DSCEngine with efficient mappings and minimal state updates, used pure/view functions for read-heavy operations, and optimized liquidation logic to reduce gas costs.
- **Security Best Practices:** Integrated OpenZeppelin’s ReentrancyGuard, implemented custom errors for gas-efficient reverts, enforced stale price checks in OracleLib, and tested failure cases (e.g., MockFailedMintDSC) to ensure robustness.
- **Complex Integrations:** Seamlessly integrated Chainlink price feeds for accurate pricing, OpenZeppelin’s ERC20/Ownable for secure token management, and multi-token collateral (WETH/WBTC) with precise USD conversions.
- **Comprehensive Testing:** Developed extensive Foundry tests, including unit, invariant, and failure case scenarios, with mocks to simulate real-world and edge cases, ensuring system reliability.
- **Automation:** Automated deployment across Sepolia and Anvil networks with DeployDSC and HelperConfig, streamlining setup and testing processes.

---

## Technical Stack

- **Programming Language:** Solidity 0.8.19
- **Development Framework:** Foundry (for testing, scripting, and deployment)
- **DeFi Integrations:**
  - Chainlink (price oracles)
  - OpenZeppelin (ERC20, Ownable, ReentrancyGuard)
- **Standards:** ERC20, NatSpec for documentation
- **Networks:** Sepolia, Anvil (with mock support)
- **Tools:** Forge for testing and scripting

---

## Setup and Testing

To explore the project, recruiters can note the developer’s robust development environment:

### Prerequisites

- **Install Foundry:**  
  ```bash
  curl -L https://foundry.paradigm.xyz | bash
  ```

- **Install dependencies:**  
  Ensure a Solidity-compatible environment (version 0.8.19).

### Clone the Repository

```bash
git clone https://github.com/rocknwa/Defi-Stable-Coin.git
cd Defi-Stable-Coin
```

### Install Dependencies

```bash
forge install
```

### Run Tests

Execute the test suites to verify functionality:

```bash
forge test --fork-url <YOUR_RPC_URL> -vvv
```

Replace `<YOUR_RPC_URL>` with a valid Ethereum node URL (e.g., Infura, Alchemy) or use Anvil for local testing.
You can also store your url in a .env file

### Deploy Contracts

Example deployment on Sepolia:

```bash
forge script script/DeployDSC.sol --rpc-url <YOUR_RPC_URL> --broadcast
```
Note: use `deployer` to store your private key

The project includes comprehensive Foundry tests (unit, invariant, and failure cases), demonstrating the developer’s commitment to code quality and reliability.

---

## Contact Information

For further inquiries or to discuss this project, please contact the developer via:

### **Author**
- **Therock Ani**  
- Twitter: [@ani_therock](https://twitter.com/ani_therock)  
- GitHub: [rocknwa](https://github.com/rocknwa)  
- Email: anitherock44@gmail.com  

