# NFL Game Predictor

Welcome to my capstone! The goal of this project is to predict the outcome of NFL football games in 3 major metrics:
1. Winner
2. Spread
3. Point Total (O/U line)

Using historical NFL data dating back to 2004, my goal is to train my model to determine how particular offensive and defensive metrics impact points scored in a particular game. 

The model will run two separate regressions to determine the expected point totals for each team. The first will compare the Home Offense vs Away Defense and the second will compare the Away Offense vs the Home Defense. The regression will input each team's current-season statistics to predict an expected point total based on training of the historical data. These outputs will be compared to determine who will score more points (the winner), the difference between these expected totals (the spread), and the sum of the point totals (the expected points scored)

For the purpose of proper scaling, all metrics compared must be on a per game basis. This is important for two main reasons:
1. Comparing team totals in-season can skew results, as teams have bye weeks and have played a different number of games.
2. The NFL moved from a 16-game season to a 17-game season in 2021, so comparing seasons before and after this switch can skew results.

**Primary audience**: Online sportsbooks like DraftKings, Caesars, FanDual and BetMGM. All these companies offer live odds to bet on the spread for NFL games.  Single plays in a game can completely change the momentum and probability of victory for one team or another, and sportsbooks need to have good algorithms that can analyze game situation quickly and effectively to give themselves an advantage over people watching the game live. People react to what they see, so the algorithm needs to be able to immediately make predictions play-by-play and possession-by-possession. My goal is to use historical data of likelihood of victory for teams in certain scenarios.

**Secondary audience**: users that want to get ahead of the system. They could use the program to the compare their own personal spreads to those that the book has already set and bet when they see a significant difference between the two. 


# Features

**Offensive Metrics**
- Points per game
- Rushing yards per game
- Passing yards per game
- Offensive penalty yards
- 3rd-down conversation rate
- 4th-down conversion rate
- Redzone conversion rate
- Interceptions per game
- Fumbles per game
- Sacks / yards per game
- Number of plays per gamme
- Formations
- Play-call breakdown (passing vs rush %)
- Depth-of-target

**Defensive Metrics**
- Points against per game
- Rushing yards against per game
- Passing yards against per game
- Defensive penalty yards
- 3rd-down stop rate
- 4th-down stop rate
- Redzone prevent rate



