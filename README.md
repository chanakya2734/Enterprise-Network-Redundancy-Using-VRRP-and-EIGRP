
# Enterprise Network Redundancy Design using VRRP and EIGRP

## Project Overview

This project demonstrates the implementation of a highly available enterprise network using Virtual Router Redundancy Protocol (VRRP) and Enhanced Interior Gateway Routing Protocol (EIGRP) in GNS3.

The network is designed to provide gateway redundancy and uninterrupted connectivity. Two routers act as redundant gateways for the LAN, while EIGRP provides dynamic routing between all routers.

---

## Objectives

* Implement gateway redundancy using VRRP.
* Configure dynamic routing using EIGRP.
* Provide high availability for end users.
* Test failover functionality between Master and Backup routers.
* Verify connectivity using Ping and Traceroute.

---

## Technologies Used

* GNS3
* Cisco IOS Routers
* EIGRP
* VRRP
* ICMP
* Traceroute

---

## Network Topology

Topology image is available in:

topology/VRRP_Topology.png

---

## IP Addressing

### LAN Network

| Device          | IP Address    |
| --------------- | ------------- |
| PC1             | 192.168.2.1   |
| PC2             | 192.168.2.2   |
| Virtual Gateway | 192.168.2.250 |

### Router Interfaces

| Router | Interface | IP Address    |
| ------ | --------- | ------------- |
| R1     | e6/0      | 192.168.2.100 |
| R2     | e6/0      | 192.168.2.101 |
| R1     | g1/0      | 192.168.12.1  |
| R2     | g1/0      | 192.168.12.2  |
| R1     | g2/0      | 192.168.13.1  |
| R3     | g2/0      | 192.168.13.3  |
| R2     | g2/0      | 192.168.23.2  |
| R3     | g1/0      | 192.168.23.3  |

---

## EIGRP Configuration

* Autonomous System Number: 90
* Dynamic route exchange between R1, R2 and R3
* Automatic route learning and convergence

---

## VRRP Configuration

### Master Router

* Router: R1
* Virtual IP: 192.168.2.250
* Priority: 150

### Backup Router

* Router: R2
* Virtual IP: 192.168.2.250
* Priority: 100

---

## Verification

### Router Connectivity Test

* Verified connectivity to Loopback Address 8.8.8.8
* Successful ping response received

### Traceroute Test

* Traceroute performed from PC1
* Verified packet forwarding through the active VRRP gateway

### Routing Verification

* Verified EIGRP route learning using:

  * show ip route
  * show ip eigrp neighbors

---

## Screenshots

Available in the screenshots folder:

* Router1_Ping_Test.png
* PC1_Traceroute_Test.png
* EIGRP_Routing_Table.png

---

## Project Structure

Enterprise-Network-Redundancy-Using-VRRP-and-EIGRP

├── README.md

├── topology

│   └── VRRP_Topology.png

├── screenshots

│   ├── Router1_Ping_Test.png

│   ├── PC1_Traceroute_Test.png

│   └── EIGRP_Routing_Table.png

├── configurations

│   ├── R1_Config.txt

│   ├── R2_Config.txt

│   └── R3_Config.txt

└── project_files

```
└── project.gns3
```

---

## Learning Outcomes

* Network Redundancy
* Gateway Failover
* High Availability Design
* EIGRP Dynamic Routing
* VRRP Configuration
* Enterprise Network Architecture
* Network Troubleshooting

---

## Author

Chanakya Burugu

Computer Science and Engineering

Networking and Infrastructure Enthusiast
