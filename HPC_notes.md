***Building SWASH per the README.md in https://gitlab.tudelft.nl/citg/wavemodels/swash  

`cd src`  
`git clone https://gitlab.tudelft.nl/citg/wavemodels/swash.git`  
`module add cmake/3.20.2` 

$PATH does not agree with $PATH_modshare counter. The following directories' usage counters were adjusted to match. Note that this may mean that module unloading may not work correctly.
 /cm/local/apps/environment-modules/4.0.0//bin  
 
 `module add intel/2018`  
 `module add mpich/intel/3.2.1`  
 `mkdir build && cd build`  
 
 ` cmake .. -GNinja -DMPI=ON -DCMAKE_INSTALL_PREFIX=/vortexfs1/home/csherwood/bin`  
 
 After failing, I did
 `module purge`   
 rm CMakeCache.txt`    
 rm -Rf CMakeFiles`  
 
 ```
-- The Fortran compiler identification is unknown
ifort: error #10417: Problem setting up the Intel(R) Compiler compilation environment.  Requires 'install path' setting gathered from 'gcc'
-- Detecting Fortran compiler ABI info
-- Detecting Fortran compiler ABI info - failed
-- Check for working Fortran compiler: /vortexfs1/apps/mpich-3.2.1-intel/bin/mpifort
-- Check for working Fortran compiler: /vortexfs1/apps/mpich-3.2.1-intel/bin/mpifort - broken
CMake Error at /vortexfs1/apps/cmake-3.20.2/share/cmake-3.20/Modules/CMakeTestFortranCompiler.cmake:51 (message):
  The Fortran compiler

    "/vortexfs1/apps/mpich-3.2.1-intel/bin/mpifort"

  is not able to compile a simple test program.

  It fails with the following output:

    Change Dir: /vortexfs1/home/csherwood/src/swash/build/CMakeFiles/CMakeTmp

    Run Build Command(s):/opt/rh/devtoolset-8/root/usr/bin/gmake -f Makefile cmTC_7446c/fast && /opt/rh/devtoolset-8/root/usr/bin/gmake  -f CMakeFiles/cmTC_7446c.dir/build.make CMakeFiles/cmTC_7446c.dir/build
    gmake[1]: Entering directory '/vortexfs1/home/csherwood/src/swash/build/CMakeFiles/CMakeTmp'
    Building Fortran object CMakeFiles/cmTC_7446c.dir/testFortranCompiler.f.o
    /vortexfs1/apps/mpich-3.2.1-intel/bin/mpifort    -c /vortexfs1/home/csherwood/src/swash/build/CMakeFiles/CMakeTmp/testFortranCompiler.f -o CMakeFiles/cmTC_7446c.dir/testFortranCompiler.f.o
    ifort: error #10417: Problem setting up the Intel(R) Compiler compilation environment.  Requires 'install path' setting gathered from 'gcc'
    gmake[1]: *** [CMakeFiles/cmTC_7446c.dir/build.make:78: CMakeFiles/cmTC_7446c.dir/testFortranCompiler.f.o] Error 1
    gmake[1]: Leaving directory '/vortexfs1/home/csherwood/src/swash/build/CMakeFiles/CMakeTmp'
    gmake: *** [Makefile:127: cmTC_7446c/fast] Error 2





  CMake will not be able to correctly generate this project.
Call Stack (most recent call first):
  CMakeLists.txt:16 (project)


-- Configuring incomplete, errors occurred!
See also "/vortexfs1/home/csherwood/src/swash/build/CMakeFiles/CMakeOutput.log".
See also "/vortexfs1/home/csherwood/src/swash/build/CMakeFiles/CMakeError.log".
 ```
