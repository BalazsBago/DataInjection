# DataInjection
Remote direct memory access for GPU Nodes 

## Introduction

This project contains information and scripts are used in Data Injection Report: Benchmark of communication between HPC nodes.

## Requirements - tools

* [OSU Micro-Becnhmark](http://mvapich.cse.ohio-state.edu/static/media/mvapich/README-OMB.txt)
* [perftest](https://github.com/lsgunth/perftest/blob/master/README)

## Requirements - libraries

* ibverbs
* cuda (8)
* mpi

## Requirements - hardware

* Two compute node
* Nvidia - GPU Direct RDMA compatible cards (at least one per node) 
* Infiniband compatible network interface cards (at least one per node) 
