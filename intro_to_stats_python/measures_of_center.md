# Measures of Center

Basics of summary statistics(mean, median, mode)

## Mean 
commonly knonw as average

```python
import numpy as np
np.mean(array[])
```
**Official Documentation:**
- [numpy.mean()](https://numpy.org/doc/stable/reference/generated/numpy.mean.html)

## Median

It is the value where 50% of the data is lower than it, and 50% of the data is higher. In short the middle value

We can calculate this by sorting all the data points and taking the middle one

```python
import numpy as np
np.median(array[])
```

**Official Documentation:**
- [numpy.median()](https://numpy.org/doc/stable/reference/generated/numpy.median.html)


## Mode
most frequent value of the data

```python
import statistics as stats 
stats.mode(array[])
```

**Documentation:**
- [statistics.mode()](https://docs.python.org/3/library/statistics.html#statistics.mode)


## Which measure of center to use?
*When data is skewed, the mean and median are different. The mean is pulled in the direction of the skew, so it's lower than the median on the left-skewed data, and higher than the median on the right-skewed data. Because the mean is pulled around by the extreme values, it's better to use the median since it's less affected by outliers.*

