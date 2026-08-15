# POC Assets CDN

This repository is a proof-of-concept image CDN hosted from GitHub.

Only files inside `assets/` are intended to be public CDN assets. The `temp/` folder is a working folder and should not be used by consumers.

## CDN URL

Use jsDelivr with this GitHub repo:

```text
https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/<asset-path>
```

Overlay example:

```text
https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/assets/overlay/3d-icons-pink-sets/3d-calendar-reminder-bell-icon.png
```

Frame example:

```text
https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/assets/frames/vintage-tarot-theSun.png
```

In HTML:

```html
<img
  src="https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/assets/overlay/3d-icons-pink-sets/3d-calendar-reminder-bell-icon.png"
  alt=""
/>
```

## Folder Structure

- `assets/overlay/` contains transparent overlay/sticker image collections.
- `assets/frames/` contains frame image assets.
- `temp/` contains working files and should not be used by CDN consumers.

## How To Publish

1. Add image files under `assets/overlay/` or `assets/frames/`.
2. Update `assets.json` and `ASSETS.md` so the manifest and docs match the asset tree.
3. Commit the changes.
4. Push `main` to GitHub.
5. Purge the jsDelivr cache for the manifest.
6. Use the jsDelivr URL pattern above to load the asset.

For a fixed version, use a git commit SHA instead of `main`:

```text
https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@<commit-sha>/<asset-path>
```

## Cache Notes

For this POC, `@main` is convenient because URLs stay simple. jsDelivr may cache files, so updates to an existing file path may not appear immediately. For reliable immutable URLs, publish with a commit SHA or use new filenames when replacing assets.

After updating `assets.json`, purge the manifest cache:

```bash
curl -L "https://purge.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/assets.json"
```

Then verify the CDN manifest:

```bash
curl -L "https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/assets.json"
```

## Available Assets

See [ASSETS.md](./ASSETS.md) for the current collection list and counts.

For apps that need to list or search assets, use the generated manifest:

```text
https://cdn.jsdelivr.net/gh/21myatt/poc-lib-assets-cdn@main/assets.json
```
