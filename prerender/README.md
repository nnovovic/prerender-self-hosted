# Prerender Docker

Lightweight Prerender container built on Alpine Linux with Node and Headless Chromium.

- [Prerender](https://github.com/prerender/prerender) 5.20.2
- [Chromium](https://github.com/chromium/chromium) 111.0.5563.146
- [Node](https://github.com/nodejs/node) 16.19.1

## Requirements

- [Docker](https://www.docker.com/)

## Usage

Pull and run the image:

```
docker pull nnovovic/prerender
docker run -p 3000:3000 nnovovic/prerender
```
Prerender will now be running on http://localhost:3000. Try the container out with curl:

```
curl http://localhost:3000/render?url=https://www.example.com/
```


## Prerender plugins

A few default plugins have been activated by default (see `server.js`):
- https://github.com/prerender/prerender/blob/master/lib/plugins/browserForceRestart.js
- https://github.com/prerender/prerender/blob/master/lib/plugins/addMetaTags.js
- https://github.com/prerender/prerender/blob/master/lib/plugins/removeScriptTags.js
- https://github.com/prerender/prerender/blob/master/lib/plugins/httpHeaders.js

## Prerender documentation

Check out the official Prerender documentation: https://github.com/prerender/prerender
