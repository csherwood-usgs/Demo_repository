***Building SWASH per the README.md in https://gitlab.tudelft.nl/citg/wavemodels/swash  

(base) [csherwood@poseidon-l2 ~]$ start_12
(base) [csherwood@pn124 ~]$ cd src
(base) [csherwood@pn124 src]$ ls
CoreBx_COAWST  environment.yml  swash
(base) [csherwood@pn124 src]$ cd swash
(base) [csherwood@pn124 swash]$ module avail
--------------------------------------------------------------- /cm/shared/whoi/default ----------------------------------------------------------------
bio  default-environment  slurm/17.11.2  slurm/17.11.12

------------------------------------------------------------- /cm/shared/whoi/applications -------------------------------------------------------------
anaconda/5.1       cmake/3.18.6      git/2.22.0       matlab-runtime/v94      nano/4.2          r/appdev                  tree/1.7.0
anaconda3/2021.11  cmake/3.20.2      globus-cli/3.5   matlab/donotuse         ncl/6.4.0         raxml-ng/1.0.1            valgrind/3.13.0
ansys/212          darknet/20180529  go/1.16.2        matlab/r2018b           nco/4.7.4         raxml-ng/1.1.0
automake/1.16.3    epa-ng/0.3.8      imagemagick/7.1  matlab/r2019b           ncview/2.1.7      singularity/2.4.2
aws/1.25           ffmpeg/20220422   jdk/16.0.1       matlab/r2020a(default)  octave/7.1.0      singularity/2.5.2
cdo/1.9.10         gaussian/09       julia/1.4.2      matlab/r2020b           r/3.4.4(default)  singularity/3.7(default)
cmake/3.11.1       gaussian/16       julia/1.6.5      matlab/r2022a           r/3.6.0           sqlite/3.34
cmake/3.14.3       gdal/2.4.3        julia/1.7.2      namd/2.13/gpu           r/4.1.3           tmux/3.1c

-------------------------------------------------------------- /cm/shared/whoi/compilers ---------------------------------------------------------------
cuda10.1/blas/10.1.243      cuda10.1/toolkit/10.1.243  cuda11.2/toolkit/11.2.0  cuda91/profiler/9.1.85  gcc/9.3.1       python3/3.4.7
cuda10.1/cudnn/7.6.5        cuda11.2/blas/11.2.0       cuda11.2/toolkit/11.2.2  cuda91/toolkit/9.1.85   intel/2018      python3/3.6.5
cuda10.1/cudnn/8.0.2        cuda11.2/blas/11.2.2       cuda91/blas/9.1.85       gcc/6.5.0               nvhpc/22.5      python3/3.9.10
cuda10.1/fft/10.1.243       cuda11.2/cudnn/8.6.0       cuda91/cudnn/7.1.3       gcc/7.3.0               pgi/18.3        python3/3.10.2
cuda10.1/nsight/10.1.243    cuda11.2/fft/11.2.0        cuda91/fft/9.1.85        gcc/8.3.1(default)      python2/2.7.14  python3/intel
cuda10.1/profiler/10.1.243  cuda11.2/fft/11.2.2        cuda91/nsight/9.1.85     gcc/8.5.0               python2/intel

