# distutils_twine

A tiny library that lets you use `python3 setup.py release` instead of
`twine upload dist/*`.

## Setup

If you use `setup.cfg`, add the following to it:

```
[options]
setup_requires =
    twine
    wheel
    distutils_twine~=3.0

[options.entry_points]
distutils.commands =
    release = distutils_twine:release
```

If you use `setup.py` exclusively, add the following to it:

```python
import setuptools
from distutils_twine import UploadCommand

setuptools.setup(cmdclass={"release": UploadCommand})
```
