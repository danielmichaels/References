# Iterating over nested JSON

Is a PITA.

this recursive function is helpful for nested arrays.

```python
def item_generator(json_input, lookup_key):
if isinstance(json_input, dict):
    for k, v in json_input.items():
        if k == lookup_key:
            yield v
        else:
            yield from item_generator(v, lookup_key)
elif isinstance(json_input, list):
    for item in json_input:
        yield from item_generator(item, lookup_key)
```

all credits [here](https://stackoverflow.com/questions/21028979/recursive-iteration-through-nested-json-for-specific-key-in-python)
