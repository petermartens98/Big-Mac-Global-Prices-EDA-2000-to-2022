# Big Mac Price Analysis: Global Economic Indicator (2000-2022)

An exploratory data analysis and visualization project examining Big Mac prices across 74 countries over 22 years. This project uses the Big Mac Index as an informal measure of purchasing power parity and currency valuation.

## 📊 Project Overview

This Jupyter notebook analyzes McDonald's Big Mac pricing data to uncover global economic trends, regional price variations, and temporal patterns in consumer purchasing power. The analysis provides insights into inflation, currency strength, and cost of living differences across nations.

**Data Source:** [Kaggle - Big Mac Price Dataset](https://www.kaggle.com/datasets/vittoriogiatti/bigmacprice)

**Dataset Statistics:**
- 1,946 records across 74 countries
- 22-year timespan (April 2000 - July 2022)
- 37 unique observation dates
- 0 missing values (complete dataset)

## 🛠️ Technologies & Libraries

**Data Processing:**
- Pandas - Data manipulation and aggregation
- NumPy - Numerical computations

**Visualization:**
- Matplotlib - Static plots and charts
- Seaborn - Statistical visualizations
- Plotly Express - Interactive visualizations

**Analysis:**
- pandas-profiling - Automated data profiling reports

## 📈 Analysis Features

### Data Exploration & Cleaning
- ✅ Validated data integrity (220 duplicates identified)
- ✅ Converted date strings to datetime objects
- ✅ Created time-series index for temporal analysis
- ✅ Engineered year feature for aggregations
- ✅ Verified data completeness (zero null values)

### Statistical Analysis
- Country-level price averages and rankings
- Global temporal trends with yearly aggregations
- Regional comparisons (Eurozone focus)
- Price distribution analysis with quartiles
- Outlier detection via box plots

### Visualizations

#### 1. World Average Price Evolution
Time-series visualization revealing steady price inflation from $2.32 (2000) to $4.00 (2022) - a 72% increase over 22 years.

<img width="635" height="390" alt="image" src="https://github.com/user-attachments/assets/4de981e1-5a44-43bc-97ec-7ffb4079887d" />


#### 2. Annual Price Distribution
Box plots illustrating price variance, median values, and outliers across each year, highlighting growing price dispersion over time.

<img width="796" height="590" alt="image" src="https://github.com/user-attachments/assets/bda4b73b-3f08-4593-ae67-6cae60f982bc" />
<img width="770" height="565" alt="image" src="https://github.com/user-attachments/assets/caa3ba0d-8309-4b41-9d0c-88d52589f7dd" />


#### 3. 2022 Global Price Ranking
Comprehensive horizontal bar chart comparing prices across 70 countries in July 2022, ranging from Kuwait ($1.30) to New Zealand ($7.10).

<img width="345" height="873" alt="image" src="https://github.com/user-attachments/assets/353b9357-a63d-4cd0-82e8-8ade569b2f82" />


#### 4. 2000 Baseline Comparison
Historical snapshot of Big Mac prices across 28 countries at the project's starting point, providing a baseline for inflation analysis.

<img width="313" height="867" alt="image" src="https://github.com/user-attachments/assets/bee5a40e-5607-4c5d-9d93-c71551d0f7df" />


#### 5. Eurozone Deep Dive
Dual analysis (full history and post-2010) examining price harmonization and divergence across 19 Eurozone countries sharing a common currency.

<img width="829" height="535" alt="image" src="https://github.com/user-attachments/assets/b478e91d-efa8-4820-8981-a8df286fc123" />
<img width="816" height="521" alt="image" src="https://github.com/user-attachments/assets/bdbe9f77-fb42-4eb7-bf35-4e01ba19de32" />


#### 6. United States Price History
Detailed tracking of US Big Mac prices showing 130% growth from $2.24 to $5.15, with clear visualization of inflationary periods.

<img width="708" height="402" alt="image" src="https://github.com/user-attachments/assets/0cc7f9cd-2400-4084-aeb1-170a8076bccf" />


#### 7. Three-Way Comparative Analysis
Side-by-side comparison of USA, Eurozone, and global average prices revealing relative purchasing power and market positioning.

<img width="809" height="503" alt="image" src="https://github.com/user-attachments/assets/e5b88829-ac26-44bc-9400-cfc155b95dcb" />

#### 8. Automated Data Profiling Report
Comprehensive pandas-profiling report with correlations, distributions, and data quality metrics.

## 🔍 Key Findings

### Price Rankings (2022)
**Most Affordable:**
1. Kuwait - $1.30
2. Oman - $1.42
3. Bahrain - $1.60
4. Venezuela - $2.00
5. Jordan - $2.30

**Most Expensive:**
1. New Zealand - $7.10
2. Norway - $6.89
3. Canada - $6.77
4. Australia - $6.70
5. Switzerland - $6.50

### Economic Insights
- **Global Inflation:** Average Big Mac price increased 72% over 22 years
- **US Market:** Above global average, showing 130% growth ($2.24 → $5.15)
- **Currency Strength:** Wide variation ($1.30 to $7.10) reflects purchasing power parity
- **Eurozone Variation:** Despite shared currency, prices range from €3.20 to €5.50
- **Emerging Markets:** Generally lower prices, indicating currency undervaluation or lower purchasing power

### Temporal Patterns
- Steady upward trend in global average prices
- Accelerated growth periods: 2007-2008, 2021-2022
- Price convergence in developed markets
- Increased dispersion in emerging markets

## 🚀 Getting Started

### Prerequisites

Ensure you have Python 3.7+ and Jupyter installed. Install required packages:

```bash
pip install pandas numpy matplotlib seaborn plotly cufflinks pandas-profiling chart-studio jupyter
```

### Installation & Setup

1. **Clone or download the repository**
   ```bash
   git clone <repository-url>
   cd big-mac-analysis
   ```

2. **Download the dataset**
   - Visit [Kaggle Dataset](https://www.kaggle.com/datasets/vittoriogiatti/bigmacprice)
   - Download `BigmacPrice.csv`
   - Place in project root directory

3. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook Big_Mac_Analysis.ipynb
   ```

4. **Run the analysis**
   - Execute cells sequentially
   - Interactive plots will render in-browser
   - Export visualizations as needed

## 📊 Dataset Schema

| Column | Type | Description |
|--------|------|-------------|
| `date` | datetime64 | Observation date (converted from string) |
| `currency_code` | object | ISO 4217 currency code (e.g., USD, EUR) |
| `name` | object | Country or region name |
| `local_price` | float64 | Big Mac price in local currency |
| `dollar_ex` | int64 | Exchange rate to convert to USD |
| `dollar_price` | float64 | Standardized price in US dollars |
| `year` | int64 | Extracted year for aggregation (engineered feature) |

## 💡 Usage Examples

### Filter by Country
```python
us_data = df[df['name'] == 'United States']
```

### Calculate Regional Averages
```python
eurozone_avg = df[df['name'].isin(eurozone_countries)].groupby('year')['dollar_price'].mean()
```

### Create Custom Visualizations
```python
fig = px.line(df, x='date', y='dollar_price', color='name')
fig.show()
```

## 🔬 Future Enhancements

- [ ] Add inflation-adjusted price analysis
- [ ] Incorporate GDP per capita comparisons
- [ ] Develop predictive pricing models
- [ ] Include additional economic indicators (CPI, PPP)
- [ ] Create interactive dashboard with Dash/Streamlit
- [ ] Expand to include other Big Mac Index periods
- [ ] Add geographic heat map visualizations

## 📸 Adding Screenshots

To populate the README with your visualizations:

1. Create a `screenshots/` directory in your project folder
2. Export plots from your notebook (right-click → Save Image)
3. Save with these exact filenames:
   - `global_trends.png` - All countries interactive plot
   - `world_average.png` - Global mean price over time
   - `price_distribution.png` - Box plots by year
   - `2022_comparison.png` - Horizontal bar chart for 2022
   - `2000_baseline.png` - Horizontal bar chart for 2000
   - `eurozone_analysis.png` - Eurozone comparative plot
   - `usa_prices.png` - US price history line chart
   - `comparative_analysis.png` - USA vs Eurozone vs World

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/NewAnalysis`)
3. Commit your changes (`git commit -m 'Add new analysis'`)
4. Push to the branch (`git push origin feature/NewAnalysis`)
5. Open a Pull Request

**Ideas for Contributions:**
- Additional statistical tests
- Machine learning price predictions
- Alternative visualization approaches
- Data quality improvements
- Documentation enhancements

## 📄 License

This project is available for educational and research purposes. Please cite the original data source (The Economist's Big Mac Index) when using this analysis.

## 🙏 Acknowledgments

- **The Economist** - Original creators of the Big Mac Index
- **Vittorio Giatti** - Dataset compilation and Kaggle publication
- **McDonald's Corporation** - Providing standardized global product pricing data

## 📧 Contact & Support

For questions, suggestions, or issues, please open an issue in the repository or contact the creator.

---

**⭐ Star this repository if you found it helpful!**
