# Take Profits Hook for Uniswap V4

A sophisticated Uniswap V4 hook that enables automated take profit orders for decentralized trading. This project implements a hook system that monitors pool price movements and automatically executes trades when specified price targets are reached.

## 🚀 Features

- **Automated Take Profit Orders**: Set price targets for your tokens and automatically execute trades when reached
- **Uniswap V4 Integration**: Built on the latest Uniswap V4 architecture using hooks
- **ERC-1155 Token System**: Each order is represented as an ERC-1155 token for easy management
- **Real-time Price Monitoring**: Continuously monitors pool ticks and executes orders when conditions are met
- **Gas Efficient**: Optimized for minimal gas consumption during order execution

## 🏗️ Architecture

The `TakeProfitsHook` is a Uniswap V4 hook that:

1. **Monitors Pool State**: Tracks price changes through tick movements
2. **Manages Orders**: Stores pending take profit orders with specific price targets
3. **Auto-executes**: Automatically triggers trades when price conditions are met
4. **Token Management**: Uses ERC-1155 tokens to represent and track orders

### Hook Permissions

- `afterInitialize`: Records initial pool tick
- `afterSwap`: Monitors price changes and executes pending orders

## 📁 Project Structure

```
src/
├── TakeProfitsHook.sol          # Main hook contract
test/
├── TakeProfitsHook.t.sol        # Comprehensive test suite
lib/                              # Dependencies (Uniswap V4, OpenZeppelin, etc.)
```

## 🛠️ Development

This project is built with [Foundry](https://getfoundry.sh/), a blazing fast Ethereum development toolkit.

### Prerequisites

- [Foundry](https://getfoundry.sh/) installed
- Solidity ^0.8.0

### Setup

```bash
# Clone the repository
git clone <repository-url>
cd limit-orders

# Install dependencies
forge install
```

### Build

```bash
forge build
```

### Test

```bash
# Run all tests
forge test

# Run with verbose output
forge test -vvv

# Run specific test
forge test --match-test testTakeProfitOrder
```

### Gas Optimization

```bash
# Generate gas snapshots
forge snapshot
```

## 🔧 Usage

### Creating a Take Profit Order

1. **Approve Tokens**: Approve the hook contract to spend your tokens
2. **Place Order**: Call the hook to create a take profit order at a specific tick
3. **Monitor**: The hook automatically monitors price movements
4. **Execution**: When the target price is reached, the order is automatically executed

### Key Functions

- `placeTakeProfitOrder`: Create a new take profit order
- `claimTokens`: Claim tokens after order execution
- `cancelOrder`: Cancel a pending order (if supported)

## 🧪 Testing

The project includes comprehensive tests covering:

- Order placement and execution
- Price movement scenarios
- Edge cases and error conditions
- Gas optimization verification

Run tests with:

```bash
forge test
```

## 📚 Dependencies

- **Uniswap V4 Core**: Core pool management and types
- **Uniswap V4 Periphery**: Hook utilities and base classes
- **OpenZeppelin**: ERC-1155 implementation and utilities
- **Solmate**: Gas-optimized math libraries

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## 📄 License

This project is licensed under the UNLICENSED license.

## ⚠️ Disclaimer

This software is for educational and experimental purposes. Use at your own risk. The authors are not responsible for any financial losses incurred through the use of this software.

## 🔗 Links

- [Uniswap V4 Documentation](https://docs.uniswap.org/)
- [Foundry Book](https://book.getfoundry.sh/)
- [Uniswap V4 Hooks Guide](https://docs.uniswap.org/contracts/v4/overview)
