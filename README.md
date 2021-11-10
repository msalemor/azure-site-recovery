# Azure Site Recovery

Design a site recovery strategy with Azure Site Recovery

## Goals

### How site recovery works

- BC/CR
  - Replicate VM over regions
  - Replicate on-prem machines into Azure (VMWare, Physical Servers, Hyper-V)
  - Provides continous replication
- Replication
  - Creates repliation points or app consistent snapshots
  - Planned or Unplanned failover
- Recovery plans
  - coordinate how VMs are recovered
- Azure Automation Integration
- Replicaties Application agnostic workloads

### Use cases

- Disaster recovery
- Migration (typically on-prem to Azure)

### Replication Azure VMs

#### Source Region

- VMs should be in a VNET and Subnet
- VMs should have disks associated to them in the storage account in the region
- Install Extension Mobility Service on the VMS to be backed-up 
  - Used to manage the failover/fallback
- In the same region create a storage account to hold the cache data to help with replication performance

#### Target Region

- Create a VNET and Subnet
- Create a storage account
- Resources can be pre-created by an admin or created by Azure Site Recovery

## Site Recovery Resoursce

## Failover/Fallback strategies
