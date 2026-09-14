# MLB Team Payroll and Regular-Season Wins
## Research Question

How strongly is MLB team payroll associated with regular-season wins from 2011 to 2024?

## Background and Context
Some Major League Baseball teams can spend much more money than others. For example, the New York Mets and Los Angeles Dodgers have been spending more money in recent years than anyone else, while teams like the Cleveland Guardians and Miami Marlins do not spend very much. So the Mets and Dodgers can sign many of the good players, as they can give them deeper contracts, and steal any good players from the Guardians and Marlins, since they can give those players better contracts than the Guardians or Marlins. But does this contribute directly to wins? This project will examine the relationship between payroll from season to season and the number of regular season wins, for each team.

## Dataset
The dataset used for this project includes team payroll and regular season win totals for each season from 2011 to 2024, with the exception of 2020, due to the season being shortened to 60 games rather than 162 due to COVID-19. Because of this exception, we have a dataset of 13 seasons, and 390 total teams, since there is 30 teams in Major League Baseball.

The dataset was obtained from the Kaggle dataset MLB Team Payrolls 2011–2024. The original dataset contains information about team payroll, wins, losses, average age, roster status, and postseason results.

## Variables
The variables used in this project were:
- team
- season
- payroll (in millions of dollars)
- wins

Losses are technically part of this project, since every season included in this dataset was 162 games, so a team's number of losses is (total games - wins).

Payroll: The amount of money allocated by an MLB team toward its players during a season. This is the "Total Payroll Allocations" variable from the dataset, converted from dollar-formatted text into a numerical value measured in U.S. dollars. Payroll is the independent variable in this analysis.

Wins: The number of games an MLB team wins during the regular season. Playoffs are not included due to uneven number of games, as some teams play 0, while some may play as many as 22. It is the "Wins" variable in the dataset, representing the number of regular-season games won by each team. Wins are the dependent variable in this analysis.

## Data Cleaning and Preparation
The payroll variable had to be converted from text into numerical values so it can be used in statistical calculations. Many variables were not included, such as average age of the team, as well as payroll to injured players - a key contributor to a team's success. A team could spend a lot of money on players who end up getting injured, so they don't win as much in the absence of this player.

The dataset was checked for missing values or duplicates, leaving no missing values or duplicates after the check, outside of the 2020 season, which had to be removed due to the 60 game season, so each season has a comparable amount of games.

## Ethics and Limitations
The original dataset was intended to include 2000-2010, as well as 2025. However, this data could not properly be retrieved, as sites that have this do not allow web scraping. The website used, https://www.kaggle.com/, included a download link for the payroll of each team from 2011 to 2024. And once again, it is not right to include the 2020 season, as the number of wins will be much lower in this season, swaying the data.

Again, the payroll of each team includes injured players, who were not contributing. However, only including healthy players may cause a bias, because the injured players not included could have played the entire season before getting injured, so they could have contributed to a lot of wins but would not be included.

## Visualizations
![MLB Team Payroll vs. Regular-Season Wins](payroll_vs_wins.png)
This scatterplot shows every team from 2011 to 2024, sorted by wins vs. payroll. The blue line shows the regression, which shows the overall direction of the chart. The chart shows a positive correlation between payroll and wins, which is to be expected. However, this line is not as steep as to be expected. This chart shows that while, in general, higher payrolls correlate to more wins, this is not a guarantee. For example, the 2023 New York Mets spent the most money of all time - $341,673,777. For context, their 2024 team is the second highest of all time - $314,748,899. But despite the high payroll, the 2023 New York Mets went only 75-87, finishing 4th out of 5 teams in their division and failing to qualify for the playoffs. However, the 2011 Tampa Bay Rays spent only $45,386,925, the fifth lowest in this time frame (not counting 2020). Yet, they went 91-71, finishing 2nd out of 5 in their division and qualifying for the postseason. So despite spending $296 million less than the 2023 Mets, the Rays still had 16 more wins. But these are the two most extreme cases, as most teams contribute to the positive correlation.


![MLB Payroll Distribution and Average Wins by Payroll Level](payroll_distribution_vs_Wins.png)
This histogram splits all the teams into groups based off its payroll, and with the key on the left, the number of teams that fall in that range. The red line shows the average number of wins each of those teams achieved, with the key being on the right. This definitely shows an increasing number of wins as it goes, although the end dips down thanks to a very low number of teams with payrolls that high, so the 2023 Mets only winning 75 games lowers the total dramatically. Had there been a larger number of teams in this range, it can be assumed the average number of wins would be much higher, likely higher than the average of 95 wins by the group of teams with payrolls from about $250M to $275M.

## Statistical Analysis
The Pearson correlation between team payroll and regular-season wins was:
r = 0.369

This number represents a positive association between payroll and wins, as 0 would be no correlation. However, this is far from 1.0, which is a perfect correlation. Payroll has an effect on win count, but there are definitely many factors that also contribute. As seen with the 2023 Mets vs 2011 Rays case, there are many teams with higher payrolls and lower wins, and vice versa. However, there are more teams with lower payrolls with lower wins, as well as higher payrolls and higher wins.

For r^2, we got 0.226, or 22.6%, which means that 22.6% of the variation in regular season wins is explained by this linear relationship. Ryan-Tyler N. Mason, in his journal, "MLB Payroll Versus Wins in 2025", found that in the 2025 season, r^2 was 0.239, or 23.9%. This is a very similar number to what was found from 2011 to 2024. Once again, in his finding, the Mets fell well below the line in number of wins, yet had the highest payroll.

## Conclusion
From what the data shows, there is a correlation between payroll of Major League Baseball teams and regular season victories in a given year over the last 15 years. However, a team having above average seasons in terms of regular season wins cannot be entirely attributed to payroll. In fact, there are huge outliers, such at the highest payroll of this time period (2023 New York Mets) finishing with 16 fewer victories than one of the lowest payrolls of this time period (2011 Tampa Bay Rays). While one can argue that teams spend much more money in 2023 than 2011, this still does not defend the large difference. There has been a 64.99% increase in payroll over this time, from an average of $101 million to $166 million. However, the difference between the Rays and Mets is $296 million, and still the Rays had a large number of victories more than the Mets. These are the extreme outliers, however, and most teams fall within a short range of the correlation, which shows that just under 1/4 of the variation is explained by payroll.

## Code and AI Transparency

The complete code and analysis for this project are available in the GitHub repository, including the Jupyter Notebook used for data cleaning, analysis, statistical calculations, and visualizations. A direct link can be found here:
[Payroll vs. Wins Jupyter Notebook](https://github.com/brtaylor00/DTSC_2301/blob/main/Payroll_vs_Wins.ipynb)

## Academic References

Bledsoe, J., Conlin, A., Edwards, G., Gawlinski, M., & Lorenz, M. (2022, June 1). Relationship between MLB payroll and performance. https://scholar.valpo.edu/. https://scholar.valpo.edu/cgi/viewcontent.cgi?article=2084&context=cus

University of North Carolina at Chapel Hill. (2024). Patel – pay to play? an analysis between team payroll vs. performance. Patel – Pay to Play? An Analysis Between Team Payroll vs. Performance | Office for Undergraduate Research. https://our.unc.edu/abstract/patel-pay-to-play-an-analysis-between-team-payroll-vs-performance/ 

RTNM, A. (2025). MLB payroll versus wins in 2025. Random Thoughts from a Nonlinear Mind. https://rtnmblog.com/mlb-payroll-versus-wins-in-2025/ 
