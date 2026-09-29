PigeonPod is a self-hosted application for turning YouTube and Bilibili sources into podcast-friendly RSS feeds. It can download audio or video, retain media locally, backfill history, and expose protected RSS feeds for podcast clients.

This YunoHost package builds the upstream PigeonPod 1.30.0 release from source and runs the resulting Java application as a dedicated system service. Application data lives in YunoHost's persistent application data directory, including the SQLite database, downloaded media, cover files, and PigeonPod-managed yt-dlp runtime files.

## Compatibility note

The upstream project currently recommends Docker for deployment, while its repository README also documents running the built JAR directly on Java 17+ with yt-dlp installed. This YunoHost package uses that native JAR route so it can integrate with YunoHost systemd and nginx without nesting Docker inside YunoHost.

## Installation model

The current upstream frontend is built with Vite using root-relative asset URLs. This package therefore installs PigeonPod at the root of a dedicated YunoHost domain rather than under an arbitrary URL path. Use a dedicated subdomain such as `pigeon.example.org` or a dedicated domain.

## First login

The upstream self-hosting documentation currently documents the default account as:

- Username: `root`
- Password: `Root@123`

Change the password immediately after the first login.

## YouTube configuration

YouTube workflows require a YouTube Data API v3 key. Configure it from PigeonPod's settings after installation.

## RSS / podcast clients

Only downloaded/completed media is exposed through RSS. PigeonPod can produce audio and video feeds, and feed URLs can be used by clients that support authenticated podcast feeds.

## Storage

Downloaded media is stored under the app data directory rather than the web application directory. Because media can grow to many gigabytes, monitor available disk space separately from the base package size.
