# Week3 Practical1 - Law of Large Numbers

As sample size increases, the sample mean and sample SD tend to get closer to the true population mean and SD.

The following code:
```R
population <- rnorm(1000, 52, 40)

samplemeans <- vector(length=100)
sampleSDs <- vector(length=100)

for(i in 1:100){
  y <- sample(population, i*10)

  samplemeans[i] <- mean(y)
  sampleSDs[i] <- sd(y)
}
```

The output:<br>
![Screenshot of output](Screenshots/image1.png)

## Explanation of the code

1. The following line code:
```R
population <- rnorm(1000, 52, 40)
```

Creates a simulated population of 1000 values from a normal distribution with:
- mean = 52
- SD = 40

2. The following line code:
```R
samplemeans <- vector(length=100)
sampleSDs <- vector(length=100)
```

Creates empty vectors to store:
- 100 sample means
- 100 sample standard deviations

3. The following line code:
```R
for(i in 1:100){
```

Runs a loop 100 times. Each loop uses a different sample size

4. The following line code:
```R
y <- sample(population, i*10)
```

Takes a sample from the population:
- When `i = 1`, sample size is 10
- When `i = 2`, sample size is 20
- Up to 1000

5. The following line code:
```R
samplemeans[i] <- mean(y)
sampleSDs[i] <- sd(y)
```

Stores the mean and SD for each sample.

## Plot 

Notice how the sample mean is more akin to the population mean as the sample size increases 

The following code:
```R
plot(samplemeans)
abline(h = 52)

plot(sampleSDs)
abline(h = 40)
```

The output:<br>
![Screenshot of the samplemeans plot](Screenshots/image2.png)
![Screenshot of the sampleSDS plot](Screenshots/image3.png)