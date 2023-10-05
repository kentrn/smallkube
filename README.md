# smallkube
This playbook will configure a 1 master + 2 worker node Kubernetes cluster that can ideally be used for development. It has been configured to use the latest version of CentOS 9 Stream and Kubernetes 1.28.1. It should work for older releases of Kubernetes (v1.24+) but this is untested. 

This project implements the following as core Kubernetes cluster components:
* Container Runtime Interface: cri-o
* Container Network Interface: OVN-Kubernetes

This setup assumes that you have connectivity to the internet to pull images.

## Setup Instructions
To get started you will need to do the following:
1. Provision your VMs on a physical host using your preferred VM hypervisor (VMWare/KVM/VirtualBox). This setup assumes bridged adaptor mode for ease of configuration.
2. Edit the `hosts` file to use the ip addresses of your provisioned vms. 
3. Prep your machines to enable ansible execution (ensure `ssh` rpm is installed, a user account with root access is available and optionally ssh-key based authentication enabled)

## TODO:
1. Implement CNI interface.
2. Implement a bastion host as loadbalancer/dns/dhcp.
3. Configure setup to support 3-node control + worker setup.