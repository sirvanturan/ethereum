evmone is a C++ implementation of the Ethereum Virtual Machine (EVM). Created by members of the Ewasm team, the project aims for clean, standalone EVM implementation that can be imported as an execution module by Ethereum Client projects. The codebase of evmone is optimized to provide fast and efficient execution of EVM smart contracts.

Characteristic of evmone
Exposes the EVMC API.
Requires C++17 standard.
The intx library is used to provide 256-bit integer precision.
The ethash library is used to provide Keccak hash function implementation needed for the special KECCAK256 instruction.
Contains two interpreters: Advanced (default) and Baseline (experimental).
Advanced Interpreter
The indirect call threading is the dispatch method used - a loaded EVM program is a table with pointers to functions implementing virtual instructions.
The gas cost and stack requirements of block of instructions is precomputed and applied once per block during execution.
Performs extensive and expensive bytecode analysis before execution.
Baseline Interpreter
Provides relatively straight-forward EVM implementation.
Performs only minimalistic JUMPDEST analysis.
Experimental. Can be enabled with O=0 option.


As geth plugin
evmone implements the EVMC API for Ethereum Virtual Machines. It can be used as a plugin replacing geth's internal EVM. But for that a modified version of geth is needed. The Ewasm's fork of go-ethereum provides binary releases of geth with EVMC support.

Next, download evmone from Releases.

Start the downloaded geth with --vm.evm option pointing to the evmone shared library.

geth --vm.evm=./libevmone.so
