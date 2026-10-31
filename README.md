# Premier League Player Performance Analysis (2025/26)

## Project Overview

The aim was to look into how expected goals (xG), expected assists (xA), and passing accuracy relate to player performance in the 2025/26 Premier League.

The project combines an existing Kaggle dataset with  player statistics collected through web scraping.

## Research Question

**How do expected goals (xG), expected assists (xA), and passing accuracy relate to player performance in the 2025/26 Premier League?**

## Data Sources

### 1. Kaggle Dataset

**Football Players Stats 2025–2026**

[View Kaggle Dataset](https://www.kaggle.com/datasets/hubertsidorowicz/football-players-stats-2025-2026)

- **2,839 player records** across five European leagues
- 102 columns
- Includes goals, assists, minutes played, shooting and defensive statistics
- 551 Premier League player records

### 2. Web-Scraped Dataset

**Statto — Premier League Player Statistics 2025/26**

[View Statto Dataset](https://statto.pythonanywhere.com/stats/players?sort=player_name&dir=asc&limit=all)

- **550 player records**
- 14 columns
- Includes expected goals (xG), expected assists (xA), and pass completion percentage
- Website approved by the module lecturer

## Methodology

1. Imported and explored the original Kaggle dataset using pandas.
2. Collected Premier League player statistics from Statto using Requests, BeautifulSoup, and pandas.
3. Cleaned numerical columns and standardised player and team names.
4. Merged both datasets using player and team names.
5. Investigated missing values and created a complete analysis dataset.
6. Used Seaborn and Matplotlib to visualise relationships between player statistics.
7. Compared cumulative statistics with per-90-minute statistics to investigate the influence of playing time.

## Data Integration Results

| Metric | Result |
|---|---:|
| Original Kaggle records | 2,839 |
| Premier League Kaggle records | 551 |
| Statto records | 550 |
| Successfully matched players | 530 |
| Complete analysis records | 511 |
| Complete records as percentage of original Kaggle data | 18.00% |


## Key Findings

The analysis was done using **386 Premier League players** who played at least 450 minutes.

| Relationship | Pearson Correlation | Interpretation |
|---|---:|---|
| xG vs Actual Goals | +0.929 | Very strong positive |
| xA vs Actual Assists | +0.842 | Strong positive |
| Passing Accuracy vs Goal Contributions | -0.215 | Weak negative |
| xG per 90 vs Goals per 90 | +0.862 | Strong positive |
| xA per 90 vs Assists per 90 | +0.721 | Strong positive |

### Expected Goals and Actual Goals

A strong positive correlation (**0.929**) was found between expected goals and  goals scored.

This suggests that players who accumulate higher xG generally score more goals.

### Expected Assists and Actual Assists

A strong positive correlation (**0.842**) was found between expected assists and actual assists.

Players who generate more expected assists generally record more assists.

### Passing Accuracy and Goal Contributions

Passing accuracy showed a weak negative correlation (**-0.215**) with total goal contributions.

Further analysis suggested that player position may help explain this relationship.

| Position | Average Passing Accuracy | Average Goal Contributions |
|---|---:|---:|
| Forward | 68.23% | 7.91 |
| Midfielder | 78.81% | 5.23 |
| Defender | 82.91% | 1.99 |
| Goalkeeper | 68.05% | 0.15 |

Defenders had the highest average passing accuracy but  few goal contributions, while forwards had the highest average goal contributions.

### Effect of Playing Time

After converting cumulative statistics to per-90-minute rates:

- The xG–goals correlation decreased from **0.929 to 0.862**.
- The xA–assists correlation decreased from **0.842 to 0.721**.

Both relationships remained strongly positive, showing that playing time contributes to the original correlations but does not fully explain them.

## Technologies Used

- **Python** — Programming language
- **Google Colab** — Development environment
- **pandas** — Data manipulation and merging
- **NumPy** — Numerical operations
- **Requests** — Retrieving website content
- **BeautifulSoup** — HTML parsing and web scraping
- **Seaborn** — Statistical visualisations
- **Matplotlib** — Graph formatting
- **GitHub** — Version control and project documentation

## Repository Contents

| File | Description |
|---|---|
| `Premier_League_Data_Acquisition.ipynb` | Complete Python notebook containing data acquisition, cleaning, merging, visualisations and conclusions |
| `players_data-2025_2026.csv` | Original Kaggle dataset |
| `premier_league_merged_2025_26.csv` | Cleaned and merged analysis dataset |
| `README.md` | Project overview, methodology and findings |

## Limitations

- Some players could not be matched between the datasets.
- Some scraped statistics were missing.
- Players with fewer than 450 minutes were excluded from the main visualisations.
- Player positions were simplified into broad categories.
- Differences in team quality and tactical roles may influence performance.
- Correlation does not establish causation.

## Conclusion

The project found that **expected goals and expected assists are strongly associated with actual attacking performance**, even after accounting for playing time.

Passing accuracy showed a much weaker relationship with attacking output, highlighting the importance of considering player positions and responsibilities.

Overall the project demonstrates how combining a Kaggle dataset with complementary web-scraped statistics can provide additional insights into football player performance.


# AI Usage Report

## Project Information

**Project:** Premier League Player Performance Analysis (2025/26)  
**Module:** Data Acquisition  
**Institution:** TU Dublin  
**AI Tool Used:** ChatGPT (OpenAI)

## 1. Overview of AI Usage

ChatGPT was used throughout the project as an assistant.

AI assistance included generating example code, explaining programming concepts, troubleshooting errors and helping structure the analysis.

The project was developed and executed in Google Colab, with the resulting files maintained in a GitHub repository.

## 2. Examples of AI-Assisted Tasks

### Example 1: Web Scraping

AI helped with code to retrieve player statistics from the Statto website.

The code helped Requests to obtain HTML content, BeautifulSoup to locate the relevant table and pandas to convert the table into a DataFrame.


### Example 2: Dataset Integration

AI helped with standardising player names and team names across the Kaggle and Statto datasets.

The datasets were merged using player and team identifiers, and the results were checked to identify successful and unsuccessful matches.

### Example 3: Data Visualisation

AI provided guidance for creating plots comparing expected goals with actual goals, expected assists with actual assists, and passing accuracy with goal contributions.

Additional analysis compared cumulative statistics with per-90-minute statistics.

## 4. Verification and Human Review

AI suggestions were implemented and tested in Google Colab.

Dataset sizes, matching results, missing values, correlation coefficients and visualisations were inspected during development.

Errors and unexpected results were investigated, and changes were made where necessary.

## 5. Limitations of AI Assistance

AI code and explanations were not treated as automatically correct.

Limitations included:

- Code requiring changes to match the actual dataset columns.
- Differences in player and team names between sources.
- Missing values affecting the final analysis.
- Statistical relationships requiring interpretation rather than assuming causation.
- The possibility of changes to the external website affecting reproducibility.

## 6. Reflection

Using ChatGPT helped support the development of the project involving multiple data sources and several stages of processing.

It was useful for understanding how to scrape HTML tables, clean and merge datasets, troubleshoot Python code and present findings clearly.

The project also highlighted the importance of checking AI-generated code against actual data, validating merge results and interpreting statistical outputs carefully.
