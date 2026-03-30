# DTC Static Assets

Static assets for DTC web properties, served via [jsDelivr CDN](https://www.jsdelivr.com/).

## Usage

Files are accessible via jsDelivr using tagged releases:

```
https://cdn.jsdelivr.net/gh/DTC-Inc/static@{tag}/{path}
```

### Examples

```html
<!-- Latest release -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/DTC-Inc/static@latest/css/portal.css">

<!-- Specific version -->
<img src="https://cdn.jsdelivr.net/gh/DTC-Inc/static@v1.0.0/brand/logo.svg">

<!-- Development (not cached, don't use in production) -->
<img src="https://cdn.jsdelivr.net/gh/DTC-Inc/static@development/brand/logo.svg">
```

### Cache Behavior

- Tagged versions (`@v1.0.0`): permanently cached, immutable
- `@latest`: cached ~12 hours, updates when new releases are tagged
- Branch names (`@development`): cached ~12 hours, use only for testing

## Directory Structure

```
brand/          Logos, icons, brand assets
  logo.svg
  logo-white.svg
  favicon.ico
backgrounds/    Background images for web properties
css/            Shared stylesheets
fonts/          Web fonts (if self-hosted)
downloads/      Client-facing downloadable files
```

## Releasing

1. Merge `development` into `release`
2. Tag the release: `git tag v1.0.0 && git push --tags`
3. jsDelivr picks up the new tag automatically
4. Purge cache if needed: `https://purge.jsdelivr.net/gh/DTC-Inc/static@latest/{path}`
