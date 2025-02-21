# CAVER-P4
CAVER: Enhancing RDMA Load Balancing by Hunting Less-Congested Paths

This repository incudes p4 programs of CAVER. We used `BF-SDE-9.4.0` to compile and run the program.

## 1.Topology Settings
We provide the details of the topology used in our source code, including switch ports and NIC IP configurations in picture `topo.pdf`. 

In our topology, each link utilizes a 100Gbps data cable, with a total of two Tofino 1 switches deployed. Each switch is configured with two pipelines, effectively virtualizing each switch into two logical switches. The network interface cards (NICs) used are Mellanox ConnectX-6, which support up to 100Gbps.

If you use a different topology, please update the `switch_config.h` file accordingly.

The `Caver_ToR` folder should be downloaded to the lower-layer switches, while the `Caver_Middle` folder should be downloaded to the upper-layer switches.

## 2.Build P4 and controller code
1.Download p4_build.sh and place it in the `$(SDE)` directory on each switch.

2.Build P4 and controller code using `make` on each switch.

## 3.Run
1.Run the controller and switch p4 program using `./test` on both switch, then both swtiches are ready to switch packets!
