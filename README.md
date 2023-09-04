# googletrans-3.1.0a0-tqdm

This repo is nearly same as [googletrans-3.1.0a0](https://pypi.org/project/googletrans/3.1.0a0/). Only diffrence is progress bar supoort when translating list. I changed this code:

```python
if isinstance(text, list):
    result = []
    for item in text:
        translated = self.translate(item, dest=dest, src=src, **kwargs)
        result.append(translated)
    return result
```

to this code:

```python
from tqdm import tqdm
if isinstance(text, list):
    result = []
    for item in tqdm(text):
        translated = self.translate(item, dest=dest, src=src, **kwargs)
        result.append(translated)
    return result
```

You can see this change [`client.py#L202`](https://github.com/Weyaxi/googletrans-3.1.0a0-tqdm/blob/main/googletrans/client.py#L202).

There has been no change other than this. 

# Installation
You can use this command to install liblary:

```python
pip install -q -U git+https://github.com/Weyaxi/googletrans-3.1.0a0-tqdm
```

