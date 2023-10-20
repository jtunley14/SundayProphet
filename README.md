# NFL Game Predictor

Welcome to my capstone! The goal of this project is to predict the outcome of NFL football games in 3 major metrics:
1. Winner
2. Spread
3. Point Total (O/U line)

Using historical NFL data dating back to 2004, I trained my model to determine how particular offensive and defensive metrics impact points scored in a particular game. 

The model will run two separate regressions to determine the expected point totals for each team. The first will compare the Home Offense vs Away Defense and the second will compare the Away Offense vs the Home Defense. The regression will input each team's current-season statistics to predict an expected point total based on training of the historical data. These outputs will be compared to determine who will score more points (the winner), the difference between these expected totals (the spread), and the sum of the point totals (the expected points scored)

For the purpose of proper scaling, all metrics compared must be on a per game basis. This is important for two main reasons:
1. Comparing team totals in-season can skew results, as teams have bye weeks and have played a different number of games.
2. The NFL moved from a 16-game season to a 17-game season in 2021, so comparing seasons before and after this switch can skew results.
