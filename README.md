# OrderBook

**OrderBook** is a high-performance, concurrent order book engine implemented in **C++**, designed with a focus on **low-latency trading** and **scalable order processing**. The project explores core mechanisms used in modern financial exchange systems, emphasizing concurrency, correctness, and performance.

## Key Features
- Concurrent order processing using **Intel Threading Building Blocks (TBB)**
- Support for multiple order types: **Limit, Market, IOC**, with extensibility for stop orders
- Asynchronous matching with separate buy/sell processing to reduce lock contention
- **Price–time priority** management  
  - Buy orders sorted by descending price  
  - Sell orders sorted by ascending price
- Fast order modification and cancellation via TBB concurrent containers
- Latency and throughput benchmarking for performance validation

## Design Overview
- `std::map`-based bid/ask price levels
- `tbb::concurrent_hash_map` and `tbb::concurrent_queue` for parallel ingestion and matching
- Modular architecture enabling future extensions (partial fills, advanced order types, improved matching)

## Use Cases
- Experimentation with high-performance trading system components
- Educational reference for order book mechanics and concurrent C++ design
- Foundation for advanced matching engines or trading simulators

## Contents
- Core order book and scheduler implementation
- Example main driver
- Comprehensive test suite
- Catch-based unit tests

> This repository is a personal project focused on concurrency, data structures, and performance engineering in quantitative systems.
