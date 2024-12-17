# Sec3_FP_DrewLippert_MaxMorgan_BradLove

data2013 <- read.csv("/Users/drewlippert/Downloads/COLLEGEFOOTBALLDATA/cfb13.csv")

view(data2013) ## Shows data in R

## Linear Regression Model 

model1 <- lm(Win ~ Pass.Yards + Pass.Yards.Per.Game + Pass.Touchdowns + Rush.Yds + Rushing.Yards.per.Game + Rushing.TD + Avg.Points.per.Game.Allowed + Opp.Pass.TDs.Allowed + Opp.Rush.Touchdowns.Allowed, data = data2013)
summary(model1)
