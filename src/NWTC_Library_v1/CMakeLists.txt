
set(NWTCLIBS_SOURCES NWTC_Library.f90 NWTC_IO.f90 NWTC_Num.f90 NWTC_Aero.f90
  ModMesh.f90 DoubPrec.f90)
set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -fPIC -ffree-line-length-none")
project(nwtclibs Fortran)
list (APPEND NWTCLIBS_SOURCES SysGnuLinux.f90)

add_library(nwtclibs  ${NWTCLIBS_SOURCES})
target_link_libraries(nwtclibs ${LAPACK_LIBRARIES} ${CMAKE_DL_LIBS})

install(TARGETS nwtclibs
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib)
