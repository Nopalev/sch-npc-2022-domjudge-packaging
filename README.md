# DOMjudge packaging repository

This repository contains packaging code for DOMjudge in various
subdirectories. Below some information on these.

## DOMjudge Docker containers

Under `docker` you find the sources for the Docker containers on
https://hub.docker.com/r/domjudge/. Under `docker-contributor` you
find the sources for building a Docker container to do development
on the DOMjudge sources from a git checkout. See the `README.md` files
in those respective directories for more details.

## How To Use

1. Clone this repository

2. Inside directory `docker`, run:

    ```bash
    cp .env.sample .env
    ```

    ```bash
    docker-compose -p alpro-domjudge up -d
    ```

3. Wait patiently

4. Once done, open http://localhost:8080/ on your browser

Note:

The initial passwords for the `admin` and `judgehost` users should be printed when starting the domserver, but if not, you can use the following commands to retrieve them:

```bash
docker exec -it domserver cat /opt/domjudge/domserver/etc/initial_admin_password.secret
docker exec -it domserver cat /opt/domjudge/domserver/etc/restapi.secret
```
