## Simple Docker config to run MySQL server

### How To Use

1. Clone this repository into directory where your server will be located.
2. Adjust settings in `docker-compose.yml` file. To change server version replace `mysql:latest` to desired one, for example `mysql:8.0.27`. Edit port if you already run another instance on `3306` port, for example to run server on `3307` port replace `3306:3306` with `3307:3306`.
3. Run server using `docker-compose up -d` command.
4. To monitor server status use `docker ps` command.
5. To stop server execute command `docker-compose down`.
