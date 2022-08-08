# Mixin

- Mixin é uma classe pai que fornece funcionalidade às subclasses, mas não se destina a ser instanciado.

- No mixin pode conter métodos que poderão ser usados em diferentes classes.

> Digamos que tenhamos diversas classes que tenham a necessidade de fazer uma conversão nelas, basta usarmos um mixin e toda classe poderá herda esse método.

```python3
from datetime import datetime

class ConversonMixin:
    @staticmethod
    def bit_to_gb(bytes: float) -> float:
        return bytes / 2**30

    @staticmethod
    def timestamp_to_date(time: float) -> str:
        return datetime.fromtimestamp(time).strftime()
```
