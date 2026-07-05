# CMake, Testing and Tooling for C/C++

A comprehensive guide to mastering CMake, testing frameworks, and development tools for C++ projects. This course covers essential topics from basic project setup to advanced techniques like unit testing, code coverage, and static analysis.

## Table of Contents

- [Features](#features)
- [How It Works](#how-it-works)
- [Technology Stack](#technology-stack)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Development](#development)
- [Testing](#testing)
- [Limitations](#limitations)
- [License](#license)

## Features

### Comprehensive CMake Tutorial
Learn how to generate, configure, and build projects using CMake.

### Detailed Testing Frameworks
Explore various testing frameworks like Google Test, Catch2, and Boost.Test.

### Code Coverage Analysis
Understand how to measure code coverage with tools like gcovr and lcov.

### Static Analysis Tools
Discover static analysis tools for better code quality and security.

## How It Works

CMake is a cross-platform build system generator. It allows you to write platform-independent build scripts in CMakeLists.txt files, which are then processed by the CMake engine to generate native build files (e.g., Makefiles, Visual Studio projects).

## Technology Stack

| Technology | Purpose |
|------------|---------|
| CMake      | Cross-platform build system generator. |
| Google Test| Unit testing framework for C++. |
| Catch2     | Another unit testing framework for C++. |
| Boost.Test   | A comprehensive testing framework for C++. |
| gcovr      | Code coverage tool using GCC's gcov. |
| lcov         | Tool to generate code coverage reports. |
| Doxygen      | Documentation generator for C++ projects. |

## Requirements

- CMake 3.10 or later
- A C++ compiler (GCC, Clang, MSVC)
- Python 3.x (for generating documentation)

## Installation

### Using Git

```bash
git clone https://github.com/PartORG/cmake-udemy-course.git
cd cmake-udemy-course
```

### Using Package Manager

For Debian-based systems:

```bash
sudo apt-get install cmake g++ python3
```

For macOS using Homebrew:

```bash
brew install cmake gcc python3
```

## Configuration

The project uses several configuration files to manage build settings and dependencies. Key files include:

- `.clang-format`: Clang formatting rules.
- `.clang-tidy`: Clang static analysis rules.
- `.cmake-format.yaml`: CMake formatting rules.
- `.editorconfig`: Editor configuration for consistent code style.

## Quick Start

### Generating a Project

```bash
mkdir build
cd build
cmake -S .. -B .
```

### Building the Project

```bash
make
```

### Running Tests

```bash
ctest
```

### Generating Documentation

```bash
doxygen docs/Doxyfile
```

## Usage

### Basic Commands

- `make dependency`: Generates a dependency graph.
- `make prepare`: Cleans up build directories.
- `make install`: Installs necessary tools (e.g., gcovr, lcov).
- `make install_doc`: Installs documentation generation tools.

### Running Executables

```bash
./bin/ExternalLibraries_Executable
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
    ├── .gitignore
    ├── .gitmodules
    ├── CMakeLists.txt
    ├── Makefile
    ├── app/
    │   └── CMakeLists.txt
    ├── cmake/
    │   ├── AddGitSubmodule.cmake
    │   ├── CPM.cmake
    │   ├── Docs.cmake
    │   └── LTO.cmake
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

## Development

### Code Formatting

```bash
clang-format -i --style=file .
```

### Static Analysis

```bash
clang-tidy --checks=* src/*.cpp
```

### Running Tests

```bash
ctest
```

### Generating Documentation

```bash
doxygen docs/Doxyfile
```

## Testing

The project includes several testing frameworks to ensure code quality. Key tests include:

- Unit tests using Google Test and Catch2.
- Code coverage analysis with gcovr and lcov.

## Limitations

- Limited support for Windows-specific features.
- No cross-platform GUI development covered.

## License

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
```