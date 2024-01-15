# SundayProphetAI: NFL Score Predictor

Welcome to my capstone project! The goal of this project is to predict the outcome of NFL football games in 3 major metrics:
1. Winner
2. Spread
3. Point Total (O/U line)

## Background and Motivation

Sports have been my passion since the moment I was born. 

I would wake up before school in elementary school to watch Sportscenter
Summers and falls consisted of traveling up and down the east coast for lacrosse tournaments
Blamed my dad for ruining our fantasy football team when I was 12 years old
Jets fan since birth

While sports analytics was something that I've always been interested in, it was never something I considered as a career, as I did not have the skills to turn into a reality. Chose this because I am passionate about it and want to combine the skills I am learning with a background that I am already very knowledgable in.
With my background in business, I am able to easily understand how to take interesting insights and turn it into a money-making opportunity?

While my term at BrainStation has come to an end and I have turned in my final submission, this is not the end for this project! When I began this project, I was new to the world of Data Science, and still learning what was and was not possible. After five months, I have so many new ideas for different approaches I can take in future iterations that will lead to improvements. I go over these at the end of this ReadMe, but feel free to follow along by following this page or my LinkedIn: https://www.linkedin.com/in/jmtunley/

## Project Overview

Using NFL team data from ESPN (2004-2022), I trained a model to predict the outcome of NFL football games. The model runs three separate regressions which determines an expected point total for each team, as well as both teams combined. These outputs will be compared to determine who will score more points (the winner), the difference between these expected totals (the spread), and the sum of the point totals (the expected points scored)

**Primary audience**: Online sportsbooks like DraftKings, Caesars, FanDual and BetMGM. All these companies offer live odds to bet on the spread of NFL football games.  Single plays in a game can completely change the momentum and probability of victory for one team or another, and sportsbooks need to have good algorithms that can analyze game situation quickly and effectively to give themselves an advantage over people watching the game live. People react to what they see, so the algorithm needs to be able to immediately make predictions play-by-play and possession-by-possession. My goal is to use historical data of likelihood of victory for teams in certain scenarios.

**Secondary audience**: Users that want to get ahead of the system. They could use this model to the compare their own personal spreads to those that the book has already set. This will help them find advantageous bets, as well as provide context for betting on official lines.

**Tertiary audience**: Throughout this process, I found a lot of really interesting insights that would be beneficial for NFL analytics teams. Understanding what and how metrics directly influence expected points can help teams make decisions that can lead to wins in the long-run. Who would've thought that calling for a touchback increases your liklihood to score points?
- For some of these interesting insights, check out my Demo Day Powerpoint slides!

## Datasets
One of the most difficult challenges in this project was getting access to all of the data I needed. While I wanted to train on as many games as possible to ensure the model was as accurate as possible, a lot of the data collected in games today are more advanced than they were 20 years ago. Not only do I need all of the same features, but also in the same format, so that the model can be run for games this year. While official sportsbooks have very advanced data collection systems, they keep this data private (for obvious reasons). This severely limited my options. While the easy option (and the one I will be taking in future versions of this project) would have been to use an API, I wanted to challenge myself by scraping directly from ESPN and cleaning it. This process took two entire notebooks, and are titled Historical Data-Scraper and In-Season Data Scraper.

The data scraped for this project is publicly-available data on ESPN. It can be accesses with the link below:
https://www.espn.com/nfl/team/stats/_/type/team/name/nyj

## Features and Methodology
All of the features used in the first iteration of this model can be viewed through the link above, but I will provide a brief summary:

Offensive metrics focused on total offensive performance, rushing metrics, passing metrics, turnover statistics and converstion rate on 3rd down and the redzone. I also included some important miscellaneous statistics such as time of possession, turnover ratio, penalties and field goals per game. While defensive statistics were not displayed on the same website in the same way, ESPN does show how opposing teams performed in those same metrics against that team. I was able to reverse-engineer this to basically give the defense statitics for that particular team. After scraping, I was able to manipulate all of this information into a table, in which a team in a particular season is represented by a single row, with columns containing all of these statitics. 

The next step was importing the results of historical games into a dataset that compared teams in each of these statitics. This process can be shown in the Game_Results_data, as well as the beginning of the TotalScorePredictor Notebook. Using a combinations function, I created matchups of every possible the set of teams with each of their statistics, then imported the results of those games where a game was actually played. Then I could remove all matchups where the game wasn't played, do my train / test split, and start honing my model!

While I wont go through every feature one-by-one, here is a list of all of them below

