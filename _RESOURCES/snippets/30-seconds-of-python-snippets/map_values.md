---
title: map_values
tags: dictionary,intermediate
firstSeen: 2019-08-20T15:34:30+03:00
lastUpdated: 2020-11-02T19:28:27+02:00
---

Creates a dictionary with the same keys as the provided dictionary and values generated by running the provided function for each value.

- Use `dict.items()` to iterate over the dictionary, assigning the values produced by `fn` to each key of a new dictionary.

```py
def map_values(obj, fn):
  return dict((k, fn(v)) for k, v in obj.items())
```

```py
users = {
  'fred': { 'user': 'fred', 'age': 40 },
  'pebbles': { 'user': 'pebbles', 'age': 1 }
}
map_values(users, lambda u : u['age']) # {'fred': 40, 'pebbles': 1}
```