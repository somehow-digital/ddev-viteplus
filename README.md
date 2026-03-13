# Vite+ for DDEV

DDEV addon that provides a Vite+ service and commands to run inside your DDEV project.

## What is Vite+?

[Vite+](https://viteplus.dev) is the unified toolchain for the web, providing a complete development environment with Vite, package management, testing, and more.

## Install

In your DDEV project:

```bash
ddev add-on get somehow-digital/ddev-viteplus
ddev restart
```

## Commands

- **`ddev vp <args...>`**

Examples:

```bash
ddev vp install
ddev vp dev
```

## URLs

The dev server container exposes Vite on:

- **HTTPS**: `https://<project>.ddev.site:3000`

**Configuration**: Add this to your `vite.config.js`:

```js
// vite.config.js
export default {
  server: {
    host: '0.0.0.0',
    port: 3000,
    allowedHosts: [
      'viteplus'
    ]
  }
}
```

**Internal Container Access**: From other DDEV containers (e.g., PHP/web container), use:
- `http://viteplus:3000`
