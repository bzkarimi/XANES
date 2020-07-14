# XANES Guideline
A practical guide on how to use **FDMNES** software to do XANES

# General Comments

* You can download **FDMNES** from here: http://neel.cnrs.fr/spip.php?article3137&lang=en

* **FDMNES** is precompiled so there is no need to compile it.

* For post processing, you need **Athena** software which can be downloaded from here: http://bruceravel.github.io/demeter/#windows

* There are several problems regarding the Mac version installation of **Athena**, and it is recommended to install the Windows version of it. 

## Running FDMNES

* ./mpirun_fdmnes -np 16: To run the parallel version of **FDMNES**.

* HOST_NUM_FOR_MUMPS=4 ./mpirun_fdmnes -np 20: 20 MPI processes, which fdmnes divides into 5 groups of 4 processes in each. One group calculates one energy value by parallel MUMPS solver with 4 parallel processes.

* ./mpirun_fdmnes -h: For getting help.

* Sample submission script: https://github.com/bzkarimi/Scripts/blob/master/HPC/fdmnes-hoffman.sh

## Papers to read

* https://journals.aps.org/prb/abstract/10.1103/PhysRevB.63.125120

* https://link.springer.com/article/10.1007/s11244-016-0612-0

* https://iopscience.iop.org/article/10.1088/1742-6596/190/1/012007

* https://pubs.acs.org/doi/abs/10.1021/acs.jpcc.0c02823

* https://iopscience.iop.org/article/10.1088/1742-6596/190/1/012084/meta

* https://pubs.acs.org/doi/abs/10.1021/acs.jpcc.6b10167

* https://iopscience.iop.org/article/10.1238/Physica.Topical.115a00813

* https://pubs.acs.org/doi/10.1021/acs.jpcc.8b07952

* http://sabotin.ung.si/~arcon/xas/xanes/xanes-theory.pdf
