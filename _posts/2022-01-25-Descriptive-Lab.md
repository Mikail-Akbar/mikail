# Welcome to my descriptive lab!

The dataset I worked with entails the statistics regarding the football teams in Europe’s top 5 leagues (Serie A, Bundesliga, Ligue 1, La Liga, Premier League). The top 5 leagues in Europe are determined by the [UEFA league coefficients](https://www.uefa.com/nationalassociations/uefarankings/country/). In this data, each club corresponds to information about its league, goals scored, shots attempted per game, yellow cards, red cards, possession %, passing accuracy (in %), the # of aerial duels won, and the team rating. I’m interested in most of these categories (besides yellow cards, red cards, and team rating), and all I wanted to do is to try to find some correlations between the data. I also wanted to find some centers in the data to see how teams in Europe generally perform. As a result, I can better understand the tactics of the game and whether certain aspects lead to more goals, etc. 

### Center and variability in my data (98 teams)
|       | Goals | Shots per game | Pass accuracy (%) | Aerial duals won |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| Mean | 52.18 | 11.85 | 80.44 | 16.00| 
| Standard Deviation | 16.45 | 2.150 | 4.690 | 3.079 | 
| Min | 20.00 | 7.100 | 66.50 | 9.500 |
| 25% | 40.25 | 10.33 | 78.03 | 14.03 |
| 50% | 50.00 | 11.45 | 80.80 | 16.10 |
| 75% | 61.75 | 13.35 | 83.45 | 17.85 |
| Max | 99.00 | 17.10 | 89.70 | 26.80 |

### Some notes about the center and variability of the selected 4 categories
- The data for the goals scored is somewhat dispersed, compared to the data for the other 3 columns. The range is a whopping 79 goals, and the standard deviation is 16.45 goals. I visualized this data in a violin plot below.
- The data in all 4 columns are not skewed in any direction, as the means and medians are very close to each other. 

![violinplot]

## What I found:

#### 1. There is a direct relationship between possession and goals scored. 

![possgoals]

Regression line: 0.718

We can conclude that teams that have more possession score more goals, which is supported by our regression line of 0.718, a number that is close to 1. Based on this graph, I wonder why coaches deploy the counter-attack tactic, where the defense sits deep on the pitch and allows the other side to have possession so that when they win back possession, they can speed down the pitch to get an open, goal-scoring opportunity. 

#### 2. Serie A teams score the most goals, while La Liga teams score the least amount of goals. 

![goalbargraph]

We can conclude that Serie A teams have the most attacking tactics (leading to the most goals), while La Liga teams have the most defensive tactics. In the future, I can further analyze the attacking vs. defensive tactics of a team by looking at the average field position of the 10 outfield players, as well as the formation each manager employs (3-4-3, 4-3-3, 4-4-2, etc.)

##### 3. La Liga teams win the most aerial duels, while Serie A teams win the least aerial duels.

![aerialswonbar]

Since La Liga teams score the least goals, this can mean that they use more defensive tactics and hence win more aerial duels (a defensive statistic.) On the other hand, while Serie A scores the most goals, that can mean that they deploy more attacking attacks and thus win the least aerial duels.

##### 4. The information above is further corroborated by a scatter plot between goals and aerials won:

![aerialgoalsscatter]

Regression line: -0.496

Although the regression line is not entirely convincing, we can somewhat conclude that the more goals a team scores, the less aerial duels they win. This is a reasonable conclusion considering that teams either favor attacking or defensive tactics (a famous example is Chelsea FC’s “Park the Bus” tactic), so teams sacrifice defensive prowess to focus on scoring more goals. 

##### 5. There is an inverse relationship between aerial duels won and possession.

![aerialsposs]

Regression line: -0.544

This is a surprising relationship, since winning more aerial duels means to win possession. So, it’s interesting to find that teams that win less aerial duels have a bigger hold on possession. Although the regression line here is also not entirely convincing, there is still some correlation between the two variables.

##### 6. There is a direct relationship between a team’s shots per game and passing accuracy.

![shotspass]

Regression line: 0.684

We can conclude that the more shots a team takes per game, the higher their passing accuracy. This is supported by a regression line of 0.684. It’s possible that this relationship exists due to the technical quality of the team; if a team can find a way to create more shots per game, their passing accuracy would also reflect the technical excellence on the pitch. 

## Limitations
I wish this dataset included information about the teams’ record. This way I can analyze whether these various statistics (shots per game, possession, aerial duels, etc) has an effect on the success of the team. While it is interesting to correlate these statistics to the goals scored per game, scoring goals does not mean that a team is successful. Furthermore, as far as I know, the team rating presented in the dataset is subjective, since it is the average of the 11 players’ user-inputted rating. Team rating also has little significance in terms of the statistics of a team – it is rather a product of the team’s statistical performance (in terms of goals, possession etc). I am more interested in whether the various categories of the dataset affect other categories, not the team rating. So, it didn’t really make sense for me to incorporate the team rating in any of my graphs or data.