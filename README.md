## The standard and parallel efficient global optimization (EGO) algorithms

### The EGO algorithm using standard EI criterion
The efficient global optimization (EGO) algorithm [1] is a widely used surrogate-based optimization algorithm for expensive single-objective optimiztion. The EGO algorithm starts by building an initial Kriging model (aka. Gaussion process model) using some initial design points which are often produced by a experiment design method, such as Latin Hypercube Sampling (LHS) method. Then, in each iteration, the point with the highest expected improvement (EI) value is selected  by using a traditional optimization algorithm, such as genetic algorithm (GA). The selected point is evaluated using the real expensive objective function and used to update the Kriging model. In such a way, the EI criterion guides the search toward the optimum of the real problem.

### The EGO algorithm using weighted EI criterion
The standard EI criterion might not give the best tradeoff between global exploration and local exploitation, so Sóbester et al.(2005) [2] proposed the weighted EI criterion to have more control between the global and local search of the EGO algorithm. 

### The parallel EGO algorithm using pseudo EI criterion
The parallel efficient global optimization (EGO) algorithm is an extendtion of the standard EGO criterion [3] which allows the EGO algorithm to select multiple design points in each iteration (cycle). Then these candidate points can be evaluated in parallel that may save some wall-clock time. The pseudo EI criterion is used in the algorithm to select multiple design points in each cycle. The detailed desciption of the pseudo EI criterion can be referred to [3]. The dace toolbox [4] is used for building the Kriging models in the implementations.

### Reference:
1. Jones, D.R., Schonlau, M., Welch, W.J.: Efficient global optimization of expensive black-box functions. Journal of Global Optimization, 13(4), 455-492 (1998).
2. A. Sóbester, S. Leary, A. Keane, On the Design of Optimization Strategies Based on Global Response Surface Approximation Models, Journal of Global Optimization, 33(1) (2005) 31-59.
2. D. Zhan, J. Qian, Y. Cheng, Pseudo expected improvement criterion for parallel, Journal of Global Optimization, 2017, 68 (3): 641-662. 
3. Lophaven SN, Nielsen HB, and Sodergaard J, DACE - A MATLAB Kriging Toolbox, Technical Report IMM-TR-2002-12, Informatics and Mathematical Modelling, Technical University of Denmark, 2002. Available at: http://www2.imm.dtu.dk/projects/dace/.
