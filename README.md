# SundayProphet NFL Game Predictor

Welcome to capstone project! The goal of this project is to predict the outcome of NFL football games in 3 major metrics:
1. Winner
2. Spread
3. Point Total (O/U line)

## Project Overview

I have 

Using NFL team data from ESPN (2004-2022), I trained a model to predict the outcome of NFL football games. The model runs three separate regressions which determines an expected point total for each team, as well as both teams combined. These outputs will be compared to determine who will score more points (the winner), the difference between these expected totals (the spread), and the sum of the point totals (the expected points scored)

**Primary audience**: Online sportsbooks like DraftKings, Caesars, FanDual and BetMGM. All these companies offer live odds to bet on the spread for NFL games.  Single plays in a game can completely change the momentum and probability of victory for one team or another, and sportsbooks need to have good algorithms that can analyze game situation quickly and effectively to give themselves an advantage over people watching the game live. People react to what they see, so the algorithm needs to be able to immediately make predictions play-by-play and possession-by-possession. My goal is to use historical data of likelihood of victory for teams in certain scenarios.

**Secondary audience**: Users that want to get ahead of the system. They could use this model to the compare their own personal spreads to those that the book has already set. This will help them find advantageous bets, as well as provide context for betting on online sportsbooks.

**Tertiary audience**: Throughout this process, I found a lot of really interesting insights that would be beneficial for NFL analytics teams. Understanding what and how metrics directly influence expected points can help teams make decisions that can lead to wins in the long-run. Who would've thought that calling for a touchback increases your liklihood to score points?

# Next Steps

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


