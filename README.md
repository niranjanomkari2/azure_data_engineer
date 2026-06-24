# Azure Data Factory Incremental Load Pipeline, On Prem Ingestion copying files from local to data lake, Web API call to read from git API to data lake

## Overview for Incremental Load Pipeline
This project demonstrates an incremental data load pattern using watermark logic.

## Key Features
- Lookup activity for last and latest load timestamps
- Incremental SQL extraction
- Data Lake storage (ADLS Gen2)
- Watermark file overwrite strategy

## Tech Stack
- Azure Data Factory
- Azure Data Lake Gen2
- SQL Server

## Pipeline Flow
1. Read last watermark (lastload.json) - for initial load it is any random date - '1900-01-01'
2. Fetch latest watermark from source - Max booking date from LastestLoad lookup
3. Load incremental data
4. Overwrite watermark file

## Key Learning
- Keep a empty.json file and overide latestLoad max value to it after the copy activity is successfully complete using another copy activity
- If the empty.json already has the existing column to be overriden, duplicate value error will be thrown.

<img width="1115" height="692" alt="image" src="https://github.com/user-attachments/assets/03f18aad-83c4-497e-b8d8-37738d5fbee5" />

<img width="565" height="340" alt="image" src="https://github.com/user-attachments/assets/32ea5167-8da8-4a20-903d-cc8947ff6bf9" />
<img width="670" height="262" alt="image" src="https://github.com/user-attachments/assets/46dafde3-ed07-440e-bbf4-be80e5937232" />
# OnPrem Ingestion:
<img width="1246" height="390" alt="image" src="https://github.com/user-attachments/assets/a64e58ac-5ebb-40fc-9ba9-95dbd924bcd9" />

# Web API - GitHub Ingestion
<img width="1206" height="371" alt="image" src="https://github.com/user-attachments/assets/108b35c9-c54d-4cc4-a56b-c047016a4b30" />



