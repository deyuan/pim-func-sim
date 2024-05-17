## PIM Functional Simulator

Copyright 2024 LavaLab @ University of Virginia. All rights reserved.

### Description

* This is a PIM functional simulator that can simulate various PIM devices, cores, resource allocation, and command execution
* This provides a C/C++ compatible library for PIM application development

### How To Build
* Run `make` at `pim-func-sim` root directory or subdirectories. Support three targets:
  * `make debug`: Build with `-g` and `-DDEBUG` for debugging and printing verbose messages
  * `make perf`: Build with `-O3` for performance measurement
  * `make dramsim3_integ`: Enable DRAMsim3 related code with `-DDRAMSIM3_INTEG`

### Code Architecture
* libpimsim
  * `src`: PIM functional simualtor source code
  * `include/libpimsim.h`: Public header file (after make)
  * `lib/libpimsim.a`: PIM functional simulator library (after make)
* apps
  * `cpp-vec-add`: Vector addition
  * `cpp-vec-arithmetic`: Vector arithmetic
  * `cpp-vec-comp`: Vector comparison
  * `cpp-vec-logical`: Vector logical operations
  * `cpp-vec-broadcast-popcnt`: Vector broadcast and pop count
  * `cpp-gemv`: General matric-vector product
  * `cpp-sad`: Sum of absolute difference
  * `cpp-pooling`: Max pooling
  * `cpp-convolution`: Convolution
  * `cpp-linear-regression`: Linear regression
  * `cpp-aes`: AES encryption
  * `cpp-radix-sort`: Radix sort

### About DRAMsim3 Integration
* This module contains a copy of DRAMsim3
  * Oringal DRAMsim3 repo: https://github.com/umd-memsys/DRAMsim3
  * Clone date: 05/06/2024
  * Location: ./libpimsim/DRAMsim3/
* DRAMsim3 related code are guarded with DRAMSIM3_INTEG flag
  * Requires `make dramsim3_integ`
* Below is needed for dramsim3_integ for now
```bash
# Build dramsim3
git clone https://github.com/fasiddique/DRAMsim3.git
cd DRAMsim3/
git checkout benchmark
mkdir build
cd build
cmake ..
make -j
# Build PIM functional simulator
git clone <url_to_this_repo>
cd pim-func-sim
export DRAMSIM3_PATH=<path_to_DRAMSIM3>
make -j
```

### Contributors
* Deyuan Guo
* Farzana Siddique
* Mohammadhosein Gholamrezaei
* Zhenxing Fan

