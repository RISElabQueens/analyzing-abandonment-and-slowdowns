# Replication Package: Understanding Abandonment and Slowdown Dynamics in the Maven Ecosystem (MSR 2025)

**Authors**: Kazi Amit Hasan, Jerin Yasmin, Huizi Hao, Yuan Tian, Safwat Hassan, Steven Ding

## Overview
This repository contains all data and code required to replicate our study investigating abandonment patterns and  slowdowns in the Maven ecosystem. 

## Repository Structure
```
.
├── Data/
│   ├── data.zip           # Compressed analysis-ready dataset
│   └── queries.md         # Neo4j Cypher queries for raw data extraction
├── RQ1/
│   └── rq1.ipynb          # Jupyter notebook for RQ 1
├── RQ2/
│   ├── rq2_quartile_v1_ab_std.ipynb      
│   ├── rq2_quartile_v1_active_std.ipynb   
│   ├── rq2_speed_x_lifespan_active    
│   └── rq2_speed_x_lifespan_abandoned   
├── requirements.txt       # Python package dependencies
└── README.md             
```

## Requirements
- Python 3.10+
- Jupyter Notebook
- 7-Zip or equivalent for data extraction
- Neo4j 4.4.11 (optional, only for raw data re-extraction)

## Setup Instructions
1. **Download Data**:  
   Get `data.zip` from [Google Drive](https://drive.google.com/drive/folders/1AJLes5f-SSUgTGcQt4Kfg6peYRpBtF1R)

2. **Extract Data**:  
   Unzip contents to `Data/` folder:
   ```bash
   unzip data.zip -d ./Data
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Contact
For technical assistance or data inquiries:  
Kazi Amit Hasan: `[kaziamit.hasan@queensu.ca]`  


<!-- ## Citation
```bibtex
@article{hasan2024maven,
  title={Understanding Abandonment and Slowdown Dynamics in the Maven Ecosystem},
  author={Hasan, Kazi Amit and Yasmin, Jerin and Hao, Huizi and Tian, Yuan and Hassan, Safwat and Ding, Steven},
  journal={[Journal Name]},
  year={2024},
  publisher={[Publisher]}
}
``` -->

