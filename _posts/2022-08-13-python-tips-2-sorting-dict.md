---
title: 'Random Python tips #2: sorting lists into buckets with defaultdict'
date: 2022-08-13 15:00 +1100
categories: [Python]
Tags: [python]
---


# defaultdict is your friend


You've probably already found yourself in the following situation: you have a list of objects and you need to sort those objects into different buckets based on some criterion. Example:

```python
countries_list = [
 "Albania",
 "Australia",
 "Belgium"
]
```
We would like to sort those strings by their first letter and into a dict, ie obtain this result:

```python
sorted_countries = {
  "A": [
    "Albania",
    "Australia"
  ],
  "B": [
    "Belgium"
  ]
}
```

The most obvious way to do it would be:

```python
sorted_countries = {}
for country in countries_list:
  c = country[0]
  if c not in sorted_countries.keys():
    sorted_countries[c] = []
  sorted_countries[c].append(country)
```

This works but is quite verbose and not very readable, especially if you are already a few indentation levels deep. Luckily Python provides this collection: [defaultdict](https://docs.python.org/3/library/collections.html#collections.defaultdict), which lets us be more concise:

```python
from collections import defaultdict

sorted_countries = defaultdict(list)
for country in countries_list:
  c = country[0]
  sorted_countries[c].append(country)
```

# Going deeper

What if you need to sort on multiple levels, e.g sort by first letter first and by word length second?

```python
sorted_countries = {
  "A": {
    7: [
      "Albania"
    ],
    9: [
      "Australia"
    ]
  },
  "B": {
    7: [
      "Belgium"
    ]
  }
}
```

Well with defaultdicts that's easy. Just provide a `defaultdict` as the default:

```python
sorted_countries = defaultdict(lambda: defaultdict(list))
for country in countries_list:
  c = country[0]
  l = len(country)
  sorted_countries[c][l].append(country)
```

We have to use a lambda here because the contructor expects a _factory_: a function that returns the default object to insert.

Needless to say this operation would have been much more verbose with the original method.




