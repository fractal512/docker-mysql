## Simple Docker config to run MySQL server

### How To Use:

1. Clone this repository into the directory where your server will be located.
2. Adjust settings in `docker-compose.yml` file. To change the server version replace `mysql:latest` with desired one, for example, `mysql:8.0.27`. Edit port if you already run another instance on `3306` port, for example, to run the server on `3307` port replace `3306:3306` with `3307:3306`.
3. Run the server using `docker-compose up -d` command (Docker must be installed in the system).
4. To monitor server status use `docker ps` command.
5. To stop the server execute command `docker-compose down`.

### How To Connect:

Setup new connection in your favorite MySQL client with the following settings:
```
Host: 127.0.0.1
Port: 3306 (or other if modified)
Username: root
Password: root (or other if modified)
```

### Fixing Issues:

#### Memory allocation error

##### Error:

```
SQLSTATE[HY001]: Memory allocation error: 1038 Out of sort memory, consider increasing server sort buffer size
```

##### Solution:

Add these lines into `mysql` service section of the `docker-compose.yml` file to increase the sort buffer size to 1 Gb (1024 * 1024 * 1024 = 1073741824 bytes = 1 Gb, adjust if needed):
```
command:
  - --sort_buffer_size=1073741824
```

#### Incorrect time

##### Solution:

Add this line under `command` section of the `docker-compose.yml` file to change the time zone (for example: set Europe/Helsinki to change the timezone to +02:00 hours):
```
- --default-time-zone=Europe/Helsinki
```
