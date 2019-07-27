[<img src="https://ipregistry.co/assets/icons/icon-72x72.png" alt="Ipregistry" width="64"/>](https://ipregistry.co/) 
# Ipregistry Python Client Library

[![License](http://img.shields.io/:license-apache-blue.svg)](LICENSE)
[![Travis](https://travis-ci.com/ipregistry/ipregistry-python.svg?branch=master&style=flat-square)](https://travis-ci.com/ipregistry/ipregistry-python)
[![PyPI](https://img.shields.io/pypi/v/ipregistry)](https://pypi.org/project/ipregistry/)

This is the official Python client library for the [Ipregistry](https://ipregistry.co) IP geolocation and threat data API, 
allowing you to lookup your own IP address or specified ones. Responses include more than 50 data points including 
location, currency, timezone, threat information, and more.

## Getting Started

You'll need an Ipregistry API key, which you can get along with 100,000 free lookups by signing up for a free account at [https://ipregistry.co](https://ipregistry.co).

### Installation

```
pip install ipregistry
```

### Quick Start

#### Single IP Lookup

```python
from ipregistry import IpregistryClient

client = IpregistryClient("YOUR_API_KEY")
ipInfo = client.lookup("54.85.132.205")
print(ipInfo)
```

#### Batch IP Lookup

```python
from ipregistry import IpregistryClient

client = IpregistryClient("YOUR_API_KEY")
ipInfoResults = client.lookup(["54.85.132.205", "8.8.8.8", "2001:67c:2e8:22::c100:68b"])
print(ipInfoResults)
```

#### Origin IP Lookup

```python
from ipregistry import IpregistryClient

client = IpregistryClient("YOUR_API_KEY")
ipInfo = client.lookup()
print(ipInfo)
```

### Caching

The Ipregistry client has built-in support for in-memory caching. The default cache strategy is to memoize up to 
2048 lookups for at most 24h. You can disable caching by passing an instance of `NoCache`:

```python
from ipregistry import IpregistryClient, NoCache

client = IpregistryClient("YOUR_API_KEY", cache=NoCache())
```

### Errors

TODO

### Filtering bots

TODO

## Other Libraries

There are official Ipregistry client libraries available for many languages including 
[Java](https://github.com/ipregistry/ipregistry-java), 
[Javascript](https://github.com/ipregistry/ipregistry-javascript), and more.

Are you looking for an official client with a programming language or framework we do not support yet? 
[let us know](mailto:support@ipregistry.co).