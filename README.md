# LTV Points Calculator

A blockchain event processing system that calculates loyalty points for users based on their holdings of Pilot Vault tokens and NFT ownership. The system processes Ethereum blockchain events to track user balances and compute points on a daily basis.

## Overview

This system calculates points for users based on:
- **Pilot Vault Token Holdings**: Users earn points proportional to their token balance
- **NFT Ownership Bonus**: Users holding at least one NFT receive a 1.42x multiplier on their points

The calculation runs daily, processing all events from contract deployment through the latest available block, maintaining complete historical state and point accumulation.

## Usage

### Running the Full Pipeline

Execute the complete points calculation pipeline:

```bash
python3 main.py
```

This will run all processing steps in sequence:
1. Find deployment blocks for both contracts
2. Calculate daily block boundaries
3. Fetch NFT Transfer events
4. Fetch Pilot Vault Transfer events
5. Reconstruct daily states
6. Calculate daily points
7. Aggregate points across all days
8. Run test suite
9. Copy latest aggregated points to latest folder

### Docker

Build and run using Docker:

```bash
docker build -t ltv-points .
docker run ltv-points
```

## Links

- **Website**: [LTV](https://ltv.finance)
- **Protocol implementation**: [GitHub Repository](https://github.com/ltvprotocol/ltv_v0)
- **Documentation**: [Protocol Documentation](https://docs.ltv.finance)
- **Twitter**: [@ltvprotocol](https://x.com/ltvprotocol)