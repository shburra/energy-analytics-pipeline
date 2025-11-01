# Azure Setup Log

### Step 1 – Create Resource Group

**Goal:** Organize all Azure resources for the Energy Analytics project.

**Details**
az group create \
  --name rg-energy-analytics-dev \
  --location germanywestcentral \
  --tags project=energy-analytics env=dev owner=shk
  


### Step 2 – Create Azure Storage Account (Data Lake Gen2)

**Goal:** Store raw and processed data (CSV / API outputs) for the Energy Analytics Pipeline.

**Details**
| Setting | Value |
|----------|--------|
| Resource Group | rg-energy-analytics-dev |
| Storage Account Name | stenergyanalyticsdev |
| Region | Germany West Central |
| Hierarchical Namespace | Enabled (Data Lake Gen2) |
| Redundancy | LRS |
| Tags | project=energy-analytics, env=dev, owner=shk |

**Status:** ✅ Created on <date>  
**Next:** Create a container structure (raw / processed / logs).

