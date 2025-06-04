## fmDNS Settings
There are several settings available to set at **_Settings → fmDNS_**.

The fmDNS _Manage Settings_ or _Super Admin_ permission is required to change settings.

### Enable named Checks
>Default: `disabled`

With named checks enabled, before any server configuration or zone reload occurs, fmDNS will parse through the configuration and run `named-checkconf` and/or `named-checkzone` against it.  If the configuration has no errors then it will be deployed to the DNS servers. Otherwise, error messages from the two utilities will be displayed and deployment will stop.

This does require the two utilities to be installed on the web server and a sudoers entry added allowing the web server user to run them.
=== "Debian-based"

    ```
    sudo apt install bind9
    ```

=== "RedHat-based"

    ```
    sudo yum install bind9
    ```

!!! note
    The **fmDNS Settings** page will show what the sudoers file entry should look like.


### Purge Configuration Files
>Default: `disabled`

When enabled, configuration files will be deleted on the DNS servers before building the server config. This can be handy if you want to remove unused files.

### Use Defined Keys with rndc
>Default: `disabled`

Use keys defined in named.conf.keys with rndc actions (each server can override this).

### Zone Filename Format
>Default: `db.{ZONENAME}.hosts`

The filename structure for the zone files. `{ZONENAME}` will be replaced with the name of the zone.

### Create Reverse Zones Automatically
>Default: `disabled`

While creating A records and choosing to create the associated PTR record, reverse zones can be automatically created if they are missing.

### Use DNAME Resource Records for Clones
>Default: `enabled`

When creating cloned zones, use the DNAME resource record rather than a full clone (when available).

### Sort Zone Names Hierarchically
>Default: `disabled`

Sort zone names with a hierarchy to group sub-zones together.

For example:
```
domain.com
bar.domain.com
foo.bar.domain.com
```

### Default DNSSEC Signature Expiry
>Default: `30`

Define the number of days the DNSSEC signatures should be valid for (each zone can override this).

### Define URL RR Web Servers
>Default: `none`

This feature will enable the fmDNS URL resource record which allows DNS records to redirect the user to a URL. For example:

`foo.bar.com  IN  URL  http://www.foobar.com/some/landing/page.html`

List the (public) IP addresses or hostnames the URL RRs should resolve to in order to handle the web redirects (semi-colon or comma delimited).