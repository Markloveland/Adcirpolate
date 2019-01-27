# Adcirpolate
Instructions to compile adcirpolate on Lonestar5 and Stampede2:
1.	First you will need to install the esmf library. The correct version can be found as a zip file on github at https://github.com/Markloveland/Adcirpolate along with a zip file of the adcirpolate code if you have not yet obtained it
2.	Copy the appropriate esmf zip file onto lonestar5 (esmf_6_3_ls5.zip) or stampede2(esmf_6_3_stampede2.zip)
3.	Unzip the zip file “unzip esmf_6_3_ls5.zip" for lonestar5 or "unzip esmf_6_3_stampede2.zip" for stampede2
4.	Go into the esmf directory and copy/paste all the lines in the envs.txt or env_vars onto the command line in order to set all necessary environmental variables
5.	Type make, this should successfully install esmf
Note: You can create a debugging version of esmf by changing the ESMF_BOPT from “O” to “g” in th envs.txt file
6.	Now that esmf is installed we can now build adcirpolate, first unzip the adcirpolate-master.zip
7.	Before compiling, 2 environmental variables must be set:
export ESMF_CONFIG_FILE=path to esmf.mk
The path to the esmf.mk file should be located inside the lib folder of esmf, something like the following:
 /scratch/04637/mdl2665/esmf/lib/libO/Linux.intel.64.mpich2.default/esmf.mk
export FC=mpif90
this is your fortran compiler
8.	Then enter into the adcirpolate folder and type:
``` 
cmake .
make
```
and the adcirpolate executable should be generated



