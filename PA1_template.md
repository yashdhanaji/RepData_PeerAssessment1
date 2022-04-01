Loading and preprocessing the data

unzip(zipfile = "activity.zip")
data <- read.csv("activity.csv")

What is mean total number of steps taken per day?
library(ggplot2)
total.steps <- tapply(data$steps, data$date, FUN = sum, na.rm = TRUE)
qplot(total.steps, binwidth = 1000, xlab = "total number of steps taken each day")
mean(total.steps, na.rm = TRUE)
## [1] 9354
median(total.steps, na.rm = TRUE)
## [1] 10395
