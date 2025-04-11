# DSCEngine Smart Contract

## Overview
**DSCEngine** is the core contract of the Decentralized Stablecoin (DSC) system. It is designed to maintain a stable value of **1 DSC = $1** by being **overcollateralized** and ensuring the security and stability of the protocol. This contract facilitates the minting and redeeming of DSC tokens, as well as the management of collateral deposits and withdrawals.

## Features
- **Exogenously Collateralized**
- **Dollar Pegged**
- **Algorithmically Stable**
- **Overcollateralized System**
- **Supports Multiple Collateral Types (WETH, WBTC, etc.)**
- **Liquidation Mechanism**
- **No Governance or Fees**

## Contract Structure
The contract follows a structured layout to enhance readability and maintainability:

### **Layout of Contract**
1. **Version Declaration**
2. **Imports**
3. **Errors**
4. **Interfaces, Libraries, Contracts**
5. **Type Declarations**
6. **State Variables**
7. **Events**
8. **Modifiers**
9. **Functions**

### **Layout of Functions**
1. **Constructor**
2. **Receive Function (if applicable)**
3. **Fallback Function (if applicable)**
4. **External Functions**
5. **Public Functions**
6. **Internal Functions**
7. **Private Functions**
8. **Internal & Private View/Pure Functions**
9. **External & Public View/Pure Functions**

## **Key Components**

### **State Variables**
- `i_dsc`: Immutable reference to the DecentralizedStableCoin contract.
- `s_priceFeeds`: Mapping of collateral token addresses to their respective price feed addresses.
- `s_collateralDeposited`: Tracks user deposits of different collateral types.
- `s_DSCMinted`: Tracks the amount of DSC minted by each user.
- `s_collateralTokens`: Array storing the list of allowed collateral tokens.
- **Constants:** Various precision, liquidation, and health factor thresholds.

### **Modifiers**
- `moreThanZero(amount)`: Ensures the input amount is greater than zero.
- `isAllowedToken(token)`: Ensures the token is a supported collateral type.

### **Events**
- `CollateralDeposited(user, token, amount)`: Logs collateral deposits.
- `CollateralRedeemed(redeemFrom, redeemTo, token, amount)`: Logs collateral withdrawals.

## **Core Functions**

### **External Functions**
- `depositCollateralAndMintDsc(tokenCollateralAddress, amountCollateral, amountDscToMint)`: Deposits collateral and mints DSC in a single transaction.
- `redeemCollateralForDsc(tokenCollateralAddress, amountCollateral, amountDscToBurn)`: Withdraws collateral and burns DSC in a single transaction.
- `redeemCollateral(tokenCollateralAddress, amountCollateral)`: Withdraws collateral if no DSC is minted.
- `burnDsc(amount)`: Burns DSC to maintain health factor.
- `liquidate(collateral, user, debtToCover)`: Allows users to liquidate undercollateralized accounts.

### **Public Functions**
- `mintDsc(amountDscToMint)`: Mints DSC if sufficient collateral is available.
- `depositCollateral(tokenCollateralAddress, amountCollateral)`: Deposits collateral into the protocol.

### **Private Functions**
- `_redeemCollateral(tokenCollateralAddress, amountCollateral, from, to)`: Handles collateral withdrawals.
- `_burnDsc(amountDscToBurn, onBehalfOf, dscFrom)`: Burns DSC on behalf of a user.

### **Internal & Private View Functions**
- `_getAccountInformation(user)`: Retrieves user DSC and collateral balances.
- `_healthFactor(user)`: Calculates user's health factor.
- `_getUsdValue(token, amount)`: Retrieves token price from the oracle.

## **Security Considerations**
- **Reentrancy Guard**: Utilizes OpenZeppelin’s `ReentrancyGuard` to prevent reentrancy attacks.
- **Overcollateralization**: Ensures system stability by maintaining a collateralization ratio above **200%**.
- **Liquidation Mechanism**: Prevents bad debt accumulation by allowing liquidators to seize undercollateralized positions.
- **Access Control**: Only allowed collateral tokens are accepted.

## **Deployment Instructions**
1. Deploy `DecentralizedStableCoin` contract.
2. Deploy `DSCEngine` contract with:
   - Array of collateral token addresses.
   - Array of respective price feed addresses.
   - Address of `DecentralizedStableCoin` contract.
3. Ensure collateral tokens are properly funded.

## **License**
This project is licensed under the **MIT License**.

---

# Clone the Uniswap v4-template repository
```bash
git clone [https://github.com/rocknwa/Defi-Stable-Coin.git](https://github.com/rocknwa/Defi-Stable-Coin.git)
```

# Navigate into the project directory

```bash
cd Defi-Stable-Coin
```

# Install dependencies using Foundry

```bash
forge install
```

# Run tests to ensure everything is set up correctly

```base
forge test
```

### **Author**
- **Therock Ani**  
- Twitter: [@ani_therock](https://twitter.com/ani_therock)  
- GitHub: [rocknwa](https://github.com/rocknwa)  
- Email: anitherock44@gmail.com

