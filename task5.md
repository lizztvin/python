![image](https://github.com/lizztvin/python/assets/74359143/31d780c8-7a56-4bcf-9347-c2e8d41a84a6)
```python
from math import ceil
from math import floor
def main(x):
    res = 0
    n = len(x)
    for i in range(0, n):
        res += 19 * (2 * (x[floor(i / 3)]) ** 3 + (x[i]) ** 2)
    return res

```

![image](https://github.com/lizztvin/python/assets/74359143/14f15a9f-422e-453c-b9c6-f5b0ad929c4d)
```python
def main(z, y, x):
    sum = 0
    n = len(x)
    z = [0] + z
    y = [0] + y
    x = [0] + x
    for i in range(1, n + 1):
        sum += 43 * (16 * (x[i] ** 3) - y[n + 1 - i] - 60 * (z[i] ** 2))
    return 33 * sum

```
