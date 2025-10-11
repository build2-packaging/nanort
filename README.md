# build2 Package Repository for NanoRT

This is the [build2](https://build2.org) package repository for [NanoRT](https://github.com/lighttransport/nanort), a modern C++ ray tracing kernel library.

This repository is a community-maintained effort and is not officially endorsed by the NanoRT authors.

| Package | Summary | Status |
|---|---|---|
| **[`libnanort`](libnanort/PACKAGE-README.md)** | C++ Ray Tracing Kernel | [![cppget.org](https://img.shields.io/website/https/cppget.org/libnanort.svg?down_message=offline&label=cppget.org&style=for-the-badge&up_color=blue&up_message=online)](https://cppget.org/libnanort) [![queue.cppget.org](https://img.shields.io/website/https/queue.cppget.org/libnanort.svg?down_message=empty&down_color=blue&label=queue.cppget.org&style=for-the-badge&up_color=orange&up_message=running)](https://queue.cppget.org/libnanort) |

## Usage
If you want to use the NanoRT in your `build2`-based project, add an appropriate repository manifest to your project's `repositories.manifest` and refer to [NanoRT's `PACKAGE-README`](libnanort/PACKAGE-README.md).

### `repositories.manifest`
To be able to fetch this repository's packages, add one of the following prerequisites to your project's `repositories.manifest`.

**Option A: `cppget.org` (Recommended)**

NanoRT offers no semantic version and as such resides in the [`alpha` section](https://cppget.org/?about#pkg%3Acppget.org%2Falpha) of `cppget.org` that you need to add:

    :
    role: prerequisite
    location: https://pkg.cppget.org/1/alpha
    # trust: ...

**Option B: Git Repository**

    :
    role: prerequisite
    location: https://github.com/build2-packaging/nanort.git

## Development Setup
The development setup for this repository uses the standard `bdep`-based workflow.
For general information and guidance on package maintenance, please see the [`build2` Documentation](https://build2.org/doc.xhtml).

First, clone the repository via SSH or HTTPS.

    git clone --recurse https://github.com/build2-packaging/nanort.git  # HTTPS
    git clone --recurse git@github.com:build2-packaging/nanort.git      # SSH

Inside the repository's directory, initialize your build configuration.

    bdep init -C @gcc cc config.cxx=g++ config.install.root=../.install config.dist.root=../.dist

Afterwards, use `b` or `bdep` to build, test, install, and distribute the packages.

## Issues and Notes
- The upstream repository does not provide any unit testing but instead focuses on examples. These examples are much more involved and have not been added to the examples package, yet. So far, only smoke tests are used to test the library inclusion.
- As NanoRT is a single-header-only library, there seems to be no standard inclusion scheme. Some projects use `#include "nanort.h"` and some use `#include "nanort/nanort.h"`. As such, both inclusion schemes are made available when importing this package.

## Contributing
Contributions are welcome and greatly appreciated!
Please start by [opening an issue](https://github.com/build2-packaging/nanort/issues) to report a bug, suggest an improvement, or request a version update.
This helps us coordinate efforts and avoid duplicate work.
You are then welcome to submit a [pull request](https://github.com/build2-packaging/nanort/pulls) that references the issue.
For guidance on package maintenance, please see the [`build2` Packaging Guidelines](https://build2.org/build2-toolchain/doc/build2-toolchain-packaging.xhtml).
