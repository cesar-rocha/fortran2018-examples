cmake_minimum_required(VERSION 3.7)
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release CACHE STRING "Debug or Release")
endif()
project(cmake Fortran)

if(CMAKE_VERSION VERSION_GREATER_EQUAL 3.14)
  include(CheckFortranSourceCompiles)
  check_fortran_source_compiles("program a; end program" FCOMP SRC_EXT F90)

  include(CheckFortranSourceRuns)
  check_fortran_source_runs("program a; end program" FRUN)
endif()
