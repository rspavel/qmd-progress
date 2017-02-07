[![Build Status](https://travis-ci.org/lanl/qmd-progress.svg?branch=master)](https://travis-ci.org/lanl/qmd-progress)

A library for quantum chemistry solvers.
=======================================

PROGRESS: Parallel, Rapid O(N) and Graph-based Recursive Electronic Structure Solver. LACC Number: LA-CC-16-068

  - This library is focused on the development of general solvers that are
  commonly used in _quantum chemistry packages_.

  - This library has to be compiled with the _Basic Matrix Library_  (BML). The BML can be downloaded from:
[BML](https://github.com/qmmd/bml)


Authors:
Anders M. N. Niklasson (<amn@lanl.gov>);
Christian F. A. Negre (<cnegre@lanl.gov>);
Marc J. Cawkwell (<cawkwell@lanl.gov>);
Nicolas Bock (<nbock@lanl.gov>);
Susan M. Mniszewski (<smm@lanl.gov>);
Michael E. Wall (<mewall@lanl.gov>)

Los Alamos National Laboratory 2015

***


## How to build:

    PKG_CONFIG_PATH=<BML install path>/lib64/pkgconfig ./build.sh

You can use:

    locate bml.pc
or

    sudo find / | grep bml.pc

to find the pkgconfig folder path.

## How to install:

    cd build
    $ sudo make install

To specify intel fortran compiler:

    FC=ifort PKG_CONFIG_PATH=<BML install path>/lib64/pkgconfig ./build.sh

To build with the gfortran compiler and OpenMP:

    CC=gcc FC=gfortran CMAKE_BUILD_TYPE=Release PROGRESS_OPENMP=yes PKG_CONFIG_PATH=<BML install path>/lib64/pkgconfig CMAKE_INSTALL_PREFIX=<PROGRESS install path> ./build.sh configure

To build with OpenMP and MPI and testing enabled:

   CC=mpicc FC=mpif90 CMAKE_BUILD_TYPE=Release PROGRESS_OPENMP=yes PROGRESS_MPI=yes PROGRESS_TESTING=yes PKG_CONFIG_PATH=<BML install path>/lib64/pkgconfig CMAKE_INSTALL_PREFIX=<PROGRESS install path> ./build.sh configure

To build with OpenMP and MPI and testing enabled and example programs built:

   CC=mpicc FC=mpif90 CMAKE_BUILD_TYPE=Release PROGRESS_OPENMP=yes PROGRESS_MPI=yes PROGRESS_TESTING=yes  PROGRESS_EXAMPLES=yes PKG_CONFIG_PATH=<BML install path>/lib64/pkgconfig CMAKE_INSTALL_PREFIX=<PROGRESS install path> ./build.sh configure

To build with OpenMP and MPI and testing enabled and example programs built and the METIS graph partitioning library:

   CC=mpicc FC=mpif90 CMAKE_BUILD_TYPE=Release PROGRESS_OPENMP=yes PROGRESS_MPI=yes PROGRESS_GRAPHLIB=yes PROGRESS_TESTING=yes PROGRESS_EXAMPLES=yes PKG_CONFIG_PATH=<BML install path>/lib64/pkgconfig CMAKE_INSTALL_PREFIX=<PROGRESS install path> EXTRA_LINK_FLAGS="-L<metis directory> -lmetis" ./build.sh configure


![Caption text](/home/christian/progress/docs/images/image.gif "Image title")
