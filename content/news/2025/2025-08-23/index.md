---
title: "Documentation moved"
date: 2025-08-16
authors:
  - name: Aleksandr Prokudin
    link: https://github.com/prokoudine
    image: https://avatars.githubusercontent.com/u/57467?v=4
tags:
  - Release
type: blog
---

The original documentation written in Docusaurus has been moved to Hugo and a Git repository that belongs to the FreeCAD organization.

<!--more-->

Now that Ondsel is gone, it's only a matter of time when the website becomes unavailable, and so does the [documentation](https://web.archive.org/web/20250319191605/http://ondsel.com/docs/) I wrote in 2024. So I took some time and ported it to [Hugo](https://gohugo.io/) using the great [Hextra](https://imfing.github.io/hextra/) theme.

This is mainly a port of existing content with use of some Hextra-specific markup to make the documentation pretty. Future work will likely include:

- Documentation restructure and finalization
- Documentation for on-prem Ondsel Lens deployment
- Documentation for the Lens add-on

Just like all Lens-related code, the repository is managed by the FreeCAD organization. You can [find it here](https://github.com/FreeCAD/lens-docs).