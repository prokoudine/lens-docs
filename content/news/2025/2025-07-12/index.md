---
title: "Lens now supports on-prem deployment"
date: 2025-07-12
slug: lens-now-supports-on-prem-deployment
authors:
  - name: Aleksandr Prokudin
    link: https://github.com/prokoudine
    image: https://avatars.githubusercontent.com/u/57467?v=4
tags:
  - Release
type: blog
---

Amritpal Singh has finished the work on an FPA grant to make Ondsel Lens self-deployable.

<!--more-->

Originally, Ondsel Lens was designed to run on AWS Lambda and store models on S3. Ever since the code has been transferred to FreeCAD and made available under the terms of AGPL, this was no longer a great idea.

Thanks to an anonymous sponsor, The FreeCAD Project Association got a donation of 40K Euro towards improving Lens for the general public (called Ondsel Onward Fund). Naturally, the first grant was dedicated to decoupling Lens from AWS and making it run on-premises.

Here are the changes contributed by Amritpal:

- Container orchestration with Docker Compose
- Replacing AWS S3 with a local storage solution
- FC-Worker redesign
- Initial documentation on self-deployment