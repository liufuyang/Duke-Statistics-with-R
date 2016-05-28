# Week 4

## Binomial Distribution

```
# of senarios X P(single scenario)
```

$$ \binom{n}{k} = {{n!}\over{k! (n-k)!}} $$

$$P(\text {k success in n trails}) = \binom{n}{k} \cdot p^k (1-p)^{(n-k)}$$

### Binomial Conditions:
1. the trails must be independent
2. the number of trails n, must be fixed
3. each trial outcome must be classified as a success or a failure
4. the probability of success, $$ p $$ must be the same for each trail 

### Expected value (mean) of binomial distribution:
$$ \mu = n p $$

### Standard deviation of binomial distribution:
$$ \sigma = \sqrt{np(1-p)} $$

# in R:

* `choose(n, k)` function
* `dbinom(k,size=n, p=0.5)`
* two ways to calculate binomial distribution:
	* norm distribution with `pnorm`
	* sum of `dbinom` function, with each section

For example:
n=245, p=0.25, k=70

Resulting mean=61.25, SD=6.78

Normal distribution approximation:
```
1- pnorm(70-0.5, 61.25, 6.78) # with 0.5 adjustment, normal approximaiton
```
gives result `0.1118`

Sum of dbinom:
```
sum(dbinom(70:245, 245, 0.25)) # direct add binomal
```
gives result `0.1128`

## Success-failure rule:
A **binomial distribution** with at least 10 expected successes and 10 expected failures closely follow a **normal distribution**

$$ np >= 10 $$
$$ n(1-p) >= 10 $$
