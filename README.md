# miniredis-python

A minimal redis client in python -- 25 lines ;)

Inspired by [miniredis-ruby](https://github.com/stulentsev/miniredis-ruby)

Usage:

```python
from miniredis import MiniRedis

r = MiniRedis()

r.set('foo', 2) # => 'OK'
r.get('foo') # => '2'

r.sadd('bar', '1') # => 1
r.sadd('bar', '2') # => 1
r.smembers('bar') # => ['1', '2']
```

The one quirk is that `del` is a reserved keyword in python, so using
`r.del('baz')` throws a SyntaxError.  MiniRedis has a line to translate
`delete` to `del`, so you can use `r.delete('baz')` instead.

**Please note**: This is a toy implementation, and is severely untested.
Use at your own risk ;)
