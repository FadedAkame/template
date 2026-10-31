# template
this repo is a quick setup for Linux C++ projects using CMake & neovim w/ clangd

## dependencies
 - C++ compiler (GCC/Clang)
 - CMake
 - neovim (w/ clangd as the lsp)
 - clang-format

## usage
simply git clone this project with your project name.
```
git clone https://github.com/FadedAkame/template.git myProject
cd myProject
```
configure & build the project.
```
cmake -B build
./run.sh {program_args}
```

## config
enter both *run.sh* and *CMakeLists.txt* to configure build settings like ASan, compiler flags & project/exe name.

other than that unless I missed something, you may configure or change anything else this was for me because I was lazy to keep remaking CMakeLists.
