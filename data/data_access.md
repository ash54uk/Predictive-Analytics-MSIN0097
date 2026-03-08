# Data Access Instructions

The data used in this project is publicly available from the UK Department for Transport and is not included in this repository due to file size.

## Download Instructions

1. Go to the STATS19 Road Safety Data page:  
   https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data

2. Download the following three files for the year **2024**:
   - `dft-road-casualty-statistics-collision-2024.csv`
   - `dft-road-casualty-statistics-vehicle-2024.csv`
   - `dft-road-casualty-statistics-road-safety-open-dataset-data-guide-2024.xlsx`

## Setup

Once downloaded, place all three files in a local folder of your choice.

Then open the notebook (`MSIN0097_Predictive_Analytics_AKS.ipynb`) and update the following two variables at the top of Step 2 to point to your local folder:

```python
BASE_PATH = '/your/local/path/to/data/'
DATA_PATH = '/your/local/path/to/data/'
```

## Licence

This data is published by the Department for Transport under the  
**Open Government Licence v3.0**:  
https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/
