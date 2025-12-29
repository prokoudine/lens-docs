---
title: Versions on Lens
weight: 1
type: docs
sidebar:
  open: false
---

Ondsel Lens has a linear history of revisions. Every version has a timestamp and a commit message that describes the change (commit messages are currently only visible in the web app).

Versions of files are stored as new files and are referenced in the database using hashes.

Additionally, one version is set as the active one. It's the version that is opened by default in both the addon and the web app.

By default, the latest version is set as the active one. However, you can override that and [set any version as the active one](../set-active-version).