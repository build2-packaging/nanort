# NanoRT - Ray Tracing Kernel

This is the `build2` package for NanoRT, a single header only modern ray tracing kernel.

## Usage
To use this package in your project, add the following configurations to the respective files after you have gained access to a `build2` package repository that contains it.

### `manifest`
To make NanoRT available for import, add the following dependency to the `manifest` of each package in your project that requires it, adjusting the version constraint as appropriate.

    depends: libnanort ^0.0.3

### `buildfile`
To import the library, use the following declaration in your `buildfile`.

    import nanort = libnanort%lib{nanort}

### C++ Header Inclusion
Finally, include the necessary header in your C++ source code.
This package provides a direct and a prefixed version for the include path.
Note that NanoRT's configuration can be controlled by defining preprocessor macros before including its header.
However, the most robust way to do this project-wide is in your `buildfile`.

```c++
#include <nanort.h>         // Direct Inclusion
#include <nanort/nanort.h>  // Prefixed Inclusion
```

## Configuration
Currently, there are no configuration variables available.
For controlling library features, refer to NanoRT's preprocessor macros.
