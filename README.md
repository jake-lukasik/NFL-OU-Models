# NFL Over/Under Prediction Using Machine Learning in R

This project aims to predict NFL Over/Under betting outcomes using machine learning algorithms in R. The model utilizes historical game data, team offensive and defensive statistics, and other relevant features to estimate the total points scored in a game and compare it to the betting lines.

This project was done by Jacob Lukasik and Michael Jenks as a final project for STAT380 - Data Science Through Statistical Reasoning and Computation. We are both B.S. Data Science majors in the Eberly College of Science at Penn State University. *The models found in this project were created to gain insight into what contributes to total scores in NFL games and to try and predict the correct outcomes for Over/Under bets and in no ways do we seek to use this with any ill intent, including but not limited to advising others how to bet, claiming that this is a 100% accurate model, etc. PLEASE BET RESPONSIBLY*

## Requirements

- R (>= 4.0.0) (Models were coded in R 4.3.1)
- Required R packages: `dplyr`, `tidyverse`, `randomForest`, `xgboost`, `pROC`, `gbm`, `caret`, `knitr`, `kableExtra`, `Matrix`
- Knowledge in various machine learning models

## Data Sources

For this project, two separate sources were used for data; the first one being [this Kaggle repository](https://www.kaggle.com/datasets/tobycrabtree/nfl-scores-and-betting-data?select=spreadspoke_scores.csv) for the betting info and game results, and the second one being [Pro Football Reference](https://www.pro-football-reference.com/) for the team offensive and defensive stats by year. As you read, you will see that all data was consolidated into one table named *'scores'* this scores table contains many different parameters, so I won't reference every single one here, but if you are interested, I have attached some links for you to see exactly what each column is:

[Scores and Lines Stats](https://www.kaggle.com/datasets/tobycrabtree/nfl-scores-and-betting-data/data) Scroll to the data section and from there you can see descriptions for each column.

[Offensive Stats](https://www.pro-football-reference.com/years/2024/#all_team_stats) Scroll to just above the table with all team offensive stats (the table is titled *Team Offense*) and click on glossary.

[Defensive Stats](https://www.pro-football-reference.com/years/2024/opp.htm) Scroll to just above the table with all team defensive stats and click on glossary.

The data sources above were used ethically and responsibly as according to [Kaggle's standard CC BY-NC-SA 4.0 License](https://creativecommons.org/licenses/by-nc-sa/4.0/) and [Sports Reference's Data Use Policy](https://www.sports-reference.com/data_use.html). All data from PFR was downloaded manually by Jacob Lukasik and no web scraping scripts or bots were used to obtain offensive and defensive team statistics.

Special thank you to Spreadspoke and Pro Football Reference for making this data so easily accessible and allowing people to use their data for projects like these.

## Data

The project relies on historical NFL game data, including team performance, player statistics, and betting lines for Over/Under. To make your own predictions, will need to provide the data in the following format (see `week12_matchups.csv` in supplementary-material folder to see how to format exactly):

### Template Data Source

| Schedule Season | Schedule Week | team_favorite_id | Betting Line Info |      Weather Info     | Over/Under Result | Home Team | Away Team | Home Team Stats | Away Team Stats |
|-----------------|---------------|------------------|-------------------|-----------------------|-------------------|-----------|-----------|-----------------|-----------------|
| 2024            | 3             | Team A           | [Betting Lines]   | [Weather Information] |  Binary [1, 0]    |  Team A   | Team B    | [Stats]         | [Stats]         |

- `Schedule Season`: Numeric - year of game
- `Schedule Week`: Numeric - week of play
- `team_favorite_id` - Factor - ID of favorited team
- `Betting Line Info` - Numeric - columns containing spread, over/under line
- `Weather Info` - Numeric - columns containing weather info (wind, temp)
- `Over/Under Result` - Binary - 1 if over hits, 0 if under (outcome column)
- `Home Team`: ID of the home team
- `Away Team`: ID of the away team
- `Home Team Stats`: Additional home team statistics (e.g., average yards per game, offensive/defensive ranks, etc.)
- `Away Team Stats`: Additional away team statistics

Note, the only information that is required to run your own predictions is schedule_season, schedule_week, team_favorite_id, spread_favorite, over_under_line, stadium_neutral,	weather_temperature, weather_wind_mph, home_id, and away_id; the offensive and defensive stats are automatically joined based off of the home and away IDs

## Installation

To install the required R packages, run:

```R
install.packages(c("dplyr", "tidyverse", "randomForest", "xgboost", "pROC", "gbm", "caret", "knitr", "kableExtra", "Matrix"))
```
## Repository Contents

All data has been saved in .csv format and uploaded to this repository. If you intend to do anything other than running the exact algorithms in the Rmd on this page, *download the data directly from sources above*.

The Rmd file and HTML that was rendered from it are available on this page, along with the PowerPoint presentation we used to present this to faculty and peers.
