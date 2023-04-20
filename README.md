###RStudio Correlation code###

library(ggplot2)
library(dplyr)
library(broom)
library(ggpubr)

#import data in .csv, make sure of headers

hist(data$variable) # for distribution of normality

plot(variable.y ~ variable.x, data =data) # for linearity

###mulitple regression###
cor(data$variable1, data$variable2) # for independence of observations

#create linear model from data
title.lm <- lm(variable.y ~ variable.x, data = data)
summary(title.lm) # for reportable stats

#check of homoscedasticity
par(mfrow=c(2,2)) # make plots easier to view
plot(title.lm)

###plotting###
title.data.graph <- ggplot(data, aes(x=x variable, y=y variable)) + geom_point()
title.data.graph <- title.data.graph + geom_smooth(method="lm", col="red")

title.data.graph <- title.data.graph + stat_regline_equation(label.x = number, label.y = number)

income.graph + theme_bw() + labs(title = "Graph Title", x = "x axis label", y = "y axis label")

title.data.graph
