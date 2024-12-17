# Sec3_FP_DrewLippert_MaxMorgan_BradLove

# Analysis of College Football Play-Style Over Time

# INTRODUCTION AND PURPOSE

In America, College Football has time and time again filled our fall Saturdays with numerous excitements of rooting on our alma maters, giving us the feeling that we are somehow a part of the team.  Over time, however, the game has changed.  NIL and Power 5 conference teams dominate, while intricacies of offensive and defensive possessions have changed to a game script developing more points than ever before.  

In this report, we will show exactly how the game has changed, using offensive statistics from various teams over the past 10 years, 2013 to 2023, to be specific.  All attributes that we will be using are found in the various datasets provided by our Kaggle source.  In using different variables, such as Offensive Time of Possession, and Passing / Rushing Attempts, we hope to clearly see a relationship.  Overall, we will be asking this question, in hopes of finding an answer: How has the overall playstyle of college football evolved over the past decade?

# LITERARY REVIEW

In looking at how college football now favors offensive schemes, we can first look at the new offensive rules implemented this season.  Instead of prolonging games that drag up scores and involve more offensive plays to be run, college overtime now consists of two-point conversions after the second touchdown scored by either team, allowing games to finish quicker, while also allowing teams to run plays that do not affect the entirety of their stat sheet.  

The late 1990s and early 2000s introduced the world to the “spread” offense in college football.  This meant “spreading [the] defense thin and creating more explosive plays…[which] emphasized speed, agility, and quick decision-making, fundamentally changing the game by prioritizing tempo and mismatches over brute strength” (Student Union Sports).  Key implementers of this tactic were coaches and pioneers like Rusty Russell, Mike Leach, Urban Meyer, and Chip Kelly, all of whom were in favor of the game becoming “mobile quarterbacks making jaw-dropping runs, and high-scoring shootouts [that soon] became the norm” (Student Union Sports).  Forget the statistics, more people tuned into these games as well, creating more money for the overall game.

However, in recent years, we have found that the “spread” offense that was originally utilized to create these “explosive plays” is utilized less and less, and that the idea of defense is becoming more of a focal point in week-to-week matchups.  Additionally, in recent years, penalties have become more of a factor, as NCAA officials deal greatly in protecting vulnerable players from massive hits that could prove to be a detriment if they continue their careers onto the National Football League (NFL).  

Take the 2021 season as an example.  According to a CBS Sports article from February of 2022, total scoring was down to 28.51 points/team, which was the lowest since 2011, when scoring was at 28.29 points/team.  In order to stop powerhouse offenses, coaches had to become creative in defensive play-calling so that they could limit opportunities, just as they have always prided themselves in limiting points.  

Additionally, the 2021 playoffs found two of the teams being the University of Georgia and the University of Cincinnati.  Amazingly, and on-topic with this, they were #1 and #4, respectively, in red zone defense, proving that defense has become prominent again in these teams that found lasting success.  In their own words: “It wasn’t a defensive revolution in college football, but it was a step in the right direction” (Dodd 2022)

Even in looking at our data pool from the most recent championship season of 2023, the National Champions of the University of Michigan had a overall offensive rank of 66 in the country, but had the #1 defense in terms of rank.  This directly, and very recently, provides ample evidence that strong defenses have made a comeback.  On the other hand, in looking at this same dataset, a team like the University of North Texas had an offensive rank of 6 in the country, while their defensive rank was 130, almost dead-last.  Their record:  5-7, with no chance of making the College Football Playoffs.  

# FAIR AND CARE PRINICIPLES

In looking at how our data correlate with the FAIR and CARE principles, we can first look at how the data was accessed.  FAIR principles state that the data must be easy for anyone to find, and can be reused by anyone who wishes to do the same data analysis that we are currently doing.  In this way, our data is extremely accessible.  We easily got our college football data from Kaggle, who made it incredibly easy to download and analyze the statistics.  

Additionally, the CARE principles say that there must be some form of ethics in the way that the data was collected to be shared.  To our knowledge, there has been nothing wrong with anything regarding data format and collection mechanisms, making it a very strong candidate for our data analysis.

# THE 'HOWS'

In order to properly show how college football has changed over the past years, we chose to use data that analyzes each FBS team’s statistics on both offense, as well as defense.  Such variables that we will be looking at our, as follows: 
OFFENSE:
Passing Yards
Passing TDS
Rushing Yards
Rushing TDS
DEFENSE:
Average Points Per Game Allowed
Touchdowns Allowed

In analyzing these metrics and comparing them to different years, we will be able to see how these statistics changed over time. 

GRAPHS

2013 

2020

