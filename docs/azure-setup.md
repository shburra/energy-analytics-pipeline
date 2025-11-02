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

### Step 3 – Create Data Lake Containers

**Goal:** Logical data organization inside Azure Data Lake Gen2.

| Container | Access | Purpose |
|------------|---------|----------|
| raw | Private | Store raw CSV/API data from SMARD.de and OpenWeather |
| processed | Private | Store transformed, cleaned datasets |
| logs | Private | Store ETL run logs or temporary files |

**Status:** ✅ Created on <date>  
**Next:** Configure Access Keys / Connection String to access the Data Lake from Python.

