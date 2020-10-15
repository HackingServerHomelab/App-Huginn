# App-Huginn

## First Time Prerequisites

1. `rm ./Data/postgresql/.gitkeep`

## Running the Containers

1. Run `./Config/gen_certs.sh` to generate the SSL certificates (alternatively,
   add custom certs to the private folder)
2. Update the `server_name` in [nginx.conf](./Config/nginx.conf)
3. Update the following mounts in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/postgresql:/var/lib/postgresql/data`
4. Update the following environment variables in [docker-compose.yml](./Docker/docker-compose.yml)
    * `POSTGRES_PASSWORD: "password" # CHANGEME`
    * `HUGINN_DATABASE_PASSWORD: "password" # CHANGEME`
    * `EMAIL_FROM_ADDRESS: "huginn@example.com" # CHANGEME`
    * `SMTP_DOMAIN: "example.com" # CHANGEME`
    * `SMTP_USER_NAME: "huginn" # CHANGEME`
    * `SMTP_PASSWORD: "password" # CHANGEME`
    * `SMTP_SERVER: "mail.example.com" # CHANGEME`
    * `SMTP_PORT: "25" # CHANGEME`
    * `SMTP_AUTHENTICATION: "plain" # CHANGEME`
    * `SMTP_ENABLE_STARTTLS_AUTO: "true" # CHANGEME`
    * `SMTP_SSL: "false" # CHANGEME`
3. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## First Time Setup

1. Visit <https://your-ip>
2. Log in with the default credentials `admin:password`
3. Ensure you uncomment the `SEED_DB` environment variable in the docker-compose
   file



