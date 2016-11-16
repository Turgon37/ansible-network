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
| network__ether_interfaces          |  The list of ethernet interfaces to be added to the sytem |
| network__bridge_interfaces         |  The list of bridge interfaces to be added to the sytem   |
| network__vlan_interfaces           | The list of vlan interfaces to be added to the sytem      |
| network__dhcp_hostname           | The hostname to use when the host introduce itself to the DHCP server (for distribution that allow this parameter)      |
| network__conflict_pkgs           | The list of package(s) that conflict with this role (commonly NetworkManager)  |

### Example

  * Simple ethernet network

```
network__ether_interfaces:
  - device: 'eth0'
    name: net
    type: ethernet
    onboot: True
    bootproto: static
    ipv4:
      address: 192.168.1.1
      netmask: 255.255.255.0
      gateway: 192.168.1.254
```

  * Simple ethernet network with DNS (resolv.conf) and route

```
network__ether_interfaces:
  - device: 'eth0'
    name: common
    type: ethernet
    onboot: True
    bootproto: static
    ipv4:
      address: 192.168.1.1
      netmask: 255.255.255.0
      gateway: 192.168.1.254
      route:
        - network: 10.0.1.0
          netmask: 255.255.255.0
          gateway: 192.168.1.250
    domain: domain.com
    dns:
    - 192.168.1.254