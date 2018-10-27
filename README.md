# cmaketest
Repo to document a cmake bug regarding OpenMP and IBM XL Fortran/C++

Compiling this project with `CC=xlc_r CXX=xlC_r FC=xlf_r cmake ..` results in linking to `-lxlomp_ser`, which disables OpenMP in XL.
