## fmWifi Parameters
fmWifi has additional parameters that can be passed to `client.php` that are specific to this module.

#### block=`<MAC Address>`
This parameter will block the specified MAC address from connecting to the access point.

!!! example
    ```
    sudo php client.php block=00:11:22:aa:bb:cc
    ```

#### -e | ebtables
This parameter will block the specified MAC address from connecting to the access point using ebtables.

!!! example
    ```
    sudo php client.php block=00:11:22:aa:bb:cc -e
    ```

#### show-clients
This parameter will provide a list of connected clients.

!!! example
    ```
    sudo php client.php show-clients
    ```

#### status
This parameter will show the current status of the access point.

!!! example
    ```
    sudo php client.php status
    ```

#### status-all
This parameter will show the full status of the access point.

!!! example
    ```
    sudo php client.php status-all
    ```

#### -o `<(human|web)>`
This parameter will format the output either for `human`-readable or for `web`. This is to be used with `show-clients`, `status`, and `status-all`.

!!! example
    ```
    sudo php client.php status -o web
    ```
