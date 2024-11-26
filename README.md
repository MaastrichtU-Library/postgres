# postgres
**Postgres** image mirror from https://hub.docker.com/_/postgres

cf. Github repository: https://github.com/docker-library/docs/tree/master/postgres

Hosted on [GitHub Container Registry](https://github.com/MaastrichtU-Library/postgres) ([ghcr.io](https://ghcr.io)) to avoid DockerHub pull limitations, and easily deploy on clusters (such as Kubernetes).


## Automatically updated

[![Publish Docker image](https://github.com/MaastrichtU-Library/postgres/workflows/Publish%20Docker%20image/badge.svg)](https://github.com/MaastrichtU-Library/postgres/actions)

The image on [ghcr.io](https://ghcr.io) is automatically updated every week (Monday at 3:00 GMT+1) by a GitHub Actions workflow to match the `latest` tag of [Postgres](https://hub.docker.com/_/postgres) 

## Run

```bash
docker run -it -v $(pwd):/root ghcr.io/maastrichtu-library/postgres:latest
```

In the container:

* User, with `sudo` privileges: `root`
* Workspace path: `/root`

Set entrypoint to `tail -f /dev/null` to keep it hanging as a service.

```bash
docker run -it --entrypoint tail -v $(pwd):/root ghcr.io/maastrichtu-library/postgres:latest -f /dev/null
```

## Build

Feel free to edit the `Dockerfile` to install additional packages in the image.

```bash
docker build -t ghcr.io/maastrichtu-library/postgres:latest .
```

## Push

```bash
docker push ghcr.io/maastrichtu-library/postgres:latest
```

