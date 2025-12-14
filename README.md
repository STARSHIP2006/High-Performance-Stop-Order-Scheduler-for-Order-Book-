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


## Build and Run

### Prerequisites

- C++ compiler with C++17/C++20 support  
  (GCC ≥ 10 / Clang ≥ 10 / MSVC ≥ 2019)
- CMake ≥ 3.10
- make or ninja

---

### Clone Repository

```bash
git clone https://github.com/STARSHIP2006/High-Performance-Stop-Order-Scheduler-for-Order-Book-.git
cd High-Performance-Stop-Order-Scheduler-for-Order-Book-
```

Compile
======

```bash
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
cmake --build . --config Release
```

Run
===
```bash
./StopOrderScheduler
```

If the executable is generated inside the build directory:
```bash
./build/StopOrderScheduler
```

Example Run With Arguments
==========================
```bash
./build/StopOrderScheduler \
  --input examples/orders.csv \
  --config examples/config.json \
  --threads 4
```

Command Line Options
====================

```bash
--input <file>     Input order stream  
--config <file>    Scheduler configuration  
--threads <n>      Number of worker threads  
--help             Display usage information  
```

Clean Build
===========

```bash
rm -rf build
```


License
=======

MIT License
> This repository is a personal project focused on concurrency, data structures, and performance engineering in quantitative systems.