# ANALYSIS 

In looking at these similar graphs, we see that we are analyzing a team’s success based on offensive yards.  At first glance, it is very evident that, while there is obviously a positive correlation between wins and offensive efficiency, we see that, in 2011, offense played a larger role in these victories.  In comparison, 2023 saw a significant decrease in relationship between the two variables.  We can conclude, based on these figures, that offense played less of a role in obtaining the same number of wins in 2023 than it did in 2011.  

# LINEAR REGRESSION

In this portion of our analysis, we completed linear regression models for offensive and defensive statistics, analyzed each of their p-values, and compared them to 0.05 to see if they had a statistically significant relationship on our primary variable of “Wins.”  

Read in the data
data2013 <- read.csv("/Users/drewlippert/Downloads/COLLEGEFOOTBALLDATA/cfb13.csv")

Shows data in R
view(data2013)

Linear Regression Model 
model1 <- lm(Win ~ Pass.Yards + Pass.Yards.Per.Game + Pass.Touchdowns + Rush.Yds + Rushing.Yards.per.Game + Rushing.TD + Avg.Points.per.Game.Allowed + Opp.Pass.TDs.Allowed + Opp.Rush.Touchdowns.Allowed, data = data2013)

summary(model1)

This figure above is a linear regression model of 2013 offensive and defensive statistics.  First, “Pass.Yards” represents a team’s total passing yards for the entirety of the season, and its p-value of 0.95131 shows that there is not a significant relationship between it and a team’s wins.  “Pass.Yards.Per.Game” represents the average passing yards on a “per-game” basis, and its p-value of 0.81053 tells us that it doesn’t make a significant impact on our wins variable.  “Pass.Touchdowns” describes the total number of passing touchdowns thrown in the entirety of the season, and its p-value of 0.00549 shows us that there is a positive statistical significance between passing touchdowns and wins, unlike the previous two explanatory variables.  “Rush.Yds” tells us the total number of yards by rushing in a given season, and its p-value of 0.00495 also tells us that there is a significant relationship between wins and total, team rushing yards.   “Rushing.Yards.Per.Game,” similar to the previous variable, describes rushing yards, but instead, in the form of a “per-game” basis.  It has a p-value of 0.00752, which shows that there is a positive relationship between it and a team’s wins because of its being greater than 0.05.  “Rushing TDs,” similar to “Pass.Touchdowns,” tells us the total number of rushing touchdowns, and its p-value of 0.00218 tells us there is a positive impact in wins.  This makes sense because anytime that you are scoring touchdowns is going to leave a positive impact and heighten your chances of winning.
	
Secondly, the last three variables in the table above from 2013 are defensive statistics.  “Avg.Points.per.Game.Allowed” is very self-explanatory, as it tells us the average points each team allows on defense.  Additionally, “Opp.Rush.Touchdowns.Allowed” tells us the amount of rushing touchdowns each defense lets up.  Both p-values, 8.11e-05 and 0.05029, respectively, are less than 0.05, meaning that both have a significance on a team’s chances of winning.  However, the variable of “Opp.Pass.TDs.Allowed,” which means the amount of passing touchdowns a defense lets up, is 0.29271, which means there is not a significance on it to a team’s wins.  

Overall, this analysis of 2013 tells us that there is a heavy emphasis on good offenses, especially good passing and rushing schemes, which are vital for a team's success in the form of wins.  This aligns with our original theory from our “Literary Review” section that explained how offensive “spread” playstyles made up a good portion of the 2000s and into the 2010s, which fits into our 2013 timeline.  However, as we will see, defenses had to adapt to these explosive playstyles, and combat them with harder defensive play.

# WORKS CITED

“College Football Defenses Finally Claw Back as Some Offensive Averages Reach Lowest Points in a Decade.” CBSSports.com, 2022, www.cbssports.com/college-  football/news/college-football-defenses-finally-claw-back-as-some-offensive-averages-reach-lowest-points-in-a-decade/. Accessed 13 Dec. 2024.

“College Football Team Stats Seasons 2013 to 2022.” Www.kaggle.com, www.kaggle.com/datasets/jeffgallini/college-football-team-stats-2019.

GoRout. “NCAA Rules Changes and Updates over Time.” GoRout, 23 Apr. 2024, gorout.com/ncaa-rules/. Accessed 11 Dec. 2024.

Union, Student. “The Evolution of Offense: How Spread Formations Revolutionized College Football - Student Union Sports.” Student Union Sports, Dec. 2024, studentunionsports.com/the-evolution-of-offense-how-spread-formations-revolutionized-college-football/. Accessed 13 Dec. 2024.
