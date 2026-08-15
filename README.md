# POC Assets CDN

This repository is a proof-of-concept image CDN hosted from GitHub.

Only files inside `assets/` are intended to be public CDN assets. The `temp/` folder is a working folder and should not be used by consumers.

## CDN URL

Use jsDelivr with this GitHub repo:

```text
https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/<asset-path>
```

Example:

```text
https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/assets/3d-icons-pink-sets/3d-calendar-reminder-bell-icon.png
```

In HTML:

```html
<img
  src="https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/assets/3d-icons-pink-sets/3d-calendar-reminder-bell-icon.png"
  alt=""
/>
```

## How To Publish

1. Add image files under `assets/`.
2. Commit the changes.
3. Push `main` to GitHub.
4. Use the jsDelivr URL pattern above to load the asset.

For a fixed version, use a git commit SHA instead of `main`:

```text
https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@<commit-sha>/<asset-path>
```

## Cache Notes

For this POC, `@main` is convenient because URLs stay simple. jsDelivr may cache files, so updates to an existing file path may not appear immediately. For reliable immutable URLs, publish with a commit SHA or use new filenames when replacing assets.

## Available Assets

See [ASSETS.md](./ASSETS.md) for the current collection list and counts.

