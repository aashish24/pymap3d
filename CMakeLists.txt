cmake_minimum_required(VERSION 2.8.12)
project(MapTran Fortran)

add_compile_options(-ffpe-trap=invalid,zero,overflow -g -fbacktrace 
                    -Wall -Wextra -Warray-bounds)# -Wfatal-errors)

add_library(maptran fortran/maptran.f90 fortran/vallado.f90 fortran/assert.f90 )

add_executable(testmaptran fortran/Test.f90)
target_link_libraries(testmaptran maptran)
