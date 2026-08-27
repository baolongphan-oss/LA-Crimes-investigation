# LA Crimes Investigation: Interactive Crime Analytics Dashboard

## Project Overview
This project analyzes Los Angeles crime data from 2020–2024 using official city records. The analysis involves data cleaning, preparation, and visualization in an interactive Tableau dashboard designed to help law enforcement and community stakeholders understand crime patterns across the city by type, location, time period, and demographics.

**Dataset Source:** [Crime Data from 2020 to 2024 dataset from data.gov](https://catalog.data.gov/dataset/crime-data-from-2020-to-present)

**Tableau Public Publication:** [LA Crimes 2010-2024](https://public.tableau.com/app/profile/long.phan6932/viz/LACrimes2010-2024/TimeofDay)

---

## Project Structure

```
LA-Crimes-investigation/
├── Crime_Data_from_2020_to_Present_20240111.csv.zip    (Raw data: 37 MB)
├── cleaned_crime_data.csv                               (Processed data: 28 MB)
├── cleaned_crime_data.csv+ (Multiple Connections).hyper.zip  (Tableau data source)
├── LACrimes.twbx                                        (Tableau workbook: interactive dashboard)
├── LACrimes.twb                                         (Tableau workbook: backup)
├── la_crimes.ipynb                                      (Python notebook: data cleaning & processing)
├── ethnicity.csv                                        (Reference data for demographics)
└── MO_CODES_Numerical_20180627.pdf                      (Crime code reference guide)
```

---

## 1. Data Loading & Exploration

### Objective
Import official LA crime data and assess its structure, completeness, and characteristics.

### Process
- Load raw crime CSV from LA Open Data portal (37 MB, 2020–2024 records)
- Inspect dataset dimensions, columns, and data types
- Assess data quality (missing values, duplicates, anomalies)
- Understand crime classification system (MO codes)

### Key Findings
- **Record Count**: 500,000+ crime incidents
- **Time Range**: 2020–2024 (4+ years of data)
- **Geographic Coverage**: All Los Angeles neighborhoods and districts
- **Crime Classifications**: 140+ distinct crime types mapped to MO codes
- **Data Quality**: Minimal missing values after cleaning

---

## 2. Data Cleaning & Preparation

### Objective
Transform raw data into a clean, normalized format suitable for analysis and visualization.

### Process

#### **Step 1: Handle Missing Values**
- Identified NULL values in key fields (location, crime type, date)
- Filled missing geographic coordinates using LA district mappings
- Removed records with critical missing information

#### **Step 2: Standardize Crime Codes**
- Mapped MO (Modus Operandi) codes to human-readable crime categories
- Consolidated similar crimes into broader categories for analysis
- Created hierarchical crime classification (crime family → specific type)

#### **Step 3: Geographic Normalization**
- Standardized location data (addresses, coordinates, districts)
- Added Los Angeles neighborhood/precinct mappings
- Validated latitude/longitude coordinates

#### **Step 4: Time Standardization**
- Parsed and standardized date/time formats
- Extracted temporal features (year, month, day of week, hour)
- Created time-based aggregation levels (daily, weekly, monthly, annual)

#### **Step 5: Create Derived Fields**
- Added demographic fields (victim ethnicity encoding)
- Created crime severity classifications
- Built season and time-of-day categorizations

### Output
- **Cleaned Dataset**: 28 MB CSV with 500,000+ records, standardized format
- **Hyper Extract**: Tableau-optimized data source for dashboard performance
- **Data Quality**: Zero critical missing values, validated records

---

## 3. Exploratory Data Analysis (Python Notebook)

### Objective
Understand patterns and trends in LA crime data before dashboard visualization.

### Analysis Performed

#### **Crime Type Distribution**
- Identified most common crime categories
- Analyzed crime frequency by type
- Ranked crimes by total incident count

#### **Geographic Patterns**
- Crime hotspots by neighborhood/district
- Spatial clustering of crime incidents
- High-crime vs. low-crime areas

#### **Temporal Trends**
- Crime rates over time (2020–2024)
- Seasonal patterns in crime
- Day-of-week and hour-of-day variations

#### **Demographic Analysis**
- Crime victim demographics by ethnicity
- Arrest outcomes and clearance rates
- Patterns in victim/suspect relationships

### Techniques Used
- **Pandas**: Data cleaning, groupby aggregations, merging datasets
- **Python**: Data validation and transformation scripting
- **Statistical Analysis**: Frequency distributions, trend analysis

---

## 4. Tableau Dashboard: Interactive Crime Analytics

### Objective
Create an interactive, user-friendly dashboard enabling stakeholders to explore LA crime data by multiple dimensions.

### Dashboard Structure

**14 Worksheets covering:**
- Crime type frequency and trends
- Geographic heat maps and district breakdowns
- Temporal analysis (monthly, seasonal, hourly patterns)
- Victim and suspect demographics
- Crime severity and clearance rates
- Year-over-year comparisons (2020–2024)

**5 Dashboards organized by audience:**
1. **Executive Overview** — High-level crime trends and top statistics
2. **Geographic Analysis** — Crime hotspots, district comparisons, neighborhood breakdowns
3. **Crime Type Deep Dive** — Specific crime categories, trends, and patterns
4. **Temporal Patterns** — Time-based analysis (hourly, daily, seasonal, annual)
5. **Demographic & Outcomes** — Victim/suspect demographics, arrest clearance rates

### Key Features
- **Interactive Filters** — Filter by date range, crime type, location, demographics
- **Drill-Down Capability** — Explore from city-level down to neighborhood-level detail
- **Trend Lines** — Visualize crime trends over the 4-year period
- **Geographic Visualization** — Map-based display of crime locations and density
- **Comparative Analysis** — Side-by-side district and crime type comparisons

### Use Cases
- **Law Enforcement**: Identify crime hotspots, allocate resources, plan operations
- **Community Safety**: Understand public safety trends in neighborhoods
- **Policy Makers**: Data-driven decisions on public safety initiatives
- **Researchers**: Analyze LA crime patterns for academic or policy studies

---

## Technical Skills Demonstrated

### Data Engineering
- Data cleaning and validation (Python, Pandas)
- Handling large datasets (37+ MB)
- Data normalization and standardization
- Multi-table joins and merging
- Creating optimized data sources for BI tools

### Data Visualization & BI
- Tableau dashboard design and development
- Interactive filtering and parameter controls
- Geospatial visualization (mapping)
- Multi-dimensional analysis
- User-centered design for stakeholder audiences

### Data Analysis
- Exploratory data analysis (EDA)
- Trend identification and time-series analysis
- Geographic and demographic pattern analysis
- Frequency and distribution analysis

---

## Key Insights & Findings

1. **Crime Concentration**: Certain neighborhoods show significantly higher crime rates; geographic targeting could improve resource allocation

2. **Temporal Patterns**: Crime varies by time of day and season; resource planning could reflect these patterns

3. **Crime Types**: Property crimes and theft are dominant categories; violent crime represents smaller but important subset

4. **Trending**: Overall crime trends and year-over-year changes provide context for public safety efforts

5. **Demographic Factors**: Victim demographics show patterns worth investigating for community-specific interventions

---

## Files & Deliverables

| File | Size | Purpose |
|------|------|---------|
| `Crime_Data_from_2020_to_Present_20240111.csv.zip` | 37 MB | Raw data from LA Open Data |
| `cleaned_crime_data.csv` | 28 MB | Processed, cleaned dataset ready for analysis |
| `cleaned_crime_data.csv+ (Multiple Connections).hyper.zip` | 16 MB | Tableau-optimized data extract |
| `LACrimes.twbx` | 18 MB | Tableau workbook (packaged with data) |
| `LACrimes.twb` | 6.4 MB | Tableau workbook (requires separate data connection) |
| `la_crimes.ipynb` | 64 KB | Python notebook with data cleaning code |
| `ethnicity.csv` | 271 B | Reference data for demographic encoding |
| `MO_CODES_Numerical_20180627.pdf` | 196 KB | LA Police crime code reference guide |

---

## How to Use This Project

### View the Dashboard
1. Open `LACrimes.twbx` in Tableau Desktop or Tableau Public
2. Explore the 5 dashboards using interactive filters
3. Drill down from city-level to neighborhood-level analysis
4. Export specific views or data for reports

### Reproduce the Analysis
1. Extract `Crime_Data_from_2020_to_Present_20240111.csv.zip`
2. Run `la_crimes.ipynb` to reproduce data cleaning steps
3. Connect Tableau to cleaned dataset to rebuild dashboards

### Extend the Project
- Add real-time data feeds for current crime monitoring
- Incorporate additional demographic data (census, socioeconomic)
- Develop predictive models for crime forecasting
- Integrate with community safety apps or public websites

---

## Tools & Technologies Used

- **Data Processing**: Python, Pandas, Jupyter Notebook
- **Data Visualization**: Tableau (Desktop/Public)
- **Data Format**: CSV, Hyper (Tableau optimized format)
- **Data Source**: LA Open Data Portal (official city records)

---

## Notes

- Dashboard designed for authorized law enforcement and community stakeholder access
- Data covers 2020–2024; older historical data available separately
- MO codes reference guide included (PDF) for crime classification interpretation
- All data is publicly available from LA Open Data portal

---

## Contact & Attribution

Project demonstrates data engineering, cleaning, and business intelligence dashboard development skills in a real-world public safety context.
