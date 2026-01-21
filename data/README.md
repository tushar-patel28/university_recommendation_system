# Data Directory

This directory contains the dataset used for the university recommendation analysis.

## Dataset

**File**: `us-colleges-and-universities.xlsx`  
**Size**: ~1.2 MB  
**Format**: Excel spreadsheet

### Dataset Contents

The dataset includes comprehensive information about US colleges and universities:

- **Institution Information**: Name, state location, institution type
- **Enrollment Data**: Total, full-time, and part-time student counts
- **Staffing**: Total employee numbers
- **Facilities**: Dormitory capacity, housing availability
- **Geographic Data**: Latitude, longitude, urbanicity classification
- **Size Classifications**: Institution size categories

### Key Variables

| Variable | Description | Example Values |
|----------|-------------|----------------|
| `NAME` | Institution name | "Harvard University" |
| `STATE` | State abbreviation | "MA", "CA", "NY" |
| `TYPE` | Institution type | 1=Public, 2=Private Non-Profit, 3=Private For-Profit |
| `TOT_ENROLL` | Total enrollment | Numbers or "-999" for missing |
| `FT_ENROLL` | Full-time enrollment | Numbers or "-999" for missing |
| `PT_ENROLL` | Part-time enrollment | Numbers or "-999" for missing |
| `TOT_EMP` | Total employees | Numbers or "-999" for missing |
| `DORM_CAP` | Dormitory capacity | Numbers or "-999" for missing |
| `HOUSING` | Housing available | 1=Yes, 2=No, -1=Not reported |
| `LOCALE` | Urbanicity code | 11-13=City, 21-23=Suburb, etc. |

### Data Quality Notes

- Missing values are coded as `-999` and are converted to `NA` during preprocessing
- Some institutions may have incomplete data for certain variables
- The R script includes comprehensive data cleaning procedures

## Usage

The R analysis script automatically loads this file from:
```r
read_excel("data/us-colleges-and-universities.xlsx")
```

Make sure this file is present in the data directory before running the analysis.

## Data Source

For information about the original data source and methodology, please refer to the project reports in the `reports/` directory.
