# Perftest

The following settings and scripts were used to perform test with 'perftest' tool.

## Test
$NODE01 and $NODE02 are the names of interested host. $PATH2PERF is the directory of 'perftest' tool.
To use 'perftest' tool one way is to login to interested nodes and run a server and client on the nodes. In this case You have to ensure that your tests are using the correct network interface cards and graphics cards.  


### Bandwitdh between Hosts:
On $NODE01
```bash
$PATH2PERF/ib_send_bw -a  
```
On $NODE02
```bash
$PATH2PERF/ib_send_bw -a $NODE01 
```

### Bandwitdh between GPU-s with GPU Direct RDMA:
On $NODE01
```bash
$PATH2PERF/ib_send_bw -a --use_cuda 
```
On $NODE02
```bash
$PATH2PERF/ib_send_bw -a --use_cuda $NODE01 
```








