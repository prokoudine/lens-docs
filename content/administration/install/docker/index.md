---
title: Install with Docker
weight: 1
type: docs
sidebar:
  open: true
---

## Installation

To install Ondsel Lens with `docker-composer`, follow these steps:

{{% steps %}}

### Install prerequisites

You only need to install Docker. Follow the [official guide](https://docs.docker.com/engine/install/).

### Clone the Lens repository with submodules

```bash
git clone https://github.com/FreeCAD/Ondsel-Server.git Lens
cd Lens
git submodule update --init --recursive
```

### Create environment file

```bash
cp env.example .env
# or for using AWS S3 for storage:
cp env.with-aws.example .env
```

### Start the server

```bash
# With analytics (recommended):
docker-compose --profile matomo-enabled up --build -d

# Without analytics:
docker-compose up --build -d

# Rebuild the frontend on env change:
docker-compose build --no-cache frontend

# For development:
docker-compose -f docker-compose.dev.yml --profile matomo-enabled up --build -d

# To use prebuild docker images
docker-compose -f docker-compose.prebuilds.yml --profile matomo-enabled up --build -d
```

{{% /steps %}}

That's it! The application should now be running at `http://localhost:3000`.

## Default credentials

### Matomo analytics

- URL: http://localhost:7000
- Username: `admin`
- Email: `admin@local.test`
- Password: `admin@local.test`

### Frontend application

- URL: http://localhost:3000
- Email: `admin@local.test`
- Password: `admin@local.test`

These credentials can be customized using environment variables in the `.env` file.

{{< callout type="info" >}} 
  For production environments, it's strongly recommended to change these default credentials using environment variables.
{{< /callout >}}
