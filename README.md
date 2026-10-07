# 🌍 World Happiness: A 10-Year Exploratory Analysis (2015-2024)

What truly drives human well-being across the globe: economic prosperity, social support, or personal freedom? This project explores ten years of data (2015-2024) from the World Happiness Report, published by the United Nations Sustainable Development Solutions Network (SDSN), using visual analytics to uncover which factors shape national happiness and how regions compare.

## Highlights

- 1,502 country-year records covering 2015 to 2024
- Correlation analysis of six happiness factors against the happiness score
- Regional comparison of average happiness across 10 world regions
- Top and bottom happiness scores, a country case study (United States vs. the world average), and an interactive world map (Plotly)

## Dataset

The dataset (`world_happiness_combined.csv`) combines yearly World Happiness Report data, with one row per country per year.

| Column | Description |
|--------|-------------|
| `Ranking` | Country's happiness rank in that year |
| `Country`, `Regional indicator` | Country and its world region |
| `Happiness score` | Overall happiness score (mean 5.45, range 1.72 to 7.84) |
| `GDP per capita` | Economic output indicator |
| `Social support` | Strength of social support |
| `Healthy life expectancy` | Healthy life expectancy in years |
| `Freedom to make life choices` | Perceived freedom |
| `Generosity` | Generosity indicator |
| `Perceptions of corruption` | Perceived corruption |
| `Year` | Report year |

The only missing values are 3 entries in `Regional indicator`. The file uses `;` as the separator and `,` as the decimal mark, so it is read with `pd.read_csv(..., sep=';', decimal=',')`.

## Analysis

1. **Data overview:** shape, data types, missing values, and summary statistics.
2. **Distributions:** histograms of happiness score, social support, healthy life expectancy, and freedom.
3. **Correlation analysis:** a correlation matrix and heatmap of the happiness score and its six factors.
4. **Regional analysis:** average happiness score by region, plus the highest and lowest scores in the dataset.
5. **Country case study:** the United States' happiness trend compared with the world average, and its relative factor profile.
6. **Global map:** a choropleth map of happiness scores for the latest year (2024).
7. **Export:** the cleaned data saved as `happiness_cleaned.csv` and `happiness_dataset.joblib`.

## Key Findings

**Correlation with happiness score:**

| Factor | Correlation |
|--------|-------------|
| Social support | 0.74 |
| Healthy life expectancy | 0.66 |
| GDP per capita | 0.63 |
| Freedom to make life choices | 0.59 |
| Generosity | 0.11 |
| Perceptions of corruption | 0.07 |

Social support, healthy life expectancy, and GDP per capita are the strongest correlates of happiness, while generosity and corruption perceptions show only weak relationships. These are correlations, not proof of causation.

**Average happiness score by region:**

| Region | Average score |
|--------|---------------|
| North America and ANZ | 7.15 |
| Western Europe | 6.72 |
| Latin America and Caribbean | 6.01 |
| Central and Eastern Europe | 5.74 |
| East Asia | 5.69 |
| Southeast Asia | 5.41 |
| Commonwealth of Independent States | 5.37 |
| Middle East and North Africa | 5.25 |
| South Asia | 4.40 |
| Sub-Saharan Africa | 4.32 |

**Other observations:**

- Finland holds the highest scores in the dataset (up to 7.84), with Denmark close behind. Afghanistan and Lebanon have the lowest.
- The United States' score fell from 7.12 in 2015 to 6.72 in 2024, its lowest point in the period.

## Tech Stack

- Python
- pandas, NumPy
- matplotlib, seaborn
- Plotly
- joblib
