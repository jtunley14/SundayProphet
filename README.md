# NFL Game Predictor

Welcome to my capstone project! The goal of this project is to predict the outcome of NFL football games in 3 major metrics:
1. Winner
2. Spread
3. Point Total (O/U line)

Using NFL team data from ESPN (2004-2022), I trained a model to predict the outcome of NFL football games. The model runs three separate regressions which determines an expected point total for each team, as well as both teams combined. These outputs will be compared to determine who will score more points (the winner), the difference between these expected totals (the spread), and the sum of the point totals (the expected points scored)

**Primary audience**: Online sportsbooks like DraftKings, Caesars, FanDual and BetMGM. All these companies offer live odds to bet on the spread for NFL games.  Single plays in a game can completely change the momentum and probability of victory for one team or another, and sportsbooks need to have good algorithms that can analyze game situation quickly and effectively to give themselves an advantage over people watching the game live. People react to what they see, so the algorithm needs to be able to immediately make predictions play-by-play and possession-by-possession. My goal is to use historical data of likelihood of victory for teams in certain scenarios.

**Secondary audience**: Users that want to get ahead of the system. They could use this model to the compare their own personal spreads to those that the book has already set. This will help them find advantageous bets.

**Tertiary audience**: Throughout this process, I found a lot of really interesting insights that would be beneficial for NFL analytics teams. Understanding what goes into points can help teams make decisions that can lead to wins in the long-run. Who would've thought that calling for a touchback increases your liklihood to score points?

# Next Steps

This model is far from perfect, and I already have so many ideas for how I can improve it moving forward! I want to incorporate weather, player statistics, and player injuries so that the model can understand how these factors influence and game and the spread. Furthermore, I am hoping to build a streamlit app so that anyone can use this product with ease. If you're interested in following along and viewing my progress, definitely give this project a follow!


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


