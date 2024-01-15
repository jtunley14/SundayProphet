# SundayProphetAI: NFL Score Predictor

Welcome to my capstone project! The goal of this project is to predict the outcome of NFL football games in 3 major metrics:
1. Winner
2. Spread
3. Point Total (O/U line)

I have been interested in sports and sports analytics for as long as I can remember. I grew up playing football, lacrosse and wrestling, and have been watching the New York Jets be bad at football since I was five years old. As a kid, In elementary school, I  would wake up at 7am to watch Sportscenter before school started, and I had mastered the art of fantasy football before I learned basic algebra. Despite my life-long love, I never imagined it was something I could pursue as a career.

Fast forward to last year, and I had just graduated from the University of Florida with a bachelors in Business Administration. While I loved business and appreciated the skills I learned during my time as an undergrad, I knew that there was more I could do to hone my technical skills and bring value to a company. That is where my coding journey began. 

In September, I enrolled at BrainStation NYC’s Data Science Bootcamp, and it was one of the best decisions I ever made. There, I was able to apply to my background in business and statistics and gain the necessary hard skills to pursue data science as a career. For my capstone project, I decided to combine the skills I was learning with a project that I was passionate and knowledgeable about. 

While my term at BrainStation has come to an end and I have submitted my final project, this is not the end, only the beginning! When I began this project, I was new to the world of Data Science, and I was still learning what was and was not possible. After five months, I have many new ideas for future iterations of this project that will lead to significant improvements. Make sure to follow along on this page or on my Linkedin: https://www.linkedin.com/in/jmtunley/

## Project Overview
Using NFL team data from ESPN (2004-2022), I trained a model to predict the outcome of NFL football games. The model runs three separate regressions which determines an expected point total for each team, as well as both teams combined. These outputs will be compared to determine who will score more points (the winner), the difference between these expected totals (the spread), and the sum of the point totals (the expected total points scored).

**Primary audience**: Online sportsbooks like DraftKings, Caesars, FanDual and BetMGM. All these companies offer live odds to bet on the spread of NFL football games.  Single plays in a game can completely change the momentum and probability of victory for one team or the other, and sportsbooks need to have good algorithms that can instantly and effectively analyze game situations to give them an advantage over people watching the game live. People react to what they see, so the algorithm needs to be able to immediately make predictions play-by-play and possession-by-possession. My goal is to use historical data of likelihood of victory for teams in certain scenarios.

**Secondary audience**: Users that want to beat the system. They could use this model to compare their own personal spreads to those that the book has already set. This will help users find advantageous bets, as well as provide context for betting on official lines.
**Tertiary audience**: Throughout this process, I found a lot of really interesting insights that would be beneficial for NFL analytics teams. Understanding what and how metrics directly influence expected points can help teams make decisions that can lead to wins in the long-run. Who would've thought that calling for a touchback increases your likelihood of scoring points?
- For some of these interesting insights, check out my Demo Day Powerpoint slides!

## Datasets
Getting access to all the data I needed was one of the most difficult challenges of this project. While I wanted to train on as many games as possible to ensure the model was as accurate as possible, a lot of the data collected in games today are more advanced than they were 20 years ago. Not only do I need all of the same features, but also in the same format, so that the model can be run for games this year. While official sportsbooks have very advanced data collection systems, they keep this data private (for obvious reasons). This severely limited my options. While the easy option (and the one I will be taking in future versions of this project) would have been to use an API, I wanted to challenge myself by scraping directly from ESPN and cleaning it. This process took two entire notebooks, and are titled Historical Data-Scraper and In-Season Data Scraper.

The data scraped for this project is publicly-available data on ESPN. It can be accessed with the following link: https://www.espn.com/nfl/team/stats/_/type/team/name/nyj

## Features and Methodology
All of the features used in the first iteration of this model can be viewed through the link above, but I will provide a brief summary:

Offensive metrics focused on total offensive performance, rushing metrics, passing metrics, turnover statistics and conversion rate on 3rd down and the redzone. I also included some important miscellaneous statistics such as time of possession, turnover ratio, penalties and field goals per game. While defensive statistics were not displayed on the same website in the same way, ESPN does show how opposing teams performed in those same metrics against that team. I was able to reverse-engineer this to basically give the defense statistics for that particular team. After scraping, I was able to manipulate all of this information into a table in which a team in a particular season is represented by a single row, with columns containing all of these statistics. 

The next step was importing the results of historical games into a dataset that compared teams in each of these statistics. This process can be shown in the Game_Results_data, as well as the beginning of the TotalScorePredictor Notebook. Using a combinations function, I created matchups of every possible set of teams with each of their statistics, then imported the results of those games where a game was actually played. Then I could remove all matchups where the game wasn't played, do my train / test split, and start honing my model!

While I won't go through every feature one-by-one, here is a list of all of them below

'SeasonID', 'Tot_TDs_PG', '1st_Downs_PG', 'Rush_1st_Downs_PG', 'Pass_1st_Downs_PG', 'OFF_1st_by_pen_PG', '3rd_Conv_Rate', '4th_Conv_Rate', 'Pass_Comp_Rate', 'Pass_Yds_PG', 'Pass_Yds_Per_Attempt', 'Pass_Tds_PG', 'Off_Int_PG', 'OFF_Sacks-Yards Lost', 'Rush_Att_PG', 'Yds_Per_Rush', 'Rush_Yds_PG', 'Rush_Tds_PG', 'Off_Plays_PG', 'Tot_Yds_PG', 'OFF_Kickoffs: Total', 'Avg_K_Return_Yds', 'OFF_Punt: Total', 'Avg_P_Return_Yds', 'OFF_INT: Total', 'Avg_I_Return_Yds', 'Yds_Per_Punt', 'OFF_Punt: Total Yards', 'OFF_FG: Good-Attempts', 'Touchback_Rate', 'Total_Penalties-Yds', 'Avg_Pen_Yds_PG', 'Avg_TOP', 'OFF_Fumbles-Lost', 'Games', 'Year', 'DEF_PPG_Against', 'DEF_Tot_Tds_PG_Against', 'DEF_1st_Downs_PG_Against', 

## Next Steps

This model is far from perfect, and I already have so many ideas for how I can improve it moving forward! 
1. Because the model does not scrape from individual games and instead season-long statistics, it is difficult to determine the role that an injury or weather would play on expected points. In future versions of this project, I plan to include these types of insights so the model can get even more context before making a prediction.
2. While using a neural network did allow me to get the most accurate predictions with the lowest RMSE, I am continuing to test with different options such as XGBoost. This can hopefully help me hone my predictions, but will also allow me to understand which features are most important in a more comprehensive manner.
3. All of the features are currently sums of season-long statistics. I want to add individual game data from an API so that I can see how individual players affect matchups and account for injuries. This would also allow me to account for team form, so the model can recognize whether a team is on a winning streak or losing streak.

If you are interested in this project and would like see future iterations and other stuff I'm working on, please feel free to follow me on LinkedIn: https://www.linkedin.com/in/jmtunley/

Additionally, I am working on a collaborative project called Whistle Labs. We are a group of data scientists and sports enthusiasts hoping to bring advanced analytics to NFL and MLS fans. If you are interested in following along, follow us on our LinkedIn! We just started, but have some great content planned soon! https://www.linkedin.com/company/whistlelabs/

HUGE Shoutout to everyone at BrainStation and BrainStation NYC for teaching me the skills that have allowed me to turn my passion into a career! I could not have done this without their mentoring.
