# modified-fftw
A corrected fftw source code for benchmarking purpose

This is based on the code developed by FFTW (http://fftw.org/). The copyright is: http://www.fftw.org/fftw3_doc/License-and-Copyright.html.
The latest code is in fftw repo: https://github.com/FFTW/fftw3.

## Installation

To build and install, follow the instructions of the fftw documents. We have used the following commands to build.

```
./configure --enable-threads --enable-openmp --enable-quad-precision
make
make install
```

## Why we change the code

The becnh program included in the test directory was not able to properly get the number of threads from the command-line. It can get it from the wisdom files. However, the defualt wisdom overrides the `nthreads` variable. We changes the code in order to fix it based on the number of core in CPU of our hardware.
