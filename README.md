# Dockerfile for [Cloudlog](http://www.cloudlog.co.uk)

Take note, the docker compose script is an example script.

If you want to use this in production, you use this behind an ssl enabled proxy, like nginx, caddy, ha-proxy,...

By default, the webpage will listen on port 8089 (using http), as this is a non-privileged port.

## running
### docker compose
Copy docker.app.sample.env to docker.app.env and edit where needed.

Variable `WEB_BASE_URL` should point to the URL that you will use in the browser.

Variable `CALLBOOK` instructs which remote callbook to use for user data look-up.

Variable `USE_FULLNAME` instructs that remote callbook data retrieval to pull the full name of the other remote station. This might be incompatible with GDPR, so use as you wish.

Copy docker.db.sample.env to docker.db.env and change the passwords before running the first time, to make sure your setup is secure.

The ".storage" directory will be made in the same folder automatically. It will be hidden.

to start: `docker compose up -d`  
to stop: `docker compose down`  
to update: `docker compose down && docker image prune -a && docker compose up -d`
