# PYDisloc3D

Solves rectangular dislocations in an elastic halfspace using the solutions of Okada (1992). Python native implementation of disloc3d.m from https://pangea.stanford.edu/research/CDFM/software/index.html. 

PyDisloc3D performs the same calculations as okada_wrapper. The key difference is that okada_wrapper uses compiled Fortran code to solve for a single observation point and loops over the provided observation grid while PYDisloc3D computes at multiple observation points simultaneously using native Python code. This results in a performance tradeoff: for smaller grids, okada_wrapper is faster, for larger grids PYDisloc3D is faster. Both use similar input geometries.
