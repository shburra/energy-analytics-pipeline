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

### Step 4 – Configure Secure Access (Connection String)

**Goal:** Enable secure local access to Azure Data Lake from Python scripts.

**Steps:**
1. Retrieved connection string from Azure → Access Keys → Key1.
2. Saved it locally in `.env` file (not committed to Git).


### Step 6 – Create Azure SQL Database

**Goal:** Central relational warehouse for processed energy + weather data.

| Setting | Value |
|----------|--------|
| Database name | sqldb-energy-analytics |
| Server | sqlsrvenergydev.database.windows.net |
| Region | Germany West Central |
| Tier | Basic |
| Auth method | SQL login (adminuser) |
| Networking | Public endpoint + Allow Azure services |
| Tags | project=energy-analytics, env=dev, owner=shk |

**Connection String:** stored locally in `.env`  
**Status:** ✅ Created on 02.11.2025  
**Next:** Connect via Python and create tables (schema setup).

