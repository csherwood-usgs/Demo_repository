### Building SWASH per the README.md in https://gitlab.tudelft.nl/citg/wavemodels/swash  
```
(base) [csherwood@pn124 build]$ module list
Currently Loaded Modulefiles:
 1) slurm/17.11.12   2) default-environment   3) impi/2018.2.199   4) intel/2018   5) cmake/3.20.2   6) stack/impi/1.0
(base) [csherwood@pn124 build]$ cmake .. -DCMAKE_Fortran_COMPILER=mpiifort -DMPI=on
-- Configuring done
You have changed variables that require your cache to be deleted.
Configure will be re-run and you may have to reset some variables.
The following variables have changed:
CMAKE_Fortran_COMPILER= mpiifort

-- The Fortran compiler identification is Intel 18.0.2.20180210
-- Detecting Fortran compiler ABI info
-- Detecting Fortran compiler ABI info - done
-- Check for working Fortran compiler: /vortexfs1/apps/intel/compilers_and_libraries_2018.2.199/linux/mpi/intel64/bin/mpiifort - skipped
-- Checking whether /vortexfs1/apps/intel/compilers_and_libraries_2018.2.199/linux/mpi/intel64/bin/mpiifort supports Fortran 90
-- Checking whether /vortexfs1/apps/intel/compilers_and_libraries_2018.2.199/linux/mpi/intel64/bin/mpiifort supports Fortran 90 - yes
-- Found Perl: /usr/bin/perl (found version "5.16.3")
-- Configuring done
-- Generating done
-- Build files have been written to: /vortexfs1/home/csherwood/src/swash/build
(base) [csherwood@pn124 build]$ make
Scanning dependencies of target swash8.01
[  1%] Building Fortran object lib/CMakeFiles/swash8.01.dir/SwanCompdata.f90.o
[  1%] Building Fortran object lib/CMakeFiles/swash8.01.dir/SwanGriddata.f90.o
[  2%] Building Fortran object lib/CMakeFiles/swash8.01.dir/SwanGridobjects.f90.o
...
[ 98%] Building Fortran object lib/CMakeFiles/swash8.01.dir/sparskit2.f.o
[ 99%] Linking Fortran static library libswash8.01.a
[ 99%] Built target swash8.01
Scanning dependencies of target swash.exe
[ 99%] Building Fortran object lib/CMakeFiles/swash.exe.dir/Swash.f90.o
[100%] Linking Fortran executable ../bin/swash.exe
[100%] Built target swash.exe
(base) [csherwood@pn124 build]$ ls bin
CMakeFiles  cmake_install.cmake  Makefile  swash.exe
```
This version runs in MPI (errors are because there is no input file)  
```
(base) [csherwood@pn124 bin]$ mpirun -np 4 ./swash.exe
application called MPI_Abort(MPI_COMM_WORLD, 4) - process 2
application called MPI_Abort(MPI_COMM_WORLD, 4) - process 0
application called MPI_Abort(MPI_COMM_WORLD, 4) - process 1
application called MPI_Abort(MPI_COMM_WORLD, 4) - process 3
(base) [csherwood@pn124 bin]$ ls
CMakeFiles           Errfile      Errfile-002  Errfile-004  PRINT      PRINT-002  PRINT-004  swashinit
cmake_install.cmake  Errfile-001  Errfile-003  Makefile     PRINT-001  PRINT-003  swash.exe
```
