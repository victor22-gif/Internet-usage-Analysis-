# Global Internet Usage Analysis (2000-2023)

## Project Overview
This project analyzes global internet usage trends across different continents and countries from 2000 to 2023. The analysis explores digital adoption rates, regional disparities, and growth patterns in internet penetration worldwide.

## Data Cleaning and Methodology

### Initial Dataset
- Source data included 217 countries
- 24 years of observations (2000-2023)
- 605 missing values identified in Internet Usage data
- Original features: Country Name, Country Code, Years (2000-2023)

### Data Preprocessing Steps

1. **Data Restructuring**
   - Transformed wide format (years as columns) to long format
   - Created new columns: Year, Internet Usage
   - Added Continent classification using `pycountry` and `pycountry_convert`

2. **Handling Missing Values**
   ```python
   # Initial missing value count
   Missing values:
   Country Name        0
   Country Code        0
   Year                0
   Weather Usage    605
   Continent           0
   ```

3. **Critical Decision: Oceania Data**
   - Attempted continental average imputation for missing values
   - Discovered insufficient data points for Oceania region
   - Identified persistent missing values in Oceania countries for 2023:
     * American Samoa
     * Australia
     * Fiji
     * French Polynesia
     * Guam
     * Kiribati
     * Marshall Islands
     * Micronesia
     * New Caledonia
     * New Zealand
     * Papua New Guinea
     * Solomon Islands
     * Tonga
     * Tuvalu
     * Vanuatu
   - Made methodological decision to exclude Oceania countries due to data sparsity

4. **Final Data Cleaning**
   - Dropped all Oceania countries from dataset
   - Successfully imputed remaining missing values using continental averages
   - Final dataset: 5,183 observations
   - Covering Africa, Asia, Europe, North America, and South America

## Analysis Features

### Key Metrics
- Global internet usage trends
- Continental comparisons
- Country-level rankings
- 5-year growth rates
- Digital divide assessment

### Visualizations
1. Global trend line plot
2. Continental distribution boxplots
3. Top 10 countries bar chart

## Key Findings

### Global Trends
- 59.3 percentage point increase in global internet usage (2000-2023)
- Current global average: 68.3% (excluding Oceania)

### Continental Analysis
```
                    mean     median       std      min       max
Continent                                                       
Africa         18.000000  18.000000  0.000000  18.0000   18.0000
Asia           87.936784  87.936784  8.391184  44.5027  100.0000
Europe         90.591906  90.591906  4.246373  80.3896   99.3479
North America  83.155100  83.155100  0.492975  81.1832   85.1270
South America  83.657580  83.657580  5.151057  72.6943   94.1192
```

### Top Performing Countries
```
Country Name            Internet Usage
Bahrain                     100.0000
Saudi Arabia               100.0000
United Arab Emirates       100.0000
Kuwait                      99.7473
Luxembourg                  99.3479
```

### Fastest Growing Countries (5-year growth rate)
```
Country Name    Growth Rate
Pakistan         473.25%
Afghanistan      423.43%
Burundi          350.00%
India            337.90%
South Sudan      275.00%
```

## Dependencies
- pandas
- numpy
- matplotlib
- seaborn
- pycountry
- pycountry_convert

## Project Structure
```
.
├── internet_usage.ipynb     # Main analysis notebook
├── internet_usage.csv       # Original dataset
└── README.md               # Project documentation
```

## Limitations
- Exclusion of Oceania region due to data sparsity
- Potential impact on global averages and trends
- Limited insights into Pacific region internet adoption

## Future Work
- Investigate alternative methods for handling sparse regional data
- Include additional socio-economic variables
- Develop more robust imputation strategies for Oceania
- Analyze policy implications of digital divide

## License
MIT

## Author
Emmanuel Victor 
