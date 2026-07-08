# Cisco ACI Contracts and Filters Overview

## Overview

Cisco ACI uses contracts and filters to control communication between Endpoint Groups (EPGs). This policy-based approach replaces traditional ACL-centric network segmentation.

## Key Components

### Endpoint Groups (EPGs)

- Group endpoints with similar policies
- Define application tiers
- Simplify policy management

### Contracts

Contracts define which traffic is allowed between a provider EPG and a consumer EPG.

### Filters

Filters specify the permitted traffic by matching:

- Protocol
- Source Port
- Destination Port
- TCP Flags (if required)

## Traffic Flow

Consumer EPG
        ↓
     Contract
        ↓
      Filter
        ↓
Provider EPG

## Common Use Cases

- Web-to-Application communication
- Application-to-Database access
- Shared infrastructure services
- DNS and NTP access
- Backup network communication

## Verification

- Verify contract association
- Validate filter entries
- Check endpoint learning
- Review fault records
- Confirm tenant and VRF configuration

## Best Practices

- Apply least-privilege access
- Reuse common contracts where appropriate
- Use descriptive naming conventions
- Document provider/consumer relationships
- Validate policies before production deployment
