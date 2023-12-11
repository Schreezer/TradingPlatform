# Decentralised Zero Day Futures Trading Platform

This application is a decentralized zero-day futures trading platform built on the Aptos blockchain. It consists of a front-end and a back-end.

## Front-end
The front-end is built using React and Chakra UI. Users can register for the platform, choose trading contracts, submit market or limit orders, view the order book, and analyze price charts. The front-end also includes error handling and validation for user inputs to ensure a smooth trading experience.

### Market Page
The market page allows users to enter the size of their order and execute buy or sell actions. It provides real-time feedback on the transaction status and any encountered errors. Along with the Candle-Stick chart, which shows the historical prices.

### Table Component
The table component displays transaction data, including the status of transactions (e.g., "Unsold" or "Sold"), prices, sizes, and other relevant information. It also provides filtering and formatting options for enhanced user experience.

### User Registration
Users can register for the platform by signing a transaction from their Aptos wallet.

### Order Submission
Users can submit market or limit orders, specifying the size and type of order.

### Transaction Processing
The back-end processes user transactions, handles error cases, and updates the order book and price chart accordingly.

# Smart Contract
The Smart Contract has the modules as:

## Trading Platform Module

This repository contains the code for a trading platform module written in Move, a programming language for the Libra blockchain. The module provides APIs for trading and managing orders, positions, and user resources.

### File Structure

The code is organized into multiple files within the `move/sources` directory. The main file is `tradingPlatform.move`, which contains the core logic for the trading platform module. It includes functions for initializing the module, registering users, creating orders, matching buy and sell orders, and managing user resources.

### Testing

The code includes a comprehensive set of test functions that cover various aspects of the trading platform module. These tests ensure that the functionality of the module is thoroughly validated.

### Usage

To use this trading platform module, developers can integrate it into their own Move-based projects. The provided APIs can be leveraged to enable trading of assets on the Libra blockchain.

## Order Module

The `order.move` file contains functions for managing orders and order heaps in the trading platform module. It includes functions for adding orders to a timestamp heap, popping orders from a timestamp heap, inserting orders into a price level heap, and accessing order information.

### Functions
- `add_to_timestamp_heap(vec: &mut vector<u64>, order: u64)`: Adds an order to a timestamp heap.
- `pop_from_timestamp_heap(vec: &mut vector<u64>)`: Pops an order from a timestamp heap.
- `insert_assuming_no_repeat(heap: &mut OrderHeap, price_level: PriceLevel)`: Inserts an order into a price level heap.
- `head_pricelevel(heap: &OrderHeap)`: Retrieves the head price level from a heap.

### Test Functions
The file also includes test functions to validate the functionality of the order module. These test functions cover scenarios such as heap matching, handling orders with the same prices, and managing orders with different prices.

### Getters and Setters
The file provides getters and setters for the `constants::Order` type, allowing access to order attributes such as price, units, state, type, position, timestamp, and flexibility.

### Test Initialization
The `initialize_module` function is used to initialize the module for testing purposes.

For any questions or issues, please contact the maintainers of this repository.

## Position Module

The `position.move` file contains functions for managing positions in the trading platform module. It includes functions for initializing the position module, opening a new position, depositing margin, checking expiration, and accessing position details.

### Position Structure
The `Position` struct represents a position with attributes such as position ID, order ID, type, strike price, strike units, margin deposits, and expiration time.

### PositionStore Structure
The `PositionStore` struct contains a table of positions and an ID for position management.

### Functions
- `init_module`: Initializes the position module.
- `open_position`: Opens a new position with specified parameters.
- `deposit_margin`: Deposits margin for a position.
- `is_expired`: Checks if a position has expired.
- `is_long`: Checks if a position is of type Long.
- `strike_price`: Retrieves the strike price of a position.
- `strike_units`: Retrieves the strike units of a position.
- `order`: Retrieves the order ID associated with a position.
- `margin_deposits`: Retrieves the margin deposits of a position.
- `fetch_position_ref`: Retrieves a reference to a position.
- `fetch_position_ref_mut`: Retrieves a mutable reference to a position.

### Test Initialization
The `initialize_module` function is used to initialize the module for testing purposes.

For any questions or issues, please contact the maintainers of this repository.
