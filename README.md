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
