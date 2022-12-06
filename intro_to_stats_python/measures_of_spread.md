# Measures of spread 
Measure of spread is is another set of summary statistic

**Spread:**
- it describe how spread apart or close apaart data poitns are. just like measue of center there are few different measure of spread

## Variance
- measures the average distance of each data point to the data's mean

### Calculate variance
+ **Manual proceess**
  1. Subtract mean from each data point
      ```python
      dists = msleep['sleep_total'] - np.mean(msleep['sleep_total'])
      print(dists)
      ```
  2. Square each distance
      ```python
      sq_dists = dists ** 2
      print(dist)
      ```
  3. Sum squared distance
      ```python
      sum_sq_dists = np.sum(sq_dists)
      print(sum_sq_dists)
      ```
  4. Divide by number of data points -1
      ```python
      variance = sum_sq_dists/(83-1)
      print(variance)
      ```

+ **Using Numpy**
    ```python
      import numpay as np
      # without `ddof=1`, population variance is calculated instead of sample variance
      np.var(msleep['sleep_total'], ddof=1)
    ```
    **Official Documentation**
    - [numpy.var()](https://numpy.org/doc/stable/reference/generated/numpy.var.html)

## Standard deviation 
+ **Manual process**
  1. take the square root of the Variance
      ```python
       import numpy as np
       np.sqrt(variance)
      ```
+ **Using Numpy**
  ```python
   import numpy as np
   np.std(msleep['sleep_tatol'], ddof=1)
  ```
  **Official Documentation**
  - [numpy.std()](https://numpy.org/doc/stable/reference/generated/numpy.std.html)

## Mean absolute deviation
```python
import numpy as np
dists = msleep['sleep_total'] - mean(msleep$sleep_total)
np.mean(np.abs(dists))
```
### statndard deviation vs. mean absolute deviation
- standard dev squares distance, penalizing longer distance more than shorter ones.
- Mean absolute deviation penalizes each distance equally.
- One isn't better than the other, but SD is more common than MAD.


## Quantiles
- also called as percentiles. It split up the data into some number of equal parts.

**example**
```python
import numpy as np
np.quantile(msleep['sleep_total'], 0.5)
```
### Quartiles 
```python
import numpy as np
np.quantile(msleep['sleep_total'], [0, 0.25,  0.5, 0.75, 1])
```
**Official Documentation**
- [numpy.quantile()](https://numpy.org/doc/stable/reference/generated/numpy.quantile.html)

### Quantile using np.linspace()
```python
np.linspace(start, stop, num)
np.quantile(msleep['sleep_total'], np.linsapce(0, 1, 5))
```
**Official Documentation**
- [numpy.linspace()](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html?highlight=linspace#numpy.linspace)

## Boxplots use quartiles
- *The boxes in box plots represent quartiles. The bottom of the box is the first quartile, and the top of the box is the third quartile. The middle line is the second quartile, or the median.*
```python
import matplotlib.pyplot as plt
plt.boxplot(msleep['sleep_total'])
plt.show()
```

## Interquartile range(IQR)
- height of the  box in a boxplot

```python
np.qunatile(msleep['sleep_totla'], 0.75) - np.quantile(msleep['sleep_total'], 0.25)
# or
from scipy.stats import iqr
iqr(msleep['sleep_total'])
```
**Official Documentation**
- [scipy.stats iqr()](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html?highlight=linspace#numpy.linspace)

## Outliers 
- data points that is substantially different from the others
  - **A data point is an outlier if:**
    - data < Q1 - 1.5 * IQR or
    - data > Q3 + 1.5 * IQR

### finding outliers
**example:**
- well start by calcualting the IQR of the mammals' body weights

```python
from scipy.stats import iqr
iqr = iqr(msleep['bodywt'])
lower_threshold = np.quantile(msleep['bodywt'], 0.25) - 1.5 * iqr
upper_threshold = np.quantile(msleep['bodywt'], 0.75) + 1.5 * iqr
```
- subset the DF to find mammals whose body weight is below or above  the thresholds.
```python
msleep[(msleep['bodywt'] < lower_threshold) |  (msleep['bodywt'] > upper_threshold)]
```

## All in one
```python
msleep['bodywt'].describe()
```
