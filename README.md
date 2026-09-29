# PigeonPod, packaged for YunoHost

Self-hosted RSS feeds from YouTube and Bilibili.

This package targets PigeonPod 1.30.0 and follows the YunoHost packaging v2.1 template structure.

## Packaging choices

- Native YunoHost service; Docker is not required.
- PigeonPod is built from the upstream 1.30.0 source tag.
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

## Notes

The package intentionally omits a source SHA-256 checksum because the upstream release currently does not publish a checksum file. Pin the checksum before submitting the package for inclusion in the official YunoHost catalog.

This package has not been installed against a live YunoHost server in the build environment. Run the official YunoHost package CI/checks and an install/upgrade/backup/restore cycle before production use.
