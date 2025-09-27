# Introduction<br>
## Running
k3s<br>
* Control plane with two node cluster<br>
* Manage my containers
  
Docker<br>
* Containerize and run my applications 
  
Ansible<br>
* Using a playbook to update and configure all the nodes

## Hardware
Control Node<br>
* Intel(R) Core(TM) i5-6400 CPU @ 2.70GHz<br>
* 2x8GiB System Memory DIMM DDR3 Synchronous 1600MHz<br>
* Ubuntu 24.04 LTS<br>

Worker Nodes<br>
* 2x[Raspberry Pi 5 (8GiB)](https://www.raspberrypi.com/products/raspberry-pi-5/)
* Raspberry Pi OS

### Purpose 
* To learn how to create and a run a full CI/CD Pipeline<br>
* The homelab will run two Docker containers using Kubernetes<br>
* The pipeline will run the application [carnac](https://github.com/dodderingstalwart/carnac) (currently running locally only)<br>
* Learn Google Cloud by keeping data in cloud bucket<br>
