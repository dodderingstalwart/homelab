# Introduction<br>
The main purpose of this homelab is to learn about Kubernetes, containers and all the tools to have a CI/CD pipeline.  I created my website and wanted to self-host it on my own hardware.  This homelab has been difficult as I try to understand why and what tools are necessary to be able to run my application.  As I continue to learn and add more tools, I will document the process the best I can.<br>

## Running
k3s<br>
* Control plane with two node cluster.<br>
* Manage the website in the containers.<br>
* Have persistent volumes for jokes/insults.<br>
  
Docker<br>
* Containerize the website and applications.
  
Ansible<br>
* Using a playbook to update and configure all the nodes.

Prometheus<br>
* Using Prometheus services to monitor the cluster.

Flux<br>
* GitOps to manage the kubernetes cluseter.

nginx<br>
* Load balancer running on the master node.

## Hardware
Control Node<br>
* Intel(R) Core(TM) i5-6400 CPU @ 2.70GHz<br>
* 2x8GiB System Memory DIMM DDR3 Synchronous 1600MHz<br>
* Ubuntu 24.04 LTS<br>

Worker Nodes<br>
* 2x[Raspberry Pi 5 (8GiB)](https://www.raspberrypi.com/products/raspberry-pi-5/)
* Raspberry Pi OS
* Using USB storage

### Purpose 
* To learn how to create and a run a full CI/CD Pipeline.<br>
* The homelab will run two Docker containers using Kubernetes.<br>
* The pipeline will run my website. (https://github.com/dodderingstalwart/dodderingstalwart.github.io) (currently running locally only).<br>

## Currently
* Currently switching to run k3s with Ansible for better automation 

### Future
* To help learn Google Cloud API by using cloud bucket to host data.<br>
* Push database into self-hosted deepseek for training on Carnac insults/jokes.<br> 
