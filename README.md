# NFL Over/Under Prediction Using Machine Learning in R

This project aims to predict NFL Over/Under betting outcomes using machine learning algorithms in R. The model utilizes historical game data, team offensive and defensive statistics, and other relevant features to estimate the total points scored in a game and compare it to the betting lines.

## Requirements

- R (>= 4.0.0) (Models were coded in R 4.3.1)
- Required R packages: `dplyr`, `tidyverse`, `randomForest`, `pROC`, `gbm`, `caret`, `knitr`, `kableExtra`
- Knowledge in various machine learning models

## Data

The project relies on historical NFL game data, including team performance, player statistics, and betting lines for Over/Under. You will need to provide the data in the following format:

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
install.packages(c("dplyr", "tidyverse", "randomForest", "pROC", "gbm", "caret", "knitr", "kableExtra"))
```
