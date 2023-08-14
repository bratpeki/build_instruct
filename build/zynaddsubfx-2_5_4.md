Most of the information needed is available in the [ZynAddSubFx repo](https://github.com/zynaddsubfx/zynaddsubfx/tree/c90b4a6d6ff76a5e20f6a9d204f6af451cf14c09).

# Build system

You must have `cmake` and `make`.

# Compilers

I can't find a list of compilers which are tested to compile ZynAddSubFx 2.5.4.
However, on my system, `gcc` >= 4.7 is required.
The compilation then relies on `g++11`.

# Libraries

The following libs are necessary:

- `fftw` 3.x.x - necessary for Fast Fourier computations
- `mxml` 2.5+
- `zlib`
- `JACK`

`fltk` 1.x.x (tested with 1.3.8) is optional, but perferred.

As of recently (Aug 2023), `mxml`'s latest version is 3.3.1.
Therefore, we will have to downgrade it in order to compile ZynAddSubFx 2.4.5.

You can install the libs with:

```sh
# You can use 'jack2' or 'pipewire-jack' instead of 'jack'
sudo pacman -S fltk fftw zlib jack

# From this folder we'll compile ZynAddSubFx and the downgraded version of 'mxml'
cd BUILD_FOLDER

# Getting 'mxml'
git clone https://github.com/michaelrsweet/mxml/
cd mxml
git checkout tags/release-2.5
./configure
make
```

# My build setup

We're aiming to make our build tree look like this:

```
BUILD_FOLDER
├── mxml
└── zynaddsubfx
```

So, make sure you're in `BUILD_FOLDER` and run the following.

```sh
# Getting ZynAddSubFx
git clone https://github.com/zynaddsubfx/zynaddsubfx
cd zynaddsubfx
git checkout tags/2.5.4
git submodule update --init
mkdir build
cd build
cmake .. -DCMAKE_PREFIX_PATH=../../mxml/
# In case you want to edit something else regarding the install, run 'ccmake .'
make -j4 # You can specify the number of parallel jobs you want
```

After that, the plugin and binary are available in `BUILD_FOLDER/zynaddsubfx/build/src`.
You can install everything onto your system using `make install`.

## Building issues

You might see this when running `git submodule update --init`:

```
fatal: unable to connect to github.com:
github.com[0: ...]: errno=Operation timed out
```

To fix this, run `git config --global url."https://".insteadOf git://` to fix the issue with the git port, which is usually restricted.

---

Another issue you might encounter when running `make -j4` is:

```
BUILD_FOLDER/zynaddsubfx/src/Misc/Bank.h:61:21: error: ‘uint8_t’ has not been declared
   61 |         void setMsb(uint8_t msb);
      |                     ^~~~~~~
```

To fix this, change the top of the file `BUILD_FOLDER/zynaddsubfx/src/Misc/Bank.h` to the following:

```c++
#ifndef BANK_H
#define BANK_H

#include <string>
#include <cstdint> // Add this line
#include <vector>
#include "../globals.h"
#include "Config.h"
```

This will introduce the missing datatypes.
