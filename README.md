# Data

The following repository contains all the data corresponding to the numerical simulations and the systems prioritization, divided into two main folders: Numerical Simulations and Systems Prioritization.

## Numerical Simulations

Results of the simulations used to generate the numerical stability maps presented in Figure 1. 

#### Comments
- The folder "Data" contains the .mat files obtained from the numerical simulations and used to generate the graphics, while the folder "Plots" contains the plot from Figure 1 in .eps format.
- Data files are always named as "Target_element", where "Target" is the name of the system and "element" can be:  
  - a (or e or m) centers: Arrays defining the bin centers corresponding to the grids where StabNum is calculated (see General Comments). Eccentricity (e) values are linearly spaced, while semi-major axis (a) and planetary mass (m) values are logarithmically spaced. 
  - StabNum: Simulation lifetime matrix in [log10(yr)].
  - info: Struct containing the target's main information. 
- When needed, "mplot" and "eplot" are added to the file name in order to determine which kind of plot the file is referring to. 

## Systems Prioritization

Data used to calculate the dynamically stable completeness and generate the single-planet systems prioritization. 

#### Comments

- Data is divided into the following folders:
  - Datalimits: 4-element array containing the semi-major axis (a) and planetary radius (R) imageable limits [amin, amax, Rmin, Rmax], calculated, together with the depth-of-search grids, using Garrett's code (see General Comments). 
  - Edges: Arrays containing the a and R bin edges (logarithmically spaced) corresponding to the grids where the calculations are performed (see General Comments). 
  - DoSGrids: Depth-of-search grids calculated using Garrett's code (see General Comments). 
  - StabGrids: Stability grids for each stability criterion considered. 
  - StabDoSGrids: Stable depth-of-search grids (calculated as StabGrid .* DoSGrid). 
  - OccGrids: Occurrence rates grids calculated using the SAG13 parametric fit, where each bin value is also multiplied by the bin area.  
  - StabCompGrids: Stable completeness grids (calculated as StabDoSGrid .* OccGrid).
- Res.mat contains the stable depth-of-search and completeness results for all 213 single-planet systems, stored in a table with the following columns:
  - Target: Name of the system and planet letter.
  - Distance: System's distance in [pc].
  - sma: Known planet's semi-major axis in [AU].
  - ecc: Known planet's eccentricity.
  - mp: Known planet's mass in [Mjup] (see General Comments).
  - StabDoS: Stable depth-of-search (this column is calculated for each stability criterion).
  - StabComp: Stable completeness (this column is calculated for each stability criterion). 
  
## General Comments
- Planetary mass (m), planetary radius (R) and semi-major axis (a) are always expressed in [Mjup], [Rearth] and [AU], respectively.
- When center values are given (e.g., in Numerical Simulations), the corresponding matrices account for the results obtained exactly at the grid points defined by acenters and ecenters (or mcenters). Therefore, if matrices are Nm x Na, then acenters and mcenters have Na and Nm points, respectively.
- When edge values are given (e.g., in Systems Prioritization), the corresponding matrices contain the bin values obtained by averaging the results at the edges of each bin defined by aedges and Redges. Therefore, if matrices are Nr x Na, then aedges and Redges have Na + 1 and Nr + 1 points, respectively. Note that, in the case of the occurrence grids (OccGrids), the average bin values are also multiplied by the bin area defined by the corresponding bin edges.
- In most cases, the known planet's mass corresponds to the minimum value mp * sinI.
- G, H and P refer to Giuppone's, the Hill AMD and Petrovich's stability criteria, respectively.
- Depth-of-search is calculated using Garrett's code, available at: https://github.com/dgarrett622/DoS .

