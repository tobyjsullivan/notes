# Docker

## Build a docker image

From within the directory containing your `Dockerfile`:

```sh
docker build -t my-image .
```

## Tag the current image

```sh
docker tage my-image tobyjsullivan/my-image:v1.0
```

## Push to Docker Hub

```sh
docker push tobyjsullivan/my-image:v1.0
```
