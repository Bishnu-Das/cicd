This repository contains Dockerfiles and docker-compose configurations for running the application.

Development
-----------

- Build and start services in development mode (live-reload):

```cmd
cd docker
docker compose -f compose.development.yaml up --build
```

This uses `Dockerfile.dev` files and mounts the source into the containers so changes are reflected immediately.

Production
----------

- Build and start production images:

```cmd
cd docker
docker compose -f compose.production.yaml up --build -d
```

Notes
-----
- Backend listens on port `3000` and gateway on `8080` (served on host `80` in production compose).
- MongoDB data is persisted to a Docker volume named `mongo-data`.
- If you use Windows `cmd.exe`, run the commands from project root in a normal shell.
