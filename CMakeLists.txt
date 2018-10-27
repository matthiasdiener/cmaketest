project(ompxltest LANGUAGES C CXX Fortran)
cmake_minimum_required(VERSION 3.12)

include(FortranCInterface)
FortranCInterface_VERIFY(CXX)

include(FindOpenMP)
if(OPENMP_FOUND)
  set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} ${OpenMP_Fortran_FLAGS}")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
endif()

add_executable(ompxl t.cpp ompxl.f)
