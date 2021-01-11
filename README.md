# Python-CayenneLPP

## Introduction

This is a fork of [_Python-CayenneLPP_ deocoder from OlegZv](https://github.com/OlegZv/Python-CayenneLPP) meant to be used as a module inside the project directory instead of a global package (Although it can be used this way as well)

Open-source library for python to decode CayenneLPP format payload.
The Cayenne Low Power Payload (LPP) provides a convenient and easy way to send data over LPWAN networks such as LoRaWAN. More details on CayenneLPP payload [here](https://github.com/myDevicesIoT/cayenne-docs).

## Installation

This fork is not available in PyPy as [OlegZv's](https://github.com/OlegZv/Python-CayenneLPP) but can be installed using the following command

``` bash
python setup.py install
```

or by extracting the (zip version) of the source code into the proyect root directory. If the files are extracted using _lpp_ as the name of the root directory, you can import the files using the following line.

``` python
from lpp.python-cayennelpp.decoder import decode
```

## Usage
To decode payload simply use method decode() from this package

```python
>>>from python_cayennelpp.decoder import decode
>>>print(decode('03670110056700FF'))
[{'channel': 3, 'name': 'Temperature Sensor', 'value': 27.2}, {'channel': 5, 'name': 'Temperature Sensor', 'value': 25.5}]
```
## Additional info
The package may raise following exceptions:
- `TypeError` - if the provided data is not of the `str` type
- `ValueError` - if the provided data length is not equal to the expected

> Note: if the package receives a wrong sensor type the intermediate result of the decoder will be returned, error printed to the stdout, but `KeyError` exception **will not be raised**
