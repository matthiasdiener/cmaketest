# cmaketest
This cmake project documents a cmake bug regarding OpenMP and IBM XL Fortran/C++.

Compiling this project with `CC=xlc_r CXX=xlC_r FC=xlf_r cmake ..` results in linking to `-lxlomp_ser`, which disables OpenMP in XL.

A workaround is to run cmake with explicit FFLAGS: `CC=xlc_r CXX=xlC_r FC=xlf_r FFLAGS="-qsmp=omp" cmake ..`

Bug report: https://gitlab.kitware.com/cmake/cmake/issues/18518
