# Server setup

1. Ensure docker & docker-compose are installed and working
2. Access via ssh and copy `Dockerfile`, `server/config.toml` and `server/docker-compose.yml` into a new directory
3. Set `default_token` in `config.toml`
4. Make any changes to `ports` in `docker-compose.yml` and add any services in `config.toml`
5. Run `docker-compose up --build -d` to start the server as a daemon

# Client setup

1. Ensure docker & docker-compose are installed and working
2. Access via ssh and copy `Dockerfile`, `client/config.toml` and `client/docker-compose.yml` into a new directory
3. Set `remote_addr` in `config.toml` to match the IP of the server
4. Set `default_token` in `config.toml` to match that set on the server
5. Add any services in `config.toml`

**Note:** Because `network_mode` is set to `host` in `docker-compose.yml`, `127.0.0.1` can be used in `config.toml` when setting `local_addr` for services

# Useful comands

1. Run `docker logs -f <container_name>` to view logs
2. Run `docker exec -ti <container-name> /bin/sh` to access a shell
3. Run `docker-compose down` to stop
4. Run `docker-compose --build --force-recreate` to rebuild the container from scratch
