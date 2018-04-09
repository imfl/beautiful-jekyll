---
layout: page
title: parallel computing
subtitle: is there any arbitrage opportunity?
use-site-title: true
---

The [Bellman-Ford algorithm](https://en.wikipedia.org/wiki/Bellman-Ford_algorithm) is an algorithm that computes the shortest paths from one single source vertex to all the other vertices in a weighted directed graph. The weights can be negative.

Assume that you have and use US dollars. Now you are travelling to East Asia. You want to know what're the cheapest rates that you can exchange for local currencies like Hong Kong dollars and Singaporean dollars. Bellman-Ford algorithm can help you solve this. Better yet, it may even tell if there is any arbitrage opportunity in the foreign exchange market. Say you exchange USD $1 for HKD $8, and HKD $8 for SGD $1.4, and SGD $1.4 for USD $1.05. Congratulations! You've found an arbitrage opportunity that brings you money with no effort.

### MPI

The C++ code is [here](https://github.com/imfl/parallel-computing/blob/master/bf-mpi.cpp) (GitHub).

### OMP

The C++ code is [here](https://github.com/imfl/parallel-computing/blob/master/bf-omp.cpp) (GitHub).

### CUDA

The C++ (CUDA) code is [here](https://github.com/imfl/parallel-computing/blob/master/bf-cuda.cu) (GitHub).

### More Information 

This project serves as a series of assignments that I did for *COMP 5112 Parallel Computing*, a postgraduate-level course that I took at the Department of Computer Science and Engineering at HKUST in Spring 2017.
