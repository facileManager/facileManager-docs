Most modules make use of a client app, but some may not. The modules with a client will have a `client.php` file found in `/usr/local/facileManager/<module_name>/` and it will utilize core functionality found in facileManager-core. The purpose of the client app is to be an agent for the module in order to update the system configuration.

Here we will break down the parameters available to all client apps.

You can always invoke the client help file at the CLI:
```
php client.php help
```

## Core Parameters

#### -h | help
Invokes the client help file and exits.

!!! example
    ```
    php client.php help
    ```

#### -v | version
Print the client app version and exits.

!!! example
    ```
    php client.php version
    ```

#### -c | cron
If the client is setup to receive updates from the facileManager server via cron, this parameter will invoke the client to check for any pending configurations. This is also the parameter used to define the crontab job during [installation](../getting-started/basic-install.md#client-installation).

!!! example
    ```
    sudo php client.php cron
    ```

!!! note
    This parameter only works if the client is configured to receive updates via cron.

#### -b | buildconf
The client app exists to build the configuration for the system. Use this parameter to build the server configuration and associated files.

!!! example
    ```
    sudo php client.php buildconf
    ```

#### -d | debug
Sometimes your desired configuration may not get deployed to the client and enabling debug mode will provide more information which may help in troubleshooting.

!!! example
    ```
    sudo php client.php buildconf debug
    ```

#### -n | dryrun
Instead of applying the configuration on the client, this parameter will show you want will be applied without saving any files.

!!! example
    ```
    php client.php buildconf dryrun
    ```

#### -p | purge
There may be old configuration files (or files unmaintained by fM and its modules) that you want to delete.

!!! example
    ```
    sudo php client.php buildconf purge
    ```

#### -s | no-ssl
This parameter will force the client to communicate with the fM server via http only.

!!! example
    ```
    sudo php client.php buildconf no-ssl
    ```

#### no-sudoers
During the [client installation](../getting-started/basic-install.md#client-installation), use this parameter to prevent the necessary sudoers entry from being made. This might be useful if you maintain the sudoers files by other means.

!!! example
    ```
    sudo php client.php install no-sudoers
    ```

#### no-update
The client will send information to the server about itself (OS, OS version, client version, app version). This parameter will prevent the information from being sent and populating the database.

!!! example
    ```
    sudo php client.php install no-update
    ```

#### apitest
Use this parameter to test the API communication.

!!! example
    ```
    php client.php apitest
    ```

#### install
This parameter invokes the [client installer](../getting-started/basic-install.md#client-installation) which asks a series of questions to correctly configure the client.

!!! example
    ```
    sudo php client.php install
    ```

#### -o | options
This can only be used in conjuction with `install`. Instead of being prompted during installation, this parameter followed by the desired options will be passed to the installer.

>**Valid options:**
>
>| Option | Description |
>|--------|-------------|
>| `FMHOST` | fM host URL |
>| `SERIALNO` | Server serial number (or 0 to auto-generate) |
>| `method` | Update method to use (cron, ssh, http) |

!!! example
    ```
    sudo php client.php install -o FMHOST=https://example.com/fm/,method=cron
    sudo php client.php install options FMHOST=fm.example.com,SERIALNO=0,method=ssh
    ```

#### upgrade
This parameter will upgrade the client app to the latest available version.

!!! example
    ```
    sudo php client.php upgrade
    ```

#### reinstall
This parameter invokes the installer on a previously installed client.

!!! example
    ```
    sudo php client.php reinstall
    ```

---
--8<--
fmDHCP/src/client.php.md
--8<--

---
--8<--
fmDNS/src/client.php.md
--8<--

---
--8<--
fmWifi/src/client.php.md
--8<--
