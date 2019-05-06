An MD study of the wear of defective tools in the nanometric cutting process
================================================================================

## Introduction

An MD simulation analysis was conducted to compare the cutting response and the tool wear between flawed and flawless tool surfaces based on a three-layer nanometric cutting model.

---

## Methodology
 
### Materials
 - single diamond tool,	with dimensions 31[100] 31[010] 22[001] in x, y, and z directions, edge radius = 4 x diamond unit cell, zero rake angle, clearance angle = 10 degrees
 - 3C-SiC workpiece,	with dimensions 65[010] 10[010] 18[001] in x, y, and z directions
 
 ![](front_view.png)
 
### Cutting Conditions
 - Depth of cut = 5 x 3C-SiC unit cell length
 - Cutting direction = [010]<-1 0 0> for ≈200 Å
 - Initial temperature = 300 K
 
### Simultion Settings
 1. Equilibration
 - NVT ensemble, timestep = 0.0005 ps 	(0.5 fs) for 10000 steps
 2. Cutting
 - NVT+NVE ensembles, timestep = 0.0005 ps (0.5 fs) for 400000/$v steps
 
---

## Execution

### Input Template:
 - in.cutsic_eq.lmp
 
 **Potential**
 - EA
 
 **Variables**
 - v		cutting velocity (unit = Å/ps)
 
 
### example:
  @Precision > mpirun -np 32 ../../lmp_mpi_20161117_atomistica046 < in.cutsic_eq.lmp -v v 3.0
  @Precision > mpirun -np 32 ../../lmp_mpi_20161117_atomistica046 < in.cutsic_cont_201407201atomistica.lmp  -v v 3.0
 
## Recommended Books and References
1. [Fung, K. Y., Tang, C. Y., and Cheung, C. F. (2017). Molecular dynamics analysis of the effect of surface flaws of diamond tools on tool wear in nanometric cutting. Computational Materials Science, 133, 60–70.](http://www.sciencedirect.com/science/article/pii/S0927025617301180)
 
