# MLB Home Run Analysis (2024)

What makes an MLB hitter hit home runs? This project analyzes 2024 batter data
from Baseball Savant to find the performance metrics most associated with home
runs, group hitters into tiers, and classify them with machine learning.

## Key Findings
- **Barrels are the strongest single predictor.** A simple linear regression on
  barrels alone explained 91.6% of the variance in home runs (r = 0.957).
- **Multiple linear regression** on the 10 most correlated stats raised R² to 0.945.
- **K-Means clustering** (on PCA-reduced data) separated hitters into four tiers,
  from below average to elite.
- **Random Forest classification** predicted a hitter's tier with 88% accuracy;
  xISO, hits, and plate appearances were the most important features.
- **Switch hitters** hit more home runs per barrel than left- or right-handed hitters.
- **Age:** younger (≤27) and older (28+) hitters showed similar home run distributions.

## Methods
Simple & Multiple Linear Regression · Principal Component Analysis (PCA) · Multidimensional Scaling (MDS) · K-Means · Density Based Spatial Clustering of Applications with Noise (DBSCAN) · Random Forest

## Data
- Source: [Baseball Savant Custom Leaderboard](https://baseballsavant.mlb.com/leaderboard/custom), 2024 season
- Switch hitters were identified by matching players across the left- and right-handed splits
- Excluded players averaging fewer than 2 plate appearances per game who also
  played fewer than 81 games, so small samples don't distort the results

## Project Structure
| File | Description |
|---|---|
| `01_data_cleaning.ipynb` | Loads raw data, determines handedness, filters low-playing-time players |
| `02_home_run_analysis.ipynb` | Regression, clustering, dimensionality reduction, and classification |
| `data/` | Raw and cleaned CSV files |

## How to Run
1. `pip install -r requirements.txt`
2. Run `01_data_cleaning.ipynb` to generate the cleaned dataset
3. Run `02_home_run_analysis.ipynb`