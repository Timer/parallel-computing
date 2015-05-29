# Prerequisites
On [Blue Waters](https://bluewaters.ncsa.illinois.edu/), running `module load cudatoolkit` is required to attach modules to the current login session.
###### When compiling
On [Blue Waters](https://bluewaters.ncsa.illinois.edu/), you must compile with `cc` and `nvcc`, and `nvcc` must be invoked with  `nvcc -arch sm_13 [...]`.
# Core functionality
Cores which are running the same task *always* run in lock step.
This means operations such as branches or jumps are *permitted* but **highly** discouraged.
# Common Gotchas
Exceeding the number of threads will result in junk, but not error.

So, carefully execute work while respecting the number of available threads in a block, and the number of blocks in a grid, by splitting for overages.
