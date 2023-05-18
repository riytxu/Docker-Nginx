# Docker-compose-Nginx-Reverse-Proxy-II

## Tutorial

[Docker compose : Nginx reverse proxy with multiple containers](http://www.bogotobogo.com/DevOps/Docker/Docker-Compose-Nginx-Reverse-Proxy-Multiple-Containers.php)

**p.s. by first need start project container for create docker networks**

## Command for docker certbor

**Dry run create certificate:**

- `docker compose -f ./docker-compose_ssl.yml run --rm certbot certonly --webroot --webroot-path /var/www/certbot/ --dry-run -d site1.example.com -d www.site1.example.com`

**Create certificate:**

- `docker compose -f ./docker-compose_ssl.yml run --rm certbot certonly --webroot -w /var/www/certbot --force-renewal --email email-name -d site1.example.com -d www.site1.example.com --agree-tos`  
  **email-name** - email adress

**Add new domain names to active certificate:**

- `docker compose -f ./docker-compose_ssl.yml run --rm certbot certonly --webroot -w /var/www/certbot --expand -d site1.example.com -d www.site1.example.com -d new-domain.com`  
  **new-domain.com** - new domain name

**Dry run renew certificate:**

- `docker compose -f ./docker-compose_ssl.yml run --rm certbot renew --dry-run`

**Renew certificate:**

- `docker compose -f ./docker-compose_ssl.yml run --rm certbot renew`
