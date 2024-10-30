# PYDisloc3D

Solves rectangular dislocations in an elastic halfspace using the solutions of [Okada (1992)](https://pubs.geoscienceworld.org/ssa/bssa/article-abstract/82/2/1018/119580/Internal-deformation-due-to-shear-and-tensile). Python native implementation of disloc3d.m from [Paul Segall](https://pangea.stanford.edu/research/CDFM/software/index.html). 

PyDisloc3D performs the same calculations as [okada_wrapper](https://github.com/tbenthompson/okada_wrapper) using a different method. Okada_wrapper uses compiled Fortran code while PyDisloc3D is a pure python implementation. PyDisloc3D computes solutions for a single dislocation at all observation points simultaneously, resulting in faster performance. 

The table below contains benchmarks for three different meshes using the [BforStrain](https://github.com/jhdorsett/BforStrain) study area solving on 235 fault patches for this code, okada_wrapper, and Matlab's disloc3D.m. Meshes generated using BforStrain using `nominal_node_spacing = 50 km`, `nominal_node_spacing = 100 km`, and `nominal_node_spacing = 100 km` with `decimate = 4` to represent fine, average, and coarse meshes.



| Num obs points | PyDisloc3D    | okada_wrapper | Matlab Disloc3D|
| -------------  | ------------- | ------------- | -------------  |
| N = 16544      | 11.2 s        | 18.9 s        | 12.0 s         |
| N = 13520      | 9.2 s         | 16.1 s        | 11.0 s         |
| N = 4856       | 3.6 s         | 5.6 s         | 5.5 s  |

Run using an M1 Pro with 16 GB Ram.
