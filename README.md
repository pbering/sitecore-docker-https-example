# Sitecore Docker HTTPS example using reverse proxy

Demonstrates how to configure a reverse proxy ([Traefik](https://github.com/containous/traefik/) in this case) to handle SSL with a auto generated self-signed certificate on the frontend and proxy traffic to backend services using HTTP.

## Usage

Add (or edit) environment variables used so they match what Windows build your are running and which Docker repository your Sitecore images is in. See [the .env file](.env).

```text
    docker-compose up --build
```

## Notes

1. Custom `traefik` image is needed due to an error in traefik that requires containers to run in process isolation mode and official traefik images is not supplied for Windows 1903 and 1909.
    1. This issue may be resolved in traefik v2 but there is *another* issue with that official images that keeps the container from starting :)
