# NFL Game Predictor

Welcome to my capstone! The goal of this project is to predict the outcome of NFL football games in 3 major metrics:
1. Winner
2. Spread
3. Point Total (O/U line)

Using NFL team data from ESPN (2004-2022), I trained a model to predict the outcome of NFL football games. The model runs two separate regressions which determines an expected point total for each team. The first will compare the Home Offense vs Away Defense and the second will compare the Away Offense vs the Home Defense. The regression will pull on a separate dataframe with team metrics from the 2023 season to output an expected point total for each combination. These outputs will be compared to determine who will score more points (the winner), the difference between these expected totals (the spread), and the sum of the point totals (the expected points scored)

All metrics compared must be on a per game basis. This is important for two main reasons:
1. Comparing team totals in-season can skew results, as teams have bye weeks and have played a different number of games.
2. The NFL moved from a 16-game season to a 17-game season in 2021, so comparing seasons before and after this switch can skew results.

**Primary audience**: Online sportsbooks like DraftKings, Caesars, FanDual and BetMGM. All these companies offer live odds to bet on the spread for NFL games.  Single plays in a game can completely change the momentum and probability of victory for one team or another, and sportsbooks need to have good algorithms that can analyze game situation quickly and effectively to give themselves an advantage over people watching the game live. People react to what they see, so the algorithm needs to be able to immediately make predictions play-by-play and possession-by-possession. My goal is to use historical data of likelihood of victory for teams in certain scenarios.

**Secondary audience**: users that want to get ahead of the system. They could use the program to the compare their own personal spreads to those that the book has already set and bet when they see a significant difference between the two. 


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


