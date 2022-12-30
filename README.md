# README
DHH:

> Add Docker files by default to new apps: Dockerfile, .dockerignore, bin/docker-entrypoint. These files can be skipped with --skip-docker. They're intended as a starting point for a production deploy of the application. Not intended for development (see [Docked Rails](https://github.com/rails/docked) for that).

> Example:

> ```bash
> docker build -t app .
> docker volume create app-storage
> docker run --rm -it -v app-storage:/rails/storage -p 3000:3000 --env RAILS_MASTER_KEY=<see config/master.key> app
> ```
> You can also start a console or a runner from this image:
> ```bash
> docker run --rm -it -v app-storage:/rails/storage --env RAILS_MASTER_KEY=<see config/master.key> app console
> ```
> To create a multi-platform image on Apple Silicon to deploy on AMD or Intel and push to Docker Hub for user/app:
> ```bash
> docker login -u <user>
> docker buildx create --use
> docker buildx build --push --platform=linux/amd64,linux/arm64 -t <user/image> .
> ```
