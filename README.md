# Investigation into `wsgi_scripts` replacement

## Current usage

Using flask's built-in debug server:

```shell
python -m hello.app
```

Using `mod_wsgi-express`:

```shell
mod_wsgi-express start-server hello/wsgi.py --log-to-terminal --port 8080
```

## Expected usage

Install with `pip install`, then execute from Python:

```
python -m hello.app
```

From a WSGI server that expects a WSGI script.

```
mod_wsgi-express start-server hello-wsgi --log-to-terminal --port 8080
```

(So `hello-wsgi` is on `$PATH`)

Finally, from the shell (useful but by no means mandatory):

```
hello-wsgi
```

(As above, `hello-wsgi` is on `$PATH`. You could also have something installed
via the normal console scripts path hence optionality)
