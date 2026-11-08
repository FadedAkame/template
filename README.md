# Template
template

## Requirements
- **C++ Compiler (GCC or Clang)**
- **CMake + Ninja**
- **Neovim + Clangd**

## Config & Building
Configure CMake
```
cmake -S . -B build -G Ninja
```
Some optional flags are
```-DCMAKE_BUILD_TYPE=(Debug, Release, RelWithDebInfo, MinSizeRel)```
and
```-DTOGGLE_ASAN=(On, Off)```

Build & run project
```
./run.sh (project_args)
```
