## User

The examples provided in this file assume you are already authenticated if authentication is required. Also assume we already have a discogs-client `Client` object called `ds`.

Assuming you are authenticated, you can retrieve your User object by calling the `identity()` method:

```python
me = ds.identity()
```

`User` objects contain many callable properties. For a full list of properties, call the Python `dir()` function with the User object as a parameter.

Some example properties include:
```python
me.name
me.profile
me.rank
me.avatar_url
```

Not all information available in the API response is mapped out, so if you need more information, you can look in the `data` property of the User object:

```python
me.data.keys()
```

## Collection

You can retrieve your collection information by calling the `collection_folders` property on a `User` object.

```python
all = me.collection_folders[0]
collection = all.releases
```

You can also sort the results of your collection by using the `sort()` method.

```python
all = me.collection_folders[0]
collection = all.releases.sort('artist', 'desc').page(1)
```

## Wantlist

You can retrieve your wantlist information by calling the `wantlist` property on a `User` object.

```python
wantlist = me.wantlist
```
