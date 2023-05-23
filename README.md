# Plain react-ts rspack app

Generated using:

```
npm create rspack@latest
```

and choosing `react-ts`

## Demonstrate that `[ext]` is not replaced/resolved on build time

See in `rspack.config.js`:

```js
output: {
    filename: "[name].[contenthash:8][ext]",
  },
```

Build the app:

```
npm run build
```

See contents of `dist`:

```
index.html
main.5ac7aa5c.5ac7aa5c[ext].map
main.5ac7aa5c[ext]
main.c94f583d.c94f583d[ext].map
main.c94f583d[ext]
```

## Use rspack core `0.1.11`

With version `0.1.11` it works as expected, `[ext]` is replaced with actual extension.

## Documentation reference for `[ext]`

https://www.rspack.dev/config/output.html#file-context

## rspack issue link

[web-infra-dev/rspack/issues/3270](https://github.com/web-infra-dev/rspack/issues/3270)