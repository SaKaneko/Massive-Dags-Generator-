# Massive-Dags-Generator-

## requirement
* C++17
* CMake

## Files

* src/Params.hpp
* src/FileUtil.hpp
* src/Graphgen.cpp
* src/FileUtil.hpp

## Output Style
You can choose 2 output styles
* Table output  
    The Dags are written as a NxN table. So the output like:
    $
    \\
    N\\
    d_{00}\ d_{01}\ ...\ d_{0N}\\
    d_{10}\ d_{11}\ ...\ d_{1N}\\
    ...\\
    d_{N0}\ d_{N1}\ ...\ d_{NN}\\
    $
    where d_ij represents that there is a edge from Node i to Node j.

* adjacency list output  
    The Dags are written as the sets of adjacency list.
    $
    \\
    N\\
    c_0\\
    cn_{01}\ cn_{02}\ ... cn_{0c_0}\\
    c_1\\
    cn_{11}\ cn_{12}\ ... cn_{1c_1}\\
    ...\\
    c_N\\
    cn_{N1}\ cn_{N2}\ ... cn_{Nc_N}\\
    $
    where c_0 represents the number of out_edges and cn_ij represents the node which has a edge to node i.



## Parameters

* α : Shape parameter of the graph
We assume that the height (depth) of a DAG is randomly generated from a uniform distribution with a mean value equal to v√α. (The height is equal to the smallest integral value not less than the real value generated randomly.) The width for each level is randomly selected from a uniform distribution with mean equal to α×v√. A dense graph (a shorter graph with high parallelism) can be generated by selecting α>>1.0; if α<<1.0, it will generate a longer graph with a low parallelism degree.