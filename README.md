# XANES Guideline
A practical guide on how to use **FDMNES** software to do XANES

# General Comments

* You can download **FDMNES** from here: http://neel.cnrs.fr/spip.php?article3137&lang=en

* **FDMNES** is precompiled so there is no need to compile it.

* For post processing, you need **Athena** software which can be downloaded from here: http://bruceravel.github.io/demeter/#windows

* There are several problems regarding the Mac version installation of **Athena**, and it is recommended to install the Windows version of it. 

## Run FDMNES

* ./mpirun_fdmnes -np 16: To run the parallel version of **FDMNES**.

* HOST_NUM_FOR_MUMPS=4 ./mpirun_fdmnes -np 20: 20 MPI processes, which fdmnes divides into 5 groups of 4 processes in each. One group calculates one energy value by parallel MUMPS solver with 4 parallel processes.

* ./mpirun_fdmnes -h: For getting help.

