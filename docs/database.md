## Database

The examples provided in this file assume you are already authenticated if authentication is required. Also assume we already have a discogs-client `Client` object called `ds`.

### Searching

Simple example:

```python
results = ds.search('Can I borrow a feeling?')
```

The search method allows for all of the parameters that the raw Discogs API allows. A full list of allowable parameters are listed here: http://www.discogs.com/developers/#page:database,header:database-search

Example usage:

```python
results = ds.search('Can I borrow a feeling?', type='release')
results = ds.search('Can I borrow a feeling?', type='release,master')
results = ds.search('Can I borrow a feeling?', artist='Kirk', type='release')
results = ds.search('Can I borrow a feeling?', genre='Hip Hop')
```

The `results` object is a paginated list, so you need to specify which page of results to view, like so:

```python
# show list of first page results
print(results.page(1))
```

### Releases

Simple example:

```python
release = ds.release(581234)
```

`Release` objects contain many callable properties. For a full list of properties, call the Python `dir()` function with the Release object as a parameter.

Some example properties include:
```python
release.artists
release.year
release.images
release.notes
```

Not all information available in the API response is mapped out, so if you need more information, you can look in the `data` property of the Release object:

```python
release.data.keys()
```

### Artists

Simple example:

```python
artist = ds.artist(1622298)
```

`Artist` objects contain many callable properties. For a full list of properties, call the Python `dir()` function with the Artist object as a parameter.

Some example properties include:
```python
artist.profile
artist.name
artist.url
artist.releases
```

Not all information available in the API response is mapped out, so if you need more information, you can look in the `data` property of the Artist object:

```python
artist.data.keys()
```

### Labels

Simple example:

```python
label = ds.label(88949)
```

`Label` objects contain many callable properties. For a full list of properties, call the Python `dir()` function with the Label object as a parameter.

Some example properties include:
```python
label.profile
label.name
label.sublabels
label.releases
```

Not all information available in the API response is mapped out, so if you need more information, you can look in the `data` property of the Label object:

```python
label.data.keys()
```

### Master Release

Simple example:

```python
master = ds.master(751011)
```

`Master` objects contain many callable properties. For a full list of properties, call the Python `dir()` function with the Master object as a parameter.

Some example properties include:
```python
master.genres
master.main_release
master.tracklist
master.versions
```

Not all information available in the API response is mapped out, so if you need more information, you can look in the `data` property of the Label object:

```python
master.data.keys()
```
