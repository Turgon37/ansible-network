Ansible Role network
========

This roles allow configuration of network components such interface, address(es), dns, vlan

## OS Family

This role is available for Debian and CentOS

## Features

At this day the role can be used to configure :

  * Ethernet Interfaces
  * Bridge Interfaces
  * Vlan interfaces
  * IPv4 addresses
  * route(s) per interface
  * dns serveur
  * dns search and domain


## Configuration

The variables that can be passed to this role and a brief description about them are as follows:

| Name                              | Description                                               |
| --------                          | --------------------------------------------------------- |
| network_ether_interfaces          |  The list of ethernet interfaces to be added to the sytem |
| network_bridge_interfaces         |  The list of bridge interfaces to be added to the sytem   |
| network_vlan_interfaces           | The list of vlan interfaces to be added to the sytem      |