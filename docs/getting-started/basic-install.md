## Server Installation

1. Move the contents of the server directory to your document root.
   (ie /var/www/html/facileManager/)
2. Point your web browser to http://example.com/facileManager/ or your
   virtualhost if you set one up (ie http://facileManager.example.com).
3. Follow the installation wizard to setup your database and admin user.

### Additional Steps (OS-based)

The following steps need to be performed on vanilla installations of certain 
operating systems to allow .htaccess files to be used.

=== "Debian-based"
    Edit /etc/apache2/sites-enabled/default and change `AllowOverride None` to `AllowOverride All` under `<directory /var/www/>` and reload apache.

=== "RHEL7/CentOS7"
    Edit /etc/httpd/conf/httpd.conf and change `AllowOverride None` to `AllowOverride All` under `<Directory /var/www/html>` and reload apache.

## Client Installation

Install PHP and the required modules.
=== "Debian-based"

    ```
    sudo apt install php-cli php-curl
    ```

=== "RedHat-based"

    ```
    sudo yum install php-cli php-curl
    ```

Install optional modules.
=== "Debian-based"

    ```
    sudo apt install php-openssl php-zlib
    ```

=== "RedHat-based"

    ```
    sudo yum install php-openssl php-zlib
    ```

Move the contents of the client directory to /usr/local/ on your client
   servers to manage. (Note: client files from the core (or complete) package
   are also required.)
```
sudo mv facileManager/client/facileManager /usr/local/
```

For each module you wish to use, run the following on each client to complete
   the installation.
```
sudo php /usr/local/facileManager/<module_name>/client.php install
```

### Prompts
The installation process invoked will prompt for three main items:

- facileManager server URL
- Client serial number
- Client update method

#### Client serial number
This number is a unique identifier for each client. In most cases you can accept the default to automatically generate a unique client serial number.

#### Client update method
How the fM server can communicate with the client to initiate configuration updates can be done via cron, ssh, or http(s).

`cron`
>Specify this option to have the client check periodically (default every 5 minutes) for any configuration updates.

`ssh`
>Specify this option to allow the fM server to SSH to the client and invoke `client.php` to apply pending changes. This option will allow for immediate changes from fM.

>When this update method is selected, the configured SSH user and public key (from **_Settings → General_**) will be installed on the client.

`http(s)`
>Specify this option to allow the fM server to invoke an HTTP POST to the client and invoke `client.php` to apply pending changes. This option will allow for immediate changes from fM.

### Installer options
The installer does have options that can be passed in the [`-o|options`](../admin/client.php.md#-o-options) parameter with the [client](../admin/client.php.md) which will skip the prompts.  This can be handy for unattended installations.

!!! note "From the client.php help file"
    (invoked with `php /usr/local/facileManager/<module_name>/client.php help`):

    ```
    -o|options    Installation options comma-delimited to avoid prompts
                      Valid options: 
                            FMHOST    fM host url
                            SERIALNO  Server serial number (or 0 to auto-generate)
                            method    Update method to use (cron, ssh, http)
                      Examples:
                            install -o FMHOST=https://example.com/fm/,method=cron
                            install options FMHOST=fm.example.com,SERIALNO=0,method=ssh
    ```

--8<--
footer.md
--8<--
