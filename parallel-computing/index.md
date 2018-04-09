---
layout: page
title: parallel computing
subtitle: is there any arbitrage opportunity?
use-site-title: true
---

The [Bellman-Ford algorithm](https://en.wikipedia.org/wiki/Bellman-Ford_algorithm) is an algorithm that computes the shortest paths from one single source vertex to all the other vertices in a weighted directed graph. The weights can be negative.

### What can I use it for?

Assume that you have US dollars. Now you are travelling to East Asia. You want to know the cheapest rates that you can exchange for local currencies. Bellman-Ford algorithm can help you solve this.

Better yet, it may even tell you if there is any arbitrage opportunity in the foreign exchange market. Say you manage to exchange USD $1 for HKD $8, and that HKD $8 for SGD $1.4, and that SGD $1.4 for USD $1.05. Congratulations! You've found an arbitrage opportunity that brings you money with no effort.

### Parallelization

In this project I parallelize the Bellman-Ford algorithm so that the computation can be much faster, especially for large graphs. Multiple programming paradigms are employed, including MPI, which is distributed-memory programming, and OMP and CUDA, which are shared-memory programming.

### MPI

The C++ code is [here](https://github.com/imfl/parallel-computing/blob/master/bf-mpi.cpp) (GitHub).

### OMP

The C++ code is [here](https://github.com/imfl/parallel-computing/blob/master/bf-omp.cpp) (GitHub).

### CUDA

The C++ (CUDA) code is [here](https://github.com/imfl/parallel-computing/blob/master/bf-cuda.cu) (GitHub).

### More Information 

This project serves as a series of assignments that I did for *COMP 5112 Parallel Computing*, a postgraduate-level course that I took at the Department of Computer Science and Engineering at HKUST in Spring 2017.
