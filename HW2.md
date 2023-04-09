# For loop vs Lapply

### 2023-23441 장재혁

### 통계학과

```R
x <- list(a = rnorm(2000,10), b = rnorm(1000), c = rnorm(2000, 1), d = rnorm(10000, 5), e = rnorm(4000, 24), f = rnorm(3000, 10))

# for loop
start_time <- Sys.time()
for (p in x) {
  mean(p)
}
end_time <- Sys.time()
elapsed_time <- as.numeric(difftime(time1 = end_time,
                                    time2 = start_time,
                                    units = "secs"))
cat("elapsed time : ",sprintf("%.3f",elapsed_time),"sec",sep="")

# lapply
start_time <- Sys.time()
y <- lapply(x, mean)
end_time <- Sys.time()
elapsed_time <- as.numeric(difftime(time1 = end_time,
                                    time2 = start_time,
                                    units = "secs"))
cat("elapsed time : ",sprintf("%.3f",elapsed_time),"sec",sep="")
```

Output

```
# for loop
elapsed time : 0.004sec
# lapply
elapsed time : 0.002sec
```
