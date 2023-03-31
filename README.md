# Prerender self-hosted using Docker

This project is focused on providing an easy way to run a self-hosted [Prerender](https://github.com/prerender/prerender) service using Docker. 

By using Docker Compose, you can easily deploy and manage their Prerender service on your own server, while [NGINX](https://www.docker.com/) provides a high-performance web server and reverse proxy.


## Requirements

- [Docker](https://www.docker.com/)

## Project structure
- nginx - Configuration for NGINX
- prerender - prerender container built on Alpine Linux with Node and Headless Chromium
- docker-compose.yml 

## Deployment

1. Copy `nginx/examples/prerender.conf` to `deploy/nginx/sites-available` and edit it.
2. Run docker compose.
```
docker compose -d up
```
3. Navigate to the url defined in `server_name` in your nginx configuration file. For example:
```
curl http://prerender.test/https://website-to-render.com/test-page
```
## Cache

In `nginx/examples/prerender.conf` you can see an example configuration. You can modify it to match your needs.

### Bypass cache
Just add header `No-Cache` to your requests

### Ignored query args
We will ignore these query arguments in our `proxy_cache_key`
- utm_source
- utm_term
- utm_campaign
- utm_medium
- utm_content
- fbclid
- keyword
- gclid