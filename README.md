# Binaries

Binaries allows to manipulate ctypes.Structure and ctypes.Union like a dict object.

## Requirements

No dependencies.

## Usage

```python
from ctypes import c_int
from binaries import DictStructure

class Data(DictStructure):
    _fields_ = [
        ('a', c_int),
        ('b', c_int),
        ('c', c_int),
    ]

data = Data()

data.a = 10
data.b = 20
data.c = 30

print data['a'], data['b'], data['c']

```

### Iterations

```python
for key in data:
    ...
```

```python
for value in data.values():
    ...
```

```python
for key, value in data.items():
    ...
```

### Convert pure dict object

```python
data.dict
```

### Convert JSON

```python
import json

json.dumps(data.dict)
```

or

```python
json.dumps(data, cls=binaries.CDataJSONEncoder)
```

## License

[![license](https://img.shields.io/github/license/rinatz/binaries.svg)](https://github.com/rinatz/binaries/blob/master/LICENSE)

Copyright (c) 2017 Kenichiro IDA
