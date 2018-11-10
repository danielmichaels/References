# Requests-cache and requests-html compatibility

At the time of writing requests-cache is not compatible with requests-html.

I will investigate this later but the following test indicates it is not
functioning as expected.

```python

import requests
import requests-cache
from requests-html import HTMLSession

t1 = time.time()
for i in range(10):
    requests.get('http://httpbin.org/delay/1')
    print(time.time() - t1)

t1 = time.time()
session = HTMLSession()
for i in range(10):
    session.get('http://httpbin.org/delay/1')
    print(time.time() - t1)

```
