## fmDHCP
There are a few settings available at **_Settings → fmDHCP_**.

_The fmDHCP **Manage Settings** or **Super Admin** permission is required to change settings._

### Enable dhcpd Checks
>Default: `disabled`

With dhcpd checks enabled, before any server configuration occurs, fmDHCP will parse through the configuration and run `dhcpd -t -cf` against it.  If the configuration has no errors then it will be deployed to the DHCP servers. Otherwise, error messages from the two utilities will be displayed and deployment will stop.

This does require the utility to be installed on the web server and a sudoers entry added allowing the web server user to run it.
=== "Debian-based"

    ```
    sudo apt install dhcpd
    ```

=== "RedHat-based"

    ```
    sudo yum install dhcpd
    ```

!!! note
    The **fmDHCP Settings** page will show what the sudoers file entry should look like.