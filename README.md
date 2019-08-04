# Data

The following repository contains all the data used for the generation of figures and the systems prioritization, divided into three folders: Figures, Numerical Simulations and Systems Prioritization.

## Figures

Plots and data used for figures 2, 3, 4 and 5. 

#### Comments

- For each figure, the folder "Data" contains the .mat files used to generate the graphics, while the folder "Plots" contains the plots in .eps format.
- For figures 2, 3 and 4, files are always named as "Target_element", where "Target" is the name of the system and "element" can be: 
  - a (or R or m) edges: Arrays defining the bin edges corresponding to the grid where Stab, DoS or StabDoS are calculated (see General Comments). 
  - a (or R or m) centers: Arrays defining the bin centers corresponding to the grid where Stab is calculated (see General Comments). 
  - Stab: Stability probability matrix.
  - DoS: Depth-of-search matrix.
  - StabDoS: Stable depth-of-search matrix (Stab * DoS). 
  - info: Struct containing the target's main information. 

## Numerical Simulations

Results of the numerical stability maps used to generate figure 1. 

#### Comments

- Files are always named as "Target_element", where "Target" is the name of the system and "element" can be:  
  - a (or R or m) centers: Arrays defining the bin centers corresponding to the grid where Stab is calculated (see General Comments). 
  - StabNum: Simulation lifetime matrix in [log10(yr)].
  - info: Struct containing the target's main information. 
- When needed, "mplot" and "eplot" are added to the file name in order to distinguish which kind of plot the file is referring to. 

## Systems Prioritization

Data used to calculate the dynamically stable completeness and generate the single-planet systems ranking. 

#### Comments

- Data is divided into the following folders:
  - Datalimits: 4-element array containing the semi-major axis (a) and planetary radius (R) imageable limits [amin, amax, Rmin, Rmax], calculated together with the depth-of-search grids using Garrett's code (see General Comments). 
  - Edges: Arrays containing the a and R bin edges corresponding to the grids where the calculations are performed. 
  - DoSGrids: Depth-of-search grids calculated using Garrett's code (see General Comments). 
  - StabGrids: Stability grids. 
  - StabDoSGrids: Stable depth-of-search grids (calculated as Stab * DoS). 
  - OccGrids: Occurrence rates grids calculated using the SAG13 parametric fit, where each bin value is also multiplied by the bin area.  
  - StabCompGrids: Stable completeness grids (calculated as StabDoS * Occ).
- Res.mat contains the stable depth-of-search and completeness results for all 213 single-planet systems, stored in a table with the following columns:
  - Target: Name of the system and planet letter.
  - Distance: System's distance in [pc].
  - sma: Known planet's semi-major axis in [AU].
  - ecc: Known planet's eccentricity.
  - mp: Known planet's mass in [Mjup].
  - StabDoS: Stable depth-of-search (this column is calculated for each stability criterion).
  - StabComp: Stable completeness (this column is given for each stability criterion). 
  
## General Comments

- When center values are given, the corresponding color matrix (e.g. Stab or DoS) accounts for the results obtained exactly at the grid points defined by acenter and Rcenters (or mcenters). If matrix is Nr x Na, then acenters and rcenters have Na and Nr points respectively. 
- When edge values are given, the corresponding color matrix (e.g. Stab or DoS) accounts for the values obtained as the average of the results calculated at the edges of each bin defined by aedges and Redges (or medges). If matrix is Nr x Na, then aedges and redges have Na + 1 and Nr + 1 points respectively.
- G, H and P refer to Giuppone's, the Hill AMD and Petrovich's stability criteria, respectively.
- Depth-search is calculated using Garrett's code, available at: https://github.com/dgarrett622/DoS

