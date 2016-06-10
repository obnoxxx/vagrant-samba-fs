# Samba File Server in a Container

This repository contains a Vagrantfile that describes the
setup of a simple Samba file server in a fedora-LXC host.

This is useful for testing/development of Samba.

In short:

* setup controlled by vagrant
* LXC-Containers as basis
* node OS: Fedora 23

## Configuration

This Vagrantfile is parametrized: The options for configuring
the number of nodes and the nodes' network interfaces and addresses
are stored in the config file 'vagrant.yml' when running any
vagrant command (except for vagrant help). The whole setup can
then conveniently be reconfigured modifying that file.

## Prerequisites

* Linux host, attached to the network (tested on Fedora 23, should work on other hosts as well)
* lxc installed
* vagrant installed
* vagrant-lxc plugin installed
* possibly preparation of bridge interfaces on the host (the example uses libvirt's `virbr` interfaces)

## Running

After adjusting the configuration, `vagrant up` will bring up the full
cluster with ctdb running on all nodes. `vagrant ssh` will ssh
into the samba server.

## TODO

- do provisioning with [ansible](https://github.com/ansible/ansible)
- add mechanism to join existing AD domain (e.g. samba-AD)

## Author

Michael Adam (obnox at samba dot org)
