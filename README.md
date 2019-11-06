# Deploy ESXi+vsphere lab on libvirt

## Description

This playbook will deploy:

- a local vsphere
- two ESXi
- a datastore VM (with a NFS)

It can easier target a local Libvirt hypervisor, or an OpenStack tenant.

## Requirements

- a Python virtualenv
- Virt-Lightning (for Libvirt)
- memory 20GB
- vcpus: 2 for vcenter, 1 for ESXi, more will probably seriously increase the performance
- Ansible 2.8+
- Qcow2 Images:
    - ESXi: https://github.com/virt-lightning/esxi-cloud-images
    - vcenter: https://github.com/goneri/vcsa_to_qcow2

## Installation

    virtualenv -p python3.7 .virtualenv/py37
    source .virtualenv/py37/bin/activate
    pip install -r requirements.txt
    ./run.py --driver openstack deploy

## Usage

Just use the `--help` argument:

    ./run.py --help

For instance, to start a deployment:

    ./run.py --driver openstack deploy


