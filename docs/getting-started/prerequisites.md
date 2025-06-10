facileManager (fM) and its modules have two parts -- the server and the client(s). The server is where the web interface runs from and holds all of the information. The client (or agent) is installed on the systems to interact with the server.

!!! note
    It is **_not_** required to host the MySQL database on the same server as the web interface.

## facileManager server

### Web server

Since the facileManager server interface is web-based, you'll need a working web server of your choice (i.e. Apache, nginx, lighttpd, etc.) with mod_rewrite.so (or equivalent) enabled.

### PHP

- PHP 7.3.0+ with MySQL support

### Database

facileManager stores all of the information in a database and only supports MySQL-compatible databases.

- MySQL 5.0 or newer
- MariaDB 5.0 or newer

Required MySQL user privileges on the database include

    SELECT, INSERT, UPDATE, DELETE, CREATE, ALTER, DROP, LOCK TABLES

!!! example
    ``` mysql
    CREATE DATABASE `facileManager`;
    CREATE USER 'fm'@'localhost' IDENTIFIED BY 'password';
    GRANT ALL ON `facileManager`.* TO 'fm'@'localhost';
    FLUSH PRIVILEGES;
    ```

### Web browser

To use facileManager you need a web browser with cookies and JavaScript enabled.

[Minimum browser versions](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/light-dark#browser_compatibility)

!!! note
    Internet Explorer is not supported - it's too tiresome.

## facileManager client (all modules)

The facileManager client app is PHP-based (PHP 5.0 or newer).

Network connectivity needs to be allowed between the server and clients.

| Source | Destination | Service | Note |
|--------|-------------|---------|------|
| Client | fM Server | http/https | The client gets its configuration via HTTP GET & POST requests to the fM server |
| fM Server | Client | ICMP Echo Request (Ping) | fM uses ICMP to ensure the clients are reachable. |
| fM Server | Client | ssh | This is only required if ssh is selected for the [update method](basic-install.md#client-update-method). |
| fM Server | Client | http/https | This is only required if http/https is selected for the [update method](basic-install.md#client-update-method). |

If you choose to have your client get updates from the server via http(s), you need:

- A running web server if using http(s) update methods
    - The install script supports the following web servers:
        - httpd
        - lighttpd
        - nginx

## Additional Module-Specific Prerequisites

In addition to the fM client prerequisites, some modules have their own unique requirements.

### fmDHCP

- ISC DHCP

!!! note
    ISC KEA is not yet supported.

### fmDNS

- ISC BIND 9.3 or later

--8<--
footer.md
--8<--
