# DC1_FABRIC

## Table of Contents

- [DC1_FABRIC](#dc1fabric )
  - [Fabric Switches and Management IP](#fabric-switches-and-management-ip)
  - [Fabric Topology](#fabric-topology)
  - [Fabric IP Allocation](#fabric-ip-allocation)
    - [Fabric Point-To-Point Links](#fabric-point-to-point-links)
    - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
    - [Overlay Loopback Interfaces (BGP EVPN Peering)](#overlay-loopback-interfaces-bgp-evpn-peering)
    - [Loopback0 Interfaces Node Allocation](#loopback0-interfaces-node-allocation)
    - [VTEP Loopback VXLAN Tunnel Source Interfaces (Leafs Only)](#vtep-loopback-vxlan-tunnel-source-interfaces-leafs-only)
    - [VTEP Loopback Node allocation](#vtep-loopback-node-allocation)

## Fabric Switches and Management IP

| Node | Management IP | Platform |
| ---- | ------------- | -------- |
| DC1-SPINE1 | 192.168.1.252/24 | vEOS-LAB |
| DC1-LEAF1A | 192.168.1.250/24 | vEOS-LAB |
| DC1-LEAF2A | 192.168.1.251/24 | vEOS-LAB |

## Fabric Topology

| Type | Leaf Node | Leaf Interface | Peer Node | Peer Interface |
| ---- | --------- | -------------- | --------- | -------------- |
| L3 Leaf | DC1-LEAF1A | Ethernet47 | DC1-SPINE1 | Ethernet47 |
| L3 Leaf | DC1-LEAF2A | Ethernet47 | DC1-SPINE1 | Ethernet48 |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| P2P Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ----------- | ------------------- | ------------------ | ------------------ |
| 10.0.0.0/24 | 256 | 4 | 1.57 % |

### Point-To-Point Links Node Allocation

| Leaf Node | Leaf Interface | Leaf IP Address | Spine Node | Spine Interface | Spine IP Address |
| --------- | -------------- | --------------- | ---------- | --------------- | ---------------- |
| DC1-LEAF1A | Ethernet47 | 10.0.0.1/31 | DC1-SPINE1 | Ethernet47 | 10.0.0.0/31 |
| DC1-LEAF2A | Ethernet47 | 10.0.0.3/31 | DC1-SPINE1 | Ethernet48 | 10.0.0.2/31 |

### Overlay Loopback Interfaces (BGP EVPN Peering)

| Overlay Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------------ | ------------------- | ------------------ | ------------------ |
| 1.1.1.0/24 | 256 | 3 | 1.18 % |

### Loopback0 Interfaces Node Allocation

| Node | Loopback0 |
| ---- | --------- |
| DC1-SPINE1 | 1.1.1.1/32 |
| DC1-LEAF1A | 1.1.1.2/32 |
| DC1-LEAF2A | 1.1.1.3/32 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (Leafs Only)

| VTEP Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| --------------------- | ------------------- | ------------------ | ------------------ |
| 2.2.2.0/24 | 256 | 2 | 0.79 % |

### VTEP Loopback Node allocation

| Node | Loopback1 |
| ---- | --------- |
| DC1-LEAF1A | 2.2.2.2/32 |
| DC1-LEAF2A | 2.2.2.3/32 |
