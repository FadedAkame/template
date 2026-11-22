# Template
placeholder

## Requirements
- **OS:** Linux
- **Compiler:** GCC w/ C++23 support
- **Build System:** CMake + Ninja

## Config & Building
Configure CMake
An optional flag is ```-DENABLE_SANITIZERS=On```
```
cmake -S . -B build -G Ninja
```
Build & run project
```
./run.sh (args)
```
