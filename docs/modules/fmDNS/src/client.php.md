## fmDNS Parameters
fmDNS has additional parameters that can be passed to `client.php` that are specific to this module.

#### dump-cache
This parameter will dump the DNS cache via `rndc dumpdb -cache` and display the contents of the `dump-file` file (if it's configured in the `named.conf.* `files).

!!! example
    ```
    sudo php client.php dump-cache
    ```

#### clear-cache
This parameter clears the DNS cache via `rndc flush`.

!!! example
    ```
    sudo php client.php clear-cache
    ```

#### -D <zone_name> | -D -f /path/to/zones.conf
This parameter dumps zone data to `STDOUT` and in required by `dump-zone`. It will dump data for a single zone by passing `-D <zone_name>` or it will dump data for multiple zones by passing `-f /path/to/zones.conf`.

!!! example
    ```
    sudo php client.php dump-zone -D test-domain.com
    sudo php client.php dump-zone -f /etc/bind/zones/master/zones.conf
    ```

#### -z | zones
Instead of building all configuration files for bind (i.e. using `buildconf`), only the zone data will be built and reloaded using this parameter.

!!! example
    ```
    sudo php client.php zones
    ```

#### id=`<ID>`
Building and reloading the zone data for a single zone can be achieved by passing the zone ID with `zones`.

!!! example
    ```
    sudo php client.php zones id=3
    ```

#### install url-only
In order to use [URL resource records](./settings.md#define-url-rr-web-servers), you may want to install the client component on a server that is not a DNS server. This parameter will install the client app for URL RR use only.

!!! example
    ```
    sudo php client.php install url-only
    ```

#### enable url
An fmDNS client that has already been installed can get enabled to serve [URL resource records](./settings.md#define-url-rr-web-servers).

!!! example
    ```
    sudo php client.php enable url
    ```

#### API Usage
The API can be invoked with the client app to manage records instead of using the web interface. While not as robust as the web interface, there are a number of supported parameters:

```
    setHost                  Invokes the API functionality
    action=XX                Defines API action to take on a record (add, update, delete)
    type=XX                  Defines the RR type (A, AAAA, CNAME, DNAME, MX, NS, PTR, TXT)
    name=XX                  Defines the name of the RR
    value=XX                 Defines the value of the RR
    ttl=XX                   Defines the TTL of the RR
    priority=XX              Defines the priority of the RR (MX only)
    append=XX                Defines whether to append the domain or not (yes, no)
    comment=XX               Defines the record comment
    status=XX                Defines the record status (active, disabled)
    newname=XX               Defines the new record name (when action=update)
    newvalue=XX              Defines the new record value (when action=update)
    reload=XX                Defines whether to reload the zone or not (yes, no)
```

!!! note
    `setHost` is a required parameter which invokes the API functionality.

!!! example
    ```
    php client.php setHost id=36 action=add name=www value=1.2.3.4 type=A ttl=500 createPTR=yes comment="some comment" status=active`
    php client.php setHost id=36 action=update name="@" newvalue=10.0.0.2 type=A reload=yes
    ```
