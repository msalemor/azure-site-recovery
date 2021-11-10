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
  - Planned: Zero data loss
  - Unplanned failover: data may be lost up to the replication point (can be adjusted)
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
- Data is copied from the cache storage account in the source region to the disks on the the storage account on the target region

#### Failover

- Replication stops
- VMs are brought on-line in the replicated region attached to the destination disks that were the target of replication

### Recovery Services Vault

#### Create a Service Vault from the Azure Portal

- From the portal search for: Recovery Service Vault
- Create a new resource group or select an existing one
- Name the vault
- Select the region
- Click: Review and Create

#### Select the source VMs

- Select the source region
- Select the VMS in the region

#### Select the target environment

- Resources can be created manually or by ASR
- Adjust the replication settings
- Start replication

## Site Recovery Infrastructure

## Site Recovery Resoursce

## Failover/Fallback strategies
