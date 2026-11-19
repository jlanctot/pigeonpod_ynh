# PigeonPod, packaged for YunoHost

Self-hosted RSS feeds from YouTube and Bilibili.

This package targets PigeonPod 1.30.1 and follows the YunoHost packaging v2.1 template structure.

## Packaging choices

- Native YunoHost service; Docker is not required.
- PigeonPod is built from the upstream 1.30.1 source tag.
- Runtime/build dependencies are provided by Debian/YunoHost packages plus Node.js 22.
- Persistent application state is stored in YunoHost's application data directory.
- Installation is intended for the root of a dedicated domain because the current upstream Vite build uses root-relative asset paths.
- Built-in PigeonPod authentication remains enabled.

## Install for testing

Install the package from a local checkout:

```bash
sudo yunohost app install /path/to/pigeonpod_ynh
```

Use a dedicated domain or subdomain, for example `pigeon.example.org`.

## Upstream

https://github.com/aizhimou/pigeon-pod
