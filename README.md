# CMake Tutorial

A comprehensive guide to using CMake for building and managing C/C++ projects, including advanced topics like testing, documentation, and tooling.

## Introduction

CMake is a powerful build system generator that simplifies the process of building software across different platforms. This repository provides hands-on examples and explanations for various CMake topics, making it an ideal resource for developers looking to deepen their understanding of CMake.

## Features

- **CMake-based project structure**: Organized into multiple directories covering different aspects of CMake usage.
- **Multiple CMake topics covered**: From basic projects to advanced features like external dependencies and testing.
- **Use of Makefile for build commands**: Demonstrates how to use Makefiles alongside CMake.
- **Support for different build types**: Includes examples for Debug, Release, and other custom build configurations.
- **Options to pass values during the build process**: Shows how to set options in the command line.
- **Target-specific builds**: Explains how to build specific targets using `cmake --build` or `make`.
- **Different linking types**: Covers PUBLIC, PRIVATE, and INTERFACE linkages.

## How It Works

CMake generates platform-specific build files (e.g., Makefiles, Visual Studio projects) based on the project's configuration. The workflow involves:

1. **Generating a Project**: Use `cmake` to generate the build system.
2. **Building the Project**: Compile the source code using the generated build files.
3. **Running Tests**: Execute tests to ensure the project works as expected.

## Technology Stack

| Technology | Purpose |
|------------|---------|
| CMake      | Build system generator for cross-platform development. |
| Makefile   | Used alongside CMake for building projects. |
| GCC/Clang  | Compilers for generating executable binaries. |
| MSVC       | Microsoft Visual C++ compiler (for Windows). |
| Doxygen    | Documentation generator for C/C++. |
| gcovr/lcov | Code coverage tools. |
| jinja2     | Python library for templating. |
| Pygments   | Syntax highlighting library for documentation. |

## Requirements

- **CMake**: Version 3.10 or later.
- **Compiler**: GCC, Clang, or MSVC.

## Installation

To install the necessary tools:

```bash
sudo apt-get update
sudo apt-get install cmake make gcc g++ doxygen gcovr lcov python3-jinja2 python3-pygments
```

## Configuration

The project uses CMake for building and managing dependencies. Build configurations include options for different compilers, build types, and target selection.

## Quick Start

1. **Generate the Project**:

    ```bash
    mkdir build
    cd build
    cmake -S .. -B .
    ```

2. **Build the Project**:

    ```bash
    make
    ```

3. **Run the Executable**:

    ```bash
    ./bin/ExternalLibraries_Executable
    ```

## Usage

### Building a Specific Target

To build a specific target, use `cmake --build` or `make`:

```bash
cmake --build . --target ExternalLibraries_Executable
```

or

```bash
make ExternalLibraries_Executable
```

### Passing Options

You can pass options during the build process using `-D` flags:

```bash
cmake -DCMAKE_BUILD_TYPE=Release ..
```

## Project Structure

```
CMake_Topics/
├── 01_HelloWorld/
│   ├── CMakeLists.txt
│   └── main.cc
├── 02_BasicProject/
│   ├── CMakeLists.txt
│   ├── main.cc
│   ├── my_lib.cc
│   └── my_lib.h
├── 03_IntermediateProject/
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   └── CMakeLists.txt
├── 04_VariablesOptions/
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   └── CMakeLists.txt
├── 05_ConfigureFile/
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   └── CMakeLists.txt
├── 06_SourcesAndHeaders/
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   └── CMakeLists.txt
├── 07_ExternalGit/
│   ├── .gitmodules
│   ├── CMakeLists.txt
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── cmake/
│   │   └── AddGitSubmodule.cmake
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── external/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   └── CMakeLists.txt
├── 08_FetchContent/
│   ├── .gitmodules
│   ├── CMakeLists.txt
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── cmake/
│   │   └── AddGitSubmodule.cmake
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── external/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   └── CMakeLists.txt
├── 09_Doxygen/
│   ├── .gitmodules
│   ├── CMakeLists.txt
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── cmake/
│   │   ├── AddGitSubmodule.cmake
│   │   └── Docs.cmake
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── docs/
│   │   └── Doxyfile
│   ├── external/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   └── CMakeLists.txt
├── 10_UnitTest/
│   ├── .gitignore
│   ├── .gitmodules
│   ├── CMakeLists.txt
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── cmake/
│   │   ├── AddGitSubmodule.cmake
│   │   ├── Docs.cmake
│   │   └── Warnings.cmake
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── docs/
│   │   └── Doxyfile
│   ├── external/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   ├── tests/
│   │   ├── CMakeLists.txt
│   │   └── main.cc
│   └── CMakeLists.txt
├── 11_Warnings/
│   ├── .gitignore
│   ├── .gitmodules
│   ├── CMakeLists.txt
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── cmake/
│   │   ├── AddGitSubmodule.cmake
│   │   ├── Docs.cmake
│   │   └── Warnings.cmake
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── docs/
│   │   └── Doxyfile
│   ├── external/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   ├── tests/
│   │   ├── CMakeLists.txt
│   │   └── main.cc
│   └── CMakeLists.txt
├── 12_Sanitizers/
│   ├── .gitignore
│   ├── .gitmodules
│   ├── CMakeLists.txt
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── cmake/
│   │   ├── AddGitSubmodule.cmake
│   │   ├── Docs.cmake
│   │   └── Sanitizer.cmake
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── docs/
│   │   └── Doxyfile
│   ├── external/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   ├── tests/
│   │   ├── CMakeLists.txt
│   │   └── main.cc
│   └── CMakeLists.txt
├── 13_LTO/
│   ├── .gitignore
│   ├── .gitmodules
│   ├── CMakeLists.txt
│   ├── Makefile
│   ├── app/
│   │   └── CMakeLists.txt
│   ├── cmake/
│   │   ├── AddGitSubmodule.cmake
│   │   ├── Docs.cmake
│   │   └── LTO.cmake
│   ├── configured/
│   │   ├── CMakeLists.txt
│   │   └── config.hpp.in
│   ├── docs/
│   │   └── Doxyfile
│   ├── external/
│   │   └── CMakeLists.txt
│   ├── src/
│   │   ├── CMakeLists.txt
│   │   └── my_lib/
│   │       ├── CMakeLists.txt
│   │       ├── my_lib.cc
│   │       └── my_lib.h
│   ├── tests/
│   │   ├── CMakeLists.txt
│   │   └── main.cc
│   └── CMakeLists.txt
└── 14_CPM/
    ├── .gitmodules
    ├── CMakeLists.txt
    ├── Makefile
    ├── app/
    │   └── CMakeLists.txt
    ├── cmake/
    │   ├── AddGitSubmodule.cmake
    │   ├── Docs.cmake
    │   └── Warnings.cmake
    ├── configured/
    │   ├── CMakeLists.txt
    │   └── config.hpp.in
    ├── docs/
    │   └── Doxyfile
    ├── external/
    │   └── CMakeLists.txt
    ├── src/
    │   ├── CMakeLists.txt
    │   └── my_lib/
    │       ├── CMakeLists.txt
    │       ├── my_lib.cc
    │       └── my_lib.h
    ├── tests/
    │   ├── CMakeLists.txt
    │   └── main.cc
    └── CMakeLists.txt
```

## LICENSE

MIT License

Copyright (c) 2022 Jan Schaffranek

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.