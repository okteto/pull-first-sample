# Pull first sample

A sample repo to pull dev images instead of building by default

## Build section

The build section in this sample defaults to building images based on the value of the `BASE_IMAGE` build arg.
This behavior is defined in the [Dockerfile.okteto](Dockerfile.okteto) file.

For example, `BASE_IMAGE` could refer to your images built on CI for every commit.

## .env file

The `.env` file defines the default values for the dockerfiles of every service, for example:

```
OKTETO_API_DOCKERFILE=Dockerfile
OKTETO_FRONTEND_DOCKERFILE=Dockerfile
```

This means, if I define these environment variables, `okteto deploy --build` will built my images on the fly. This is useful to build my images with my local changes while I am developing.

If `.env` is not commited to the git repo, deploying the repo from the UI will use the default images built on CI.




