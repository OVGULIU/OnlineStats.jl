
# QuantileSGD


````julia
using OnlineStats, DataFrames
````





### Create model with the first batch
````julia
o = QuantileSGD(rand(100), StochasticWeighting(.7), τ = [.1:.2:.9])
````





### Update model with many batches
````julia
for i = 1:10000
    update!(o, rand(100))
end
````





### Check estimates
Since true distribution is Uniform(0, 1), true quantiles equal τ.

````julia
julia> DataFrame(o)
1x3 DataFrame
| Row | quantiles                                      | τ                     |
|-----|------------------------------------------------|-----------------------|
| 1   | [0.102063,0.304939,0.507841,0.705866,0.900356] | [0.1,0.3,0.5,0.7,0.9] |

| Row | nobs    |
|-----|---------|
| 1   | 1000100 |

````



