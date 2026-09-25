# Lab-2---HW-3

Study Group Members: Sara Troshani, Huzaifa 

## Age by Gender

## Age by Gender

```r
summary(Age[Gender == "female"])
summary(Age[Gender == "male"])
summary(Age[Gender == "trans"])
summary(Age[Gender == "other"])

mean(Age[Gender == "female"])
sd(Age[Gender == "female"])

mean(Age[Gender == "male"])
sd(Age[Gender == "male"])
```

```text
Female mean age: 51.62
Female standard deviation: 15.59

Male mean age: 53.29
Male standard deviation: 16.29
```

The average age for women was about 51.62 years, while the average age for men was about 53.29 years. Men were slightly older on average in this dataset.

## Age and K4SUM

```r
age_means <- aggregate(K4SUM ~ Age,
                       data = d_HHP2020_24,
                       FUN = mean)

plot(age_means$Age, age_means$K4SUM,
     pch = 19,
     xlab = "Age (years)",
     ylab = "Mean K4SUM (4 = best, 16 = worst)",
     main = "Average anxiety/depression score falls with age")

lines(lowess(age_means$Age, age_means$K4SUM),
      lwd = 2)
```

I chose age and K4SUM because I wanted to see if mental health changes with age. The graph shows that K4SUM generally goes down as age increases. Since a lower K4SUM means fewer anxiety and depression symptoms, older people in this dataset reported fewer symptoms on average.

This shows a relationship between age and K4SUM, but it does not mean that age directly causes the difference.

## Income and K4SUM

```r
boxplot(K4SUM ~ income_midpoint_factor,
        data = d_HHP2020_24,
        xlab = "Household income bracket (midpoint, $)",
        ylab = "K4SUM (4 = best, 16 = worst)",
        main = "Higher income, lower anxiety/depression score",
        las = 2)
```

I chose income and K4SUM because I wanted to see if income level was related to mental health. The boxplot shows that as income increases, K4SUM scores generally go down.

Since lower K4SUM scores mean fewer anxiety and depression symptoms, higher-income groups had lower K4SUM scores in this dataset. This shows a relationship between income and K4SUM, but it does not mean that higher income directly causes better mental health.
