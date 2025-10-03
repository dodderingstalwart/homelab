# Introduction<br>
## Running
k3s<br>
* Control plane with two node cluster.<br>
* Manage the carnac containers.<br>
* Have persistent volumes for jokes/insults<br>
  
Docker<br>
* Containerize to run the applications.
  
Ansible<br>
* Using a playbook to update and configure all the nodes.

## Hardware
Control Node<br>
* Intel(R) Core(TM) i5-6400 CPU @ 2.70GHz<br>
* 2x8GiB System Memory DIMM DDR3 Synchronous 1600MHz<br>
* Ubuntu 24.04 LTS<br>

Worker Nodes<br>
* 2x[Raspberry Pi 5 (8GiB)](https://www.raspberrypi.com/products/raspberry-pi-5/)
* Raspberry Pi OS
* Using nvme storage

### Purpose 
* To learn how to create and a run a full CI/CD Pipeline.<br>
* The homelab will run two Docker containers using Kubernetes.<br>
* The pipeline will run the application [carnac](https://github.com/dodderingstalwart/carnac) (currently running locally only).<br>

## Currently
* Currently switching to run k3s with Ansible for better automation 

### Future
* To help learn Google Cloud API by using cloud bucket to host data.<br>
* Push database into self-hosted deepseek for training on Carnac insults/jokes.<br> 
