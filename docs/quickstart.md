## Quickstart

### Instantiating the client object

```python
>>> import discogs_client
>>> ds = discogs_client.Client('ExampleApplication/0.1')
```

The string passed into the `Client` class is your User-Agent. A User-Agent is
required for Discogs API requests, as it identifies your application to the
Discogs servers.

There are more parameters the `Client` class accepts on instantiation; please
refer to the `Authorization` file for more details.

Once instantiated, you can either start making requests to endpoints that do not
require authentication, or you can authenticate and make requests to a wider
range of endpoints.

```python
release = ds.release(1293022)
print(release.title)
artists = release.artists
```

As you can see, once you fetch data from an endpoint, you can call various
properties and methods on those objects. See the `Database` documentation for a
full list of properties and methods.
