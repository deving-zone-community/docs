# Sample Strategies

# Simple Gridbot on USDC/USK

before
--8<-- ".sample.yml"
after

``` yaml title="grid_usk_usdc.yml"
---
foo: bar
baz: up
```

``` title="sample.yml"
--8<-- ".sample.yml"
```

``` title="poc_usdc_usk_grid.yml"
--8<-- "poc_usdc_usk_grid.yml"
```

## what it does

buy sell 0.5% above middle

```yaml
---
foo: here # Code block content # (1)!
bar: here # Code block content # (2)
```

1.  Look ma, less line noise!
2.  Look ma, less line noise!

``` py linenums="1"
import tensorflow as tf
```

``` py title="bubble_sort.py"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```