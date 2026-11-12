cmake_minimum_required(VERSION 3.20)
project(project LANGUAGES CXX)

# Main settings
option(TOGGLE_ASAN  "Enable AddressSanitizer"           OFF)
option(TOGGLE_UBSAN "Enable UndefinedBehaviorSanitizer" OFF)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Main executable
file(GLOB_RECURSE SOURCE_FILES CONFIGURE_DEPENDS src/*.cpp)
add_executable(${PROJECT_NAME} ${SOURCE_FILES})
target_include_directories(${PROJECT_NAME} PRIVATE src)
target_compile_options(${PROJECT_NAME} PRIVATE
    -Werror
    -Wall
    -Wextra
    -Wpedantic
    -Wconversion
    -Wsign-conversion
    -Wshadow
    -Wformat=2
    -Wnull-dereference
    -Wdouble-promotion
)

# Optional ASan/UBSan
if(TOGGLE_ASAN)
    set(ASAN_FLAGS -fsanitize=address -fno-omit-frame-pointer)
    target_compile_options(${PROJECT_NAME} PRIVATE ${ASAN_FLAGS})
    target_link_options(${PROJECT_NAME} PRIVATE ${ASAN_FLAGS})
endif()
if(TOGGLE_UBSAN)
    set(UBSAN_FLAGS -fsanitize=undefined -fno-omit-frame-pointer)
    target_compile_options(${PROJECT_NAME} PRIVATE ${UBSAN_FLAGS})
    target_link_options(${PROJECT_NAME} PRIVATE ${UBSAN_FLAGS})
endif()
