# build2 Package for NanoRT

This project is a [build2](https://build2.org) package repository that provides access to [NanoRT](https://github.com/lighttransport/nanort), a modern C++ ray tracing kernel library.

[![Official](https://img.shields.io/website/https/github.com/lighttransport/nanort.svg?down_message=offline&label=Official&style=for-the-badge&up_color=blue&up_message=online)](https://github.com/lighttransport/nanort)
[![build2](https://img.shields.io/website/https/github.com/build2-packaging/nanort.svg?down_message=offline&label=build2&style=for-the-badge&up_color=blue&up_message=online)](https://github.com/build2-packaging/nanort)
[![cppget.org](https://img.shields.io/website/https/cppget.org/libnanort.svg?down_message=offline&label=cppget.org&style=for-the-badge&up_color=blue&up_message=online)](https://cppget.org/libnanort)
[![queue.cppget.org](https://img.shields.io/website/https/queue.cppget.org/libnanort.svg?down_message=empty&down_color=blue&label=queue.cppget.org&style=for-the-badge&up_color=orange&up_message=running)](https://queue.cppget.org/libnanort)

## Usage
As NanoRT does not provide any versioning scheme, make sure to add the alpha section of the `cppget.org` repository to your project's `repositories.manifest` to be able to fetch this package.

    :
    role: prerequisite
    location: https://pkg.cppget.org/1/alpha
    # trust: ...

If the alpha section of `cppget.org` is not an option then add this Git repository itself instead as a prerequisite.

    :
    role: prerequisite
    location: https://github.com/build2-packaging/nanort.git

Add the respective dependency in your project's `manifest` file to make the package available for import.

    depends: libnanort ^0.0.2

Then use the following line in your `buildfile` to import the library.

    import nanort = libnanort%lib{nanort}

After declaring the library as a dependency to your required target, use one of the following inclusion schemes to include the library in a C++ source file.

```c++
#include <nanort.h>
#include <nanort/nanort.h>
```

## Configuration
There are no configuration options available.

## Issues and Notes
- The upstream repository does not provide any unit testing but instead focuses on examples. These examples are much more involved and have not been added to the examples package, yet. So far, only smoke tests are used to test the library inclusion.
- As NanoRT is a single-header-only library, there seems to be no standard inclusion scheme. Some projects use `#include "nanort.h"` and some use `#include "nanort/nanort.h"`. As such, both inclusion schemes are made available when importing this package.

## Contributing
Thank you in advance for your help and contribution to keep this package up-to-date.
Please, file an issue on [GitHub](https://github.com/build2-packaging/nanort/issues) for questions, bug reports, or to recommend updating the package version.
If you're making a pull request to fix bugs or update the package version yourself, refer to the [`build2` Packaging Guidelines](https://build2.org/build2-toolchain/doc/build2-toolchain-packaging.xhtml#core-version-management).
