---
title: Ondsel Lens Documentation
toc: true
---

## What is Ondsel Lens?

Ondsel Lens is an online vaulting and product data management (PDM) service for mechanical engineers and industrial designers. Lens will help you collaborate and iterate on your product designs, as well as showcase and share your personal work.

This documentation covers the administration of your own Ondsel Lens instance, managing projects, and using the FreeCAD addon.

{{< cards cols="3" >}}
  {{< card link="administration" title="Administration" icon="server" >}}
  {{< card link="webapp" title="Web app" icon="globe-alt" >}}
  {{< card link="addon" title="Lens addon" icon="puzzle" >}}
{{< /cards >}}

<!--   {{< card link="about" title="About" icon="user" >}} -->

## What is Ondsel?

Ondsel was a company built around the free and open-source FreeCAD project. The company maintained three products: the Lens PDM, a FreeCAD flavour called Ondsel Engineering Service, and Lens Addon for connecting FreeCAD to Ondsel Lens.

The company shut down in November 2024 and transferred most of its intellectual property to the FreeCAD community.

## Where is the source code?

The Ondsel Lens ecosystem has the following components managed by the FreeCAD project on GitHub:

| Component | Licenses |
|-----------|----------|
| [Containerized headless FreeCAD runner](https://github.com/FreeCAD/FC-Worker) | LGPL 2.0+ |
| [Ondsel Lens web app](https://github.com/FreeCAD/Ondsel-Server) | AGPL 3.0+ |
| [Ondsel Lens addon for FreeCAD](https://github.com/FreeCAD/Ondsel-Lens-Addon) | Apache 2.0, CC-BY-SA 2.0, CC-BY-SA 4.0, CC0 1.0, LGPL 2.0+ |