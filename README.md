# `udiff` - Automatic differentiation with uarray/unumpy.
[![Join the chat at https://gitter.im/Plures/uarray](https://badges.gitter.im/Plures/uarray.svg)](https://gitter.im/Plures/uarray?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) ![language](https://img.shields.io/badge/language-python3-orange.svg) ![license](https://img.shields.io/github/license/Quansight-Labs/udiff)

## Quickstart
```python
import uarray as ua
import unumpy as np
import udiff
from unumpy import numpy_backend

with ua.set_backend(numpy_backend), ua.set_backend(udiff, coerce=True):
    x = np.reshape(np.arange(25), (5, 5))
    x.var = udiff.Variable('x')
    x.diffs[x].diffs[x] = 0

    y = np.exp(2 * x)
    print(y)
    print(y.diffs[x])
    print(y.diffs[x].diffs[x])
```

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for more information on how to contribute to `udiff`.
