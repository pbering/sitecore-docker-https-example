# Sitecore Docker HTTPS example using reverse proxy

Demonstrates how to configure a reverse proxy ([Traefik](https://github.com/containous/traefik/) in this case) to handle SSL with a auto generated self-signed certificate on the frontend and proxy traffic to backend services using HTTP.

## Usage

1. Add (or edit) environment variables used so they match what Windows build your are running and which registry you are using. See [the .env file](.env).
1. Add `solr.sitecore-https.local` and `cm.sitecore-https.local` to your HOSTS file.
1. Run `docker-compose up`

> IMPORTANT: The traefik service in docker-compose.yml is configured to use port 80 and 443, so if you got anything running using the same ports for example IIS, you need to shut it down (or stop the sites) or change the ports.
