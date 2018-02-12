# OSU Micro-Becnchmarks

The following settings and scripts were used to perform test with OSU Micro-Benchmark tool.

## Test
$NODE01 and $NODE02 are the names of interested host. $PATH2OSU is the directory of OSU tool. If You can not ensure that the rigth CPU, GPU and Network interface card are selected, then use script to prepare the proper environment.

### Bandwitdh between Hosts
```bash
mpiexec -np 2 -npernode 1 -host $NODE01,$NODE02 $PATH2OSU/mpi/pt2pt/osu_bw
```
$NODE01 and $NODE02 are the names of interested host.

### Latency between Hosts
```bash
mpiexec -np 2 -npernode 1 -host $NODE01,$NODE02 $PATH2OSU/mpi/pt2pt/osu_latency
```
### Bandwitdh between GPUs on different nodes without GPU Direct RDMA
```bash
mpiexec -np 2 -npernode 1 -host $NODE01,$NODE02 -mca btl_openib_want_cuda_gdr 0 $PATH2OSU/mpi/pt2pt/osu_bw -d CUDA D D
```

### Latency between GPUs on different nodes without GPU Direct RDMA
```bash
mpiexec -np 2 -npernode 1 -host $NODE01,$NODE02 -mca btl_openib_want_cuda_gdr 0 $PATH2OSU/mpi/pt2pt/osu_latency -d CUDA D D
```

### Bandwitdh between GPUs on different nodes with GPU Direct RDMA
```bash
mpiexec -np 2 -npernode 1 -host $NODE01,$NODE02 -mca btl_openib_want_cuda_gdr 1 -mca btl_openib_cuda_rdma_limit 1342177280 $PATH2OSU/mpi/pt2pt/osu_bw -d CUDA D D
```

### Latency between GPUs on different nodes with GPU Direct RDMA
```bash
mpiexec -np 2 -npernode 1 -host $NODE01,$NODE02 -mca btl_openib_want_cuda_gdr 1 -mca btl_openib_cuda_rdma_limit 1342177280 $PATH2OSU/mpi/pt2pt/osu_latency -d CUDA D D
```




