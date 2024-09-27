#  Container Scripts (containers repo):
Scripts, etc. for containers. This repo will focus on multi-purpose containers and base containers. 

This collection reflects the logistical difficulty of building containers on laptops and small personal machines, as per permissions restrictions on HPC platforms. Consequently, container formulas reflect a cascade approach, wherein end point containers (a specific application) is build from a hierarchy of base containers, eg [Ubuntu base] -> [MPICH + GCC] -> [Netcdf, etc.] -> [AM4 simulator].

It would seem that these restrictions are no more. Apptainer and PodMan container systems do not require `sudo` priveleges to run or even build containers, so they can be built right on the HPC, by ordinary users. Because container builds -- and in particualr the compilation of large packages such as `gcc`, can be run on multiple processors and batched to run unattended, such hierarchy is not necessary. That said, there is still benefit to using build caches, hierarchical containers, staged container builds, etc. to reduce build time. This is especially true for work done in Cloud environments, where compute cycles can be very expensive.
