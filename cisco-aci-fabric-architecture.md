# Cisco ACI Fabric Architecture

## Overview

Cisco Application Centric Infrastructure (ACI) provides centralized policy-based management for modern data center networks.

## Core Components

### APIC

- Centralized management controller
- Policy management
- Automation and orchestration

### Spine Switches

- High-speed fabric backbone
- Forward traffic between leaf switches
- No endpoint learning

### Leaf Switches

- Connect servers and endpoints
- Enforce policies
- Learn endpoint locations

## ACI Logical Model

### Tenant

Represents an organizational unit or business group.

### VRF

Provides Layer 3 isolation.

### Bridge Domain

Provides Layer 2 forwarding domain.

### Application Profile

Groups related applications together.

### Endpoint Group (EPG)

Collection of endpoints sharing common policies.

## Policy Model

### Contracts

- Define communication rules
- Control traffic between EPGs

### Filters

- Specify permitted protocols
- Define ports and services

## External Connectivity

### L3Out

- Connects ACI fabric to external networks
- Supports OSPF
- Supports BGP
- Supports Static Routing

## High Availability

- Redundant Spine Architecture
- Dual-Homed Connectivity
- APIC Cluster Redundancy

## Monitoring

- APIC Health Scores
- Fabric Faults
- Endpoint Tracking
- Interface Statistics

## Benefits

- Centralized Management
- Automated Provisioning
- Application Visibility
- Scalable Data Center Architecture

## Real-World Example

Implemented Cisco ACI fabric for enterprise data center environments with multi-tenant segmentation, policy-based communication, and BGP-based external connectivity through L3Out integration.
