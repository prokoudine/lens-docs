---
title: Sync status
weight: 1
type: docs
sidebar:
  open: false
---

All files available in the Ondsel Lens addon for FreeCAD have one of the following five statuses:

- **Untracked**: The file is in the local cache folder, but Ondsel Lens does not track it.
- **Not downloaded**: The file is only available on Lens, it has never been downloaded and automatically saved to the local cache folder.
- **Synced**: The local version is in sync with the Ondsel Lens version.
- **Local copy newer**: The local version is newer than the server one, i.e. you saved the file, but haven't uploaded a new revision yet.
- **Lens copy newer**: The server version is newer than the local one. Someone uploaded a new revision of the file to Ondsel Lens, but you haven't downloaded it yet.