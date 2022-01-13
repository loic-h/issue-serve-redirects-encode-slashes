# [Issue] Serve - Redirect encode slashes

[Serve](https://github.com/vercel/serve)

When using augmented paremeters (like in [path-to-regexop](https://github.com/pillarjs/path-to-regexp)) in redirects and rewrites, slahes will be double encoded and make the URL unreachable.

With the following configuration:
```
"redirects": [
  {
    "source": "/bar/:path*",
    "destination": "/foo/bar/:path*"
  }
]
```

http://localhost:3000/bar/my/long/path redirects to http://localhost:3000/foo/bar/my%252Flong%252Fpath

## Install

```
$ npm i
```

## Reproduce the issue
Run

```
$ npm run serve
```

Open http://localhost:3000/bar/my/long/path
