A [nextcloud server](https://github.com/nextcloud/server) docker-compose secured with Caddy https proxy and storing data on S3

# Features
- Secure (HTTPS) nextcloud connection via Caddy reverse proxy
- Automatic SSL certificate retrieval and renewal via Caddy
- nextcloud data stored on S3 (or compatiable service)

# Prerequisites
- docker and docker-compose
- A domain name (e.g. nextcloud.yourdomain.com)
- An Amazon S3 (or compatible) storage (optional)

# Steps
1. Clone this repo
2. Modify caddy/Caddyfile and replace nextcloud.mydomain.com with your own domain
3. Modify docker-compose.yml 
    - replace NEXTCLOUD_TRUSTED_DOMAINS with your own domain
    - replace S3_BUCKET, S3_HOST, S3_REGION, and S3_USEPATH_STYLE with your own setting; delete them if you're not storing nextcloud data to S3.
4. Modify nextcloud.env and replace the necessary admin user name, admin password, and, optionally, S3 key and S3 secret.
5. Start the server with command `docker-compose up -d` and visit https://nextcloud.yourdomain.com on your browser.

# References
- See [nextcloud/docker](https://github.com/nextcloud/docker) for more nextcloud server settings. For example, use a database server to replace sqlite.
- See [Caddyfile document](https://caddyserver.com/docs/caddyfile) for more options you can use in the Caddyfile.
