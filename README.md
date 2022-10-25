## Simple Docker config to run MySQL server

### How To Use:

1. Clone this repository into the directory where your server will be located.
2. Adjust settings in `docker-compose.yml` file. To change the server version replace `mysql:latest` with desired one, for example, `mysql:8.0.27`. Edit port if you already run another instance on `3306` port, for example, to run the server on `3307` port replace `3306:3306` with `3307:3306`.
3. Run the server using `docker-compose up -d` command (Docker has to be installed in the system).
4. To monitor server status use `docker ps` command.
5. To stop the server execute command `docker-compose down`.

### How To Connect:

Setup new connection in your favorite MySQL client with the settings:
```
Host: 127.0.0.1
Port: 3306 (or other if modified)
Username: root
Password: root (or other if modified)
```
