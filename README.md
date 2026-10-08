# brandt.computer

[brandt.computer](https://brandt.computer)

Built with [static-site](../../relaylang/static-site) and styled with [style-grammar](../../workshop/style-grammar), the workshop house style.

- `content/` is the source: `index.md`, the document shell in `layouts/default.layout.relay` (meta tags live there), the site stylesheet `assets/style.css` (a serif reading face over style-grammar), and files copied as-is (`404.html`, `CNAME`, `.nojekyll`).
- `docs/` is the built site, which GitHub Pages serves. Never edit it by hand; the build deletes and rewrites it.

## Build

```sh
relay build.relay
```

`package.relay` names static-site and its dependencies by path, so the build needs the workshop checkout around this repository, with relay-markdown and relay-yaml libraries built for the current Relay.

## Publish

GitHub Pages deploys from the `main` branch, `/docs` folder. Commit `docs/` with the content change that produced it.

`404.html` is copied rather than built so it stays at the site root, and it links its stylesheets with root-absolute paths because Pages serves it at any missing URL.
