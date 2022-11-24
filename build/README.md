Exploring CICE6-WW3-DOCN-DATM-DROF CESM build
=============================================

This directory contains scripts exploring building a CICE6-WW3-DOCN-DATM-DROF-SLND-SGLC CESM coonfiguration. Two build scripts are provided. Both assume that shared libs are already built at `/scratch/tm70/ds0092/cime/scratch/D_JRA_WD/bld`. The required shared libraries can be built using (for example) the CIME `GMOM_JRA_WD` compset:
```
./create_newcase --case D_JRA_WD --compset GMOM_JRA_WD --res f19_g17_rx1 --machine gadi --run-unsupported
./case.setup
./case.build --sharedlib-only
```

`build.sh` (working)
--------------------
This script builds all the model components and the CMEPS `cesm.exe` exectuable

`build_switch.sh` (not working)
-------------------------------
This script uses a prior complete build of `GMOM_JRA_WD` and attempts to switch out the active ocean component for a data ocean at the final step of building the CMEPS `cesm.exe` executable. If you don't already have a complete build of `GMOM_JRA_WD`, first run:
```
./create_newcase --case GMOM_JRA_WD --compset GMOM_JRA_WD --res f19_g17_rx1 --machine gadi --run-unsupported
./case.setup
./case.build
```