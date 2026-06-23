# Cisco ACI Tenant, VRF, Bridge Domain, and EPG Guide

## Overview

Cisco ACI uses a policy-driven architecture where applications, endpoints, and network services are organized into logical objects such as Tenants, VRFs, Bridge Domains, and Endpoint Groups (EPGs).

---

## Tenant Overview

A Tenant is the highest-level logical container within Cisco ACI.

### Purpose

- Provides administrative separation
- Supports multi-tenancy
- Isolates network resources

### Examples

- Production Tenant
- Development Tenant
- DMZ Tenant

---

## VRF Design

A Virtual Routing and Forwarding (VRF) instance provides Layer 3 isolation.

### Benefits

- Separate routing tables
- Traffic isolation
- Overlapping IP support

### Example

Production VRF

- 10.10.0.0/16

Development VRF

- 10.20.0.0/16

---

## Bridge Domains

Bridge Domains (BDs) provide Layer 2 forwarding domains within a VRF.

### Functions

- ARP Flooding Control
- Gateway Configuration
- Subnet Association

### Example

Production-BD

Subnet:

10.10.10.0/24

Application-BD

Subnet:

10.10.20.0/24

---

## Endpoint Groups (EPGs)

EPGs contain endpoints that share the same policies.

### Examples

Web-EPG

- Web Servers

App-EPG

- Application Servers

DB-EPG

- Database Servers

### Benefits

- Simplified policy assignment
- Application-based segmentation
- Security enforcement

---

## Contracts

Contracts define communication rules between EPGs.

### Example

Web-EPG → App-EPG

Allow:

- TCP 443
- TCP 8080

App-EPG → DB-EPG

Allow:

- TCP 1433
- TCP 3306

### Benefits

- Micro-segmentation
- Controlled communication
- Policy-based security

---

## Filters

Filters specify permitted protocols and ports.

### Examples

HTTP Filter

- TCP 80

HTTPS Filter

- TCP 443

Database Filter

- TCP 1433

---

## L3Out Connectivity

L3Out connects the ACI fabric to external networks.

### Supported Routing Protocols

- BGP
- OSPF
- Static Routing

### Common Use Cases

- Internet Connectivity
- WAN Connectivity
- Data Center Interconnect
- MPLS Connectivity

---

## Best Practices

### Tenant Design

- Separate Production and Development
- Use consistent naming standards

### VRF Design

- Minimize route leakage
- Use dedicated VRFs for security zones

### Bridge Domains

- Avoid unnecessary Layer 2 extensions
- Keep subnet design simple

### EPG Design

- Group applications logically
- Apply least-privilege communication

### Contracts

- Permit only required traffic
- Document all application flows

---

## Troubleshooting Tips

### Verify Endpoint Learning

Check:

- Endpoint Location
- MAC Address Learning
- IP Learning

### Verify Contracts

Check:

- Contract Associations
- Subject Configuration
- Filter Entries

### Verify L3Out

Check:

- BGP Neighbor State
- OSPF Adjacencies
- Route Advertisements

### Verify Health Scores

Monitor:

- APIC Health
- Fabric Health
- Node Health

---

## Real-World Example

Implemented Cisco ACI multi-tenant architecture using dedicated VRFs, Bridge Domains, EPGs, and Contracts to provide secure application segmentation and policy-based communication across enterprise data center environments.
