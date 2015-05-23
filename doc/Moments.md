
# Moments


````julia
using OnlineStats, DataFrames
````





### Create object with the first batch
````julia
o = Moments(rand(100))
````





### Update estimates with many batches
````julia
for i = 1:10000
    update!(o, rand(100))
end
````





### Check estimates
Truth:

| Estimate | value
|----------|--------
| Mean     | 0.5
| Var      | 0.08333...
| Skewness | 0
| Kurtosis | -1.2

````julia
julia> DataFrame(o)
1x5 DataFrame
| Row | μ        | σ²        | skewness     | kurtosis | nobs    |
|-----|----------|-----------|--------------|----------|---------|
| 1   | 0.499999 | 0.0832945 | -0.000144205 | -1.20046 | 1000100 |

````