'SeasonID', 'Tot_TDs_PG', '1st_Downs_PG', 'Rush_1st_Downs_PG', 'Pass_1st_Downs_PG', 'OFF_1st_by_pen_PG', '3rd_Conv_Rate', '4th_Conv_Rate', 'Pass_Comp_Rate', 'Pass_Yds_PG', 'Pass_Yds_Per_Attempt', 'Pass_Tds_PG', 'Off_Int_PG', 'OFF_Sacks-Yards Lost', 'Rush_Att_PG', 'Yds_Per_Rush', 'Rush_Yds_PG', 'Rush_Tds_PG', 'Off_Plays_PG', 'Tot_Yds_PG', 'OFF_Kickoffs: Total', 'Avg_K_Return_Yds', 'OFF_Punt: Total', 'Avg_P_Return_Yds', 'OFF_INT: Total', 'Avg_I_Return_Yds', 'Yds_Per_Punt', 'OFF_Punt: Total Yards', 'OFF_FG: Good-Attempts', 'Touchback_Rate', 'Total_Penalties-Yds', 'Avg_Pen_Yds_PG', 'Avg_TOP', 'OFF_Fumbles-Lost', 'Games', 'Year', 'DEF_PPG_Against', 'DEF_Tot_Tds_PG_Against', 'DEF_1st_Downs_PG_Against', 'DEF_Rush_1st_Downs_PG_Against', 'DEF_Pass_1st_Downs_PG_Against', 'DEF_1st_by_pen_PG', 'DEF_3rd_Conv_Rate', 'DEF_4th_Conv_Rate', 'DEF_Comp-Att', 'DEF_Pass_Yds_Per_Attempt', 'DEF_Pass_Yds_PG', 'DEF_Pass_Tds_PG', 'DEF_Int_PG', 'DEF_Sacks-Yards Lost', 'DEF_Rush_Att_PG', 'DEF_Yds_Per_Rush', 'DEF_Rush_Yds_PG', 'DEF_Rush_Tds_PG', 'DEF_Tot_Plays_PG', 'DEF_YPG_Against', 'DEF_Kickoffs: Total', 'DEF_Avg_K_Return_Yds', 'DEF_Punt: Total', 'DEF_Avg_P_Return_Yds', 'DEF_INT: Total', 'DEF_Avg_I_Return_Yds', 'DEF_Yds_Per_Punt_Against', 'DEF_Punt: Total Yards', 'DEF_FG: Good-Attempts', 'DEF_Touchback_Rate', 'DEF_Total_Penalties-Yds', 'DEF_Avg_Pen_Yds_PG', 'DEF_Avg_TOP', 'DEF_Fumbles-Lost'

## Next Steps

This model is far from perfect, and I already have so many ideas for how I can improve it moving forward! 
1. Because the model does not scrape from individual games and instead season-long statistics, it is difficult to determine the role that an injury or weather would play on expected points. In future versions of this project, I plan to include these types of insights so the model can get even more context before making a prediction.
2. While using a neural network did allow me to get the most accurate predictions with the lowest RMSE, I am continuing to test with different options such as XGBoost. This can hopefully help me hone my predictions, but will also allow me to understand which features are most important in a more comprehensive manner.

If you are interested in this project and would like see future iterations and other stuff I'm working on, please feel free to follow my on LinkedIn: https://www.linkedin.com/in/jmtunley/
You can also follow our blog, Whistle Labs, at https://www.linkedin.com/company/whistlelabs/. We just started creating content, but will be providing advanced statistics on NFL Football and MLS Soccer.

HUGE Shoutout to everyone at BrainStation and BrainStation NYC for teaching me the skills that allowed me to make this passion into a career! I could not have done this without their mentoring.

# Features

'SeasonID', 'PPG', 'Tot_TDs_PG', '1st_Downs_PG', 'Rush_1st_Downs_PG',
       'Pass_1st_Downs_PG', 'OFF_1st_by_pen_PG', '3rd_Conv_Rate',
       '4th_Conv_Rate', 'Pass_Comp_Rate', 'Pass_Yds_PG',
       'Pass_Yds_Per_Attempt', 'Pass_Tds_PG', 'Off_Int_PG',
       'OFF_Sacks-Yards Lost', 'Rush_Att_PG', 'Yds_Per_Rush', 'Rush_Yds_PG',
       'Rush_Tds_PG', 'Off_Plays_PG', 'Tot_Yds_PG', 'OFF_Kickoffs: Total',
       'Avg_K_Return_Yds', 'OFF_Punt: Total', 'Avg_P_Return_Yds',
       'OFF_INT: Total', 'Avg_I_Return_Yds', 'Yds_Per_Punt',
       'OFF_Punt: Total Yards', 'OFF_FG: Good-Attempts', 'Touchback_Rate',
       'Total_Penalties-Yds', 'Avg_Pen_Yds_PG', 'Avg_TOP', 'OFF_Fumbles-Lost',
       'Games', 'Year', 'DEF_PPG_Against', 'DEF_Tot_Tds_PG_Against',
       'DEF_1st_Downs_PG_Against', 'DEF_Rush_1st_Downs_PG_Against',
       'DEF_Pass_1st_Downs_PG_Against', 'DEF_1st_by_pen_PG',
       'DEF_3rd_Conv_Rate', 'DEF_4th_Conv_Rate', 'DEF_Comp-Att',
       'DEF_Pass_Yds_Per_Attempt', 'DEF_Pass_Yds_PG', 'DEF_Pass_Tds_PG',
       'DEF_Int_PG', 'DEF_Sacks-Yards Lost', 'DEF_Rush_Att_PG',
       'DEF_Yds_Per_Rush', 'DEF_Rush_Yds_PG', 'DEF_Rush_Tds_PG',
       'DEF_Tot_Plays_PG', 'DEF_YPG_Against', 'DEF_Kickoffs: Total',
       'DEF_Avg_K_Return_Yds', 'DEF_Punt: Total', 'DEF_Avg_P_Return_Yds',
       'DEF_INT: Total', 'DEF_Avg_I_Return_Yds', 'DEF_Yds_Per_Punt_Against',
       'DEF_Punt: Total Yards', 'DEF_FG: Good-Attempts', 'DEF_Touchback_Rate',
       'DEF_Total_Penalties-Yds', 'DEF_Avg_Pen_Yds_PG', 'DEF_Avg_TOP',
       'DEF_Fumbles-Lost'


