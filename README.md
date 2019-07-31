# Data

The following repository contains all the data used for the generation of figures and the systems prioritization, divided into three folders: Figures, Numerical Simulations and Systems Prioritization.

## Figures

Plots and data used for figures 2, 3, 4 and 5. 

#### Comments

- For each figure, the folder "Data" contains the .mat files used to generate the graphics, while the folder "Plots" contains the figure in .eps format.
- For figures 2, 3 and 4, files are always named as "Target_element", where "Target" is the name of the system and "element" can be: 
  - a (or R or m) edges: Arrays defining the bin edges corresponding to the grid where Stab, DoS or StabDoS are calculated. 
  - a (or R or m) centers: Arrays defining the bin centers corresponding to the grid where Stab is calculated. 
  - Stab: Stability probability matrix.
  - DoS: Depth-of-search matrix.
  - StabDoS: Stable depth-of-search matrix (Stab * DoS). 
  - info: Struct containing the target's main information. 

## Numerical Simulations

Results of the numerical stability maps, used to generate figure 1. 

#### Comments

- Files are named similarly to the Figures data. _mplot and _eplot are added to distinguish which plot is the file referring to. 
-

## Systems Prioritization

Data used to calculate the dynamically stable completeness and generate the single-planet systems ranking. 

#### Comments

- Data is divided into the following folders:
  - Datalimits: 4-element array containing the semi-major axis (a) and planetary radius (R) imageable limits [amin, amax, Rmin, Rmax], calculated together with the depth-of-search grids. 
  - Edges: Arrays containing the a and R bin edges corresponding to the grids where the calculations are performed. 
  - DoSGrids: Depth-of-search grids. 
  - StabGrids: Stability grids. 
  - StabDoSGrids: Stable depth-of-search grids (Stab * DoS). 
  - OccGrids: Occurrence rates grids, where each bin value is multiplied by the bin area.  
  - StabCompGrids: Stable completeness grids (StabDoS * Occ).
- Res.mat contains the stable depth-of-search and completeness results for all 213 systems, stored in a table with the following columns:
  - Target
  - 
## General Comments

- G, H and P refer to Giuppone's, the Hill AMD and Petrovich's stability criteria respectively.
- 

