# XANES Guideline
A practical guide on how to use **FDMNES** software to do XANES

# General Comments

* You can download **FDMNES** from here: http://neel.cnrs.fr/spip.php?article3137&lang=en

* **FDMNES** is precompiled so there is no need to compile it.

* For post processing, you need **Athena** software which can be downloaded from here: http://bruceravel.github.io/demeter/#windows

* There are several problems regarding the Mac version installation of **Athena**, and it is recommended to install the Windows version of it. 

## Running FDMNES

* First of all, you need to set the path to your input file(s) in **fdmfile.txt** file.

* The actual input file format is .txt.

* Output files: **filename_conv.txt** contains the energies and intensities of the spectrum and **filename_bav.txt** is the log file which contains more detailed information about the calculations.

* Sample input/output files can be found here: https://github.com/bzkarimi/XANES/tree/master/Sample-files

## FDMNES Running Commands

* ./mpirun_fdmnes -np 16: To run the parallel version of **FDMNES**.

* HOST_NUM_FOR_MUMPS=4 ./mpirun_fdmnes -np 20: 20 MPI processes, which fdmnes divides into 5 groups of 4 processes in each. One group calculates one energy value by parallel MUMPS solver with 4 parallel processes.

* ./mpirun_fdmnes -h: For getting help.

* Sample submission script: https://github.com/bzkarimi/Scripts/blob/master/HPC/fdmnes-hoffman.sh

## Post-processing

* You have to normalize the intensities before you plot the spectrum (**filename_conv.txt**). This can be done automatically using **Athena** software. You just need to open **filename_conv.txt** with **Athena** and click on normalize. Then you can save the new data into a new file.

* **Note**: When you open your raw file (**filename_conv.txt**) with **Athena**, it asks which column in your data corresponds to E (first column) and which column corresponds to intensity (second column).

* **Linear Combination Fitting (LCF)**: In order to do **LCF**, you have to open all files that you want to use (Standards and the one that you want to do the fitting). Once you have all your files open in **Athena** simply choose the spectrum that you want to do **LCF** on, then choose Linear Combination Fitting from the menu. The software automatically sets the other files as standards. The initial coefficients for each standard is equal to each other. Once you do **LCF** you can obtain the new coefficients and extract the fitted spectrum data.

* **Note**: Make sure that you do **LCF** on the normalized spectrum not the raw ones.


## Papers to Read

* https://journals.aps.org/prb/abstract/10.1103/PhysRevB.63.125120

* https://link.springer.com/article/10.1007/s11244-016-0612-0

* https://iopscience.iop.org/article/10.1088/1742-6596/190/1/012007

* https://pubs.acs.org/doi/abs/10.1021/acs.jpcc.0c02823

* https://iopscience.iop.org/article/10.1088/1742-6596/190/1/012084/meta

* https://pubs.acs.org/doi/abs/10.1021/acs.jpcc.6b10167

* https://iopscience.iop.org/article/10.1238/Physica.Topical.115a00813

* https://pubs.acs.org/doi/10.1021/acs.jpcc.8b07952

* http://sabotin.ung.si/~arcon/xas/xanes/xanes-theory.pdf
