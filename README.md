# CMake Tutorial

## Overview

This repository contains a series of CMake projects designed to help you learn and understand various aspects of CMake, including project generation, build configurations, testing, and tooling.

## Requirements

- **CMake**: 3.10 or later
- **GCC/Clang**: 7.0 or later
- **Doxygen**: 1.8.15 or later
- **gcovr/lcov**: For code coverage analysis
- **Python**: 3.6 or later (for Doxygen documentation generation)

## Installation

To set up the environment, follow these steps:

```bash
# Install required tools and dependencies
sudo apt-get update
sudo apt-get install cmake gcc g++ doxygen gcovr lcov python3

# Clone the repository
git clone https://github.com/PartORG/cmake-udemy-course.git
cd cmake-udemy-course

# Prepare the build directory
make prepare

# Generate the project
make dependency

# Build the project in Release mode
cmake -DCMAKE_BUILD_TYPE=Release ..
make install
make install_doc
```

## Usage

To run the projects, use the following commands:

```bash
# Navigate to the build directory
cd build

# Build a specific target (e.g., ExternalLibraries_Executable)
cmake --build . --target ExternalLibraries_Executable

# Run the executable
./bin/ExternalLibraries_Executable
```

For more detailed instructions on each project, refer to the individual `CMakeLists.txt` files in the respective directories.