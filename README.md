# htb_implement
Implementation of hierarchical token buckets in POX. This code just shows how to setup a simple token bucket in a topology.
Two files are required for this. The file in `in_mininet` is used to setup the topology. The file in `in_pox` contains the controller.

## Prerequisites
* Mininet
* Pox

## Where to place files
* Put the files from the folder `in_mininet` into `mininet/custom`
* Put the files from the folder `in_pox` into `pox/pox/forwarding`

## How to execute the controller
* From inside the `mininet/custom` directory, run the following command
```
sudo python topology_queue.py
```
* From inside the `pox` directory, run the following command
```
sudo ./pox.py log.level --DEBUG forwarding.controller_queue
```

## To test the topology
* From inside the mininet console run the command `iperf h3 h1`
* This should give a bandwidth of ~6 Mbps. Queue 1 is being used
* Run the command `iperf h4 h1`
* This should give a bandwidth of ~4 Mbps. Queue 2 is being used
