### HPC notes

## Managing Jobs
To submit a job
`sbatch <mysubmitscript.sh>`

To submit an interactive job
`srun -p interactive --mem=500 --ntasks=1 --time=00:20:00 --pty bash`

List your current running jobs
`squeue -u $USER -t RUNNING`

List all pending jobs
`squeue -al -t PENDING`

List all current jobs in the compute partition
`squeue -p compute`

List detailed information for a job (useful for troubleshooting)
`scontrol show jobid -dd  <jobid>`

List status info for a currently running job:
`sstat -j <jobid> --format=AveCPU,AvePages,AveRSS,AveVMSize,JobID --allsteps`
 
Get statistics on completed jobs by jobid
`sacct -j <jobid> --format=JobID,JobName,MaxRSS,Elapsed`

See how much memory your job used
`sacct -j <job_id> —format=”JobID,user,elapsed,ReqMem,MaxVMSize,ncpus,MaxVMSizeNode”`

```[root@poseidon-l1 ~]# sacct -j 9200 --format="JobID,user,elapsed,ReqMem,MaxVMSize,ncpus,MaxVMSizeNode"
       JobID      User    Elapsed     ReqMem  MaxVMSize      NCPUS  MaxVMSizeNode 
------------ --------- ---------- ---------- ---------- ---------- -------------- 
9200          username   01:09:51    40000Mn                    72                
9200.batch               01:09:51    40000Mn  27503812K         36          pn055 
9200.0                   01:09:49    40000Mn  27002992K          1          pn056 
In this example, the job used ~28GB of memory.
```

Cancel job
`scancel  <jobid>`

Cancel all pending jobs
`scancel -t PENDING -u <username>`

Cancel jobs by name
`scancel --name  myJobName`

Pause job
`scontrol hold  <jobid>`

Resume job
`scontrol resume  <jobid>`

Requeue job
`scontrol requeue  <jobid>`

View cluster status and availability
`sinfo`

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