-------------------------------------------------------------- /cm/shared/whoi/libraries ---------------------------------------------------------------
boost/gcc/1.67                   gsl/gcc/2.4        mpich/gcc/3.2.1            openmpi/gcc/3.0.1             pcre2/10.39        stack/mpich/1.0
boost/intel/1.67                 hdf5/gcc/1.10.2    mpich/intel/3.2.1          openmpi/gcc/4.0.1             petsc/gcc/3.9.1    stack/pgi/2.0
development/openmpi/intel/3.1.3  hdf5/intel/1.10.2  mpich/intel/donotuse       openmpi/intel/2.1.5           petsc/intel/3.9.1  szip/gcc/2.1.1
fftw/gcc/3.3.7                   hdf5/pgi/1.10.2    mpich/pgi/3.2.1            openmpi/intel/3.0.1(default)  petsc/pgi/3.9.1    szip/pgi/2.1.1
fftw/impi/3.3.7                  htslib/1.11        netcdf/gcc/4.6.1           openmpi/intel/3.1.3           pnetcdf/pgi/1.9.0  udunits2/2.2.26
fftw/impi/3.3.7-dp               impi/2018.2.199    netcdf/intel/4.6.1         openmpi/intel/4.0.1           stack/impi/1.0     zlib/gcc/1.2.11
fftw/intel/3.3.7                 mct/2.6            netcdf/pgi/4.5.0(default)  openmpi/pgi/2.1.2(default)    stack/intel/1.0    zlib/pgi/1.2.11
fftw/pgi/3.3.7                   mct/impi/2.6       netcdf/pgi/4.6.1           openmpi/pgi/donotuse          stack/intel/2.0
(base) [csherwood@pn124 swash]$ module add slurm/17.11.12
(base) [csherwood@pn124 swash]$ module add default-environment
(base) [csherwood@pn124 swash]$ module add intel/2018
WARNING: $PATH does not agree with $PATH_modshare counter. The following directories' usage counters were adjusted to match. Note that this may mean that module unloading may not work correctly.
 /cm/local/apps/environment-modules/4.0.0//bin
(base) [csherwood@pn124 swash]$ module add mpich/intel/3.2.1
(base) [csherwood@pn124 swash]$ module add stack/mpich/1.0
(base) [csherwood@pn124 swash]$ module add stack/intel/2.0
(base) [csherwood@pn124 swash]$ mkdir build && cd build
mkdir: cannot create directory ‘build’: File exists
(base) [csherwood@pn124 swash]$ cd build
(base) [csherwood@pn124 build]$ pwd
/vortexfs1/home/csherwood/src/swash/build
(base) [csherwood@pn124 build]$ ls
CMakeCache.txt  CMakeFiles
(base) [csherwood@pn124 build]$ rm *.txt

^C^C

(base) [csherwood@pn124 build]$
(base) [csherwood@pn124 build]$ rm -Rf CMakefiles
(base) [csherwood@pn124 build]$ cmake ..  -DMPI=ON -DCMAKE_INSTALL_PREFIX=/vortexfs1/home/csherwood/bin
CMake Error at CMakeLists.txt:6 (cmake_minimum_required):
  CMake 3.12 or higher is required.  You are running version 2.8.12.2


-- Configuring incomplete, errors occurred!
See also "/vortexfs1/home/csherwood/src/swash/build/CMakeFiles/CMakeOutput.log".
See also "/vortexfs1/home/csherwood/src/swash/build/CMakeFiles/CMakeError.log".
(base) [csherwood@pn124 build]$ module add cmake/3.20.2
(base) [csherwood@pn124 build]$ cmake ..  -DMPI=ON -DCMAKE_INSTALL_PREFIX=/vortexfs1/home/csherwood/bin
-- The Fortran compiler identification is Intel 18.0.2.20180210
-- Detecting Fortran compiler ABI info
-- Detecting Fortran compiler ABI info - done
-- Check for working Fortran compiler: /vortexfs1/apps/intel/compilers_and_libraries_2018.2.199/linux/bin/intel64/ifort - skipped
-- Checking whether /vortexfs1/apps/intel/compilers_and_libraries_2018.2.199/linux/bin/intel64/ifort supports Fortran 90
-- Checking whether /vortexfs1/apps/intel/compilers_and_libraries_2018.2.199/linux/bin/intel64/ifort supports Fortran 90 - yes
-- Found Perl: /usr/bin/perl (found version "5.16.3")
-- Found MPI_Fortran: /vortexfs1/apps/openmpi-4.0.1-intel/lib/libmpi_usempif08.so (found version "3.1")
-- Found MPI: TRUE (found version "3.1") found components: Fortran
-- Configuring done
-- Generating done
-- Build files have been written to: /vortexfs1/home/csherwood/src/swash/build
(base) [csherwood@pn124 build]$ client_loop: send disconnect: Connection reset
