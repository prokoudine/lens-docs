---
title: Install manually
weight: 2
type: docs
sidebar:
  open: true
---

## Installation

To install Ondsel Lens manually, follow these steps:

{{% steps %}}

### Install prerequisites

- [Install MongoDB](https://www.mongodb.com/docs/manual/installation/)
- [Install NodeJS](https://nodejs.org/en/download)
- [Install Docker](https://docs.docker.com/engine/install/) (needed for FC-Worker)

### Clone the repository with submodules

```bash
git clone https://github.com/FreeCAD/Ondsel-Server.git Lens
cd Lens
git submodule update --init --recursive
```

### Run MongoDB

First, start the MongoDB service:

```bash
systemctl start mongodb
```

If necessary, remove the old database, `od-backend-db`, e.g., using MongoDB Compass.

### Run the frontend

Go to the `frontend` directory and rename `env.example` to `.env` (Or export variables). After that, install frontend dependencies and run the server:

```bash
$ cd frontend
$ mv env.example .env
$ set -a; . ./.env; set +a
$ npm ci
$ npm run dev
```

To run from Docker, recompile with:

```bash
sudo docker build -t frontend .
```

and run (or re-run) with:

```bash
sudo docker run --env-file .env -p 80:80 --rm --name frontend frontend:latest
```

If it is required to make the server accessible on the local network, change
the environment variable below in `.env` and use the hostname or IP address
where the backend is available.

```bash
VITE_APP_API_URL=http://<host-or-ip-of-backend>:3030/
```

Then run the frontend with:

```bash
npm run dev -- --host 0.0.0.0
```

### Run the backend

- Go to the `backend` directory, rename `env.example` or `env.with-aws.example` (for using AWS S3 for storage) to `.env` (or export variables), and install backend dependencies:

```bash
$ cd backend
$ mv env.example .env # or `mv env.with-aws.example .env` for using AWS S3 for storage
$ set -a; . ./.env; set +a
$ npm ci
```

### Run migrations

When running the backend for the first time, you need to run migrations to set up the database. These are automatically handled by `entry.sh` when using docker-compose, but must be run manually otherwise.

```bash
npm run migration addInitialTosPp                # Creates placeholder Terms of Service and Privacy Policy
npm run migration createDefaultSiteConfig        # Creates default site configuration for branding
npm run migration addDefaultAdminUser            # Creates admin user (email: admin@local.test, password: admin@local.test)
npm run migration createDefaultPublisherEntries  # Creates publisher entries for software releases page
```

### Run FC-Worker

The FC-Worker is a submodule and has its own [repository](https://github.com/FreeCAD/FC-Worker).

Go to the `FC-Worker` directory, build the docker image, and then run the docker image:

```bash
$ cd FC-Worker
$ docker-compose build
$ docker-compose up -d`
```

Check if it works:

```bash
curl -v http://127.0.0.1:9000/2015-03-31/functions/function/invocations -X POST -H "Content-Type: application/json" -d '{"command":"<your-health-check-string>"}'
```

### Start the server

Finally, run the server:

```bash
npm run dev
```

{{% /steps %}}

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