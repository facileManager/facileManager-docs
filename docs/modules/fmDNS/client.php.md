--8<--
client.php.md
--8<--

### fmDNS Parameters
fmDNS has additional parameters that can be passed to `client.php` that are specific to this module.

```
   -D                         Name of zone to dump (required by dump-zone)
   -f                         Filename hosting the zone data (required by dump-zone)
   -z|zones                   Build all associated zone files
     dump-cache               Dump the DNS cache
     dump-zone                Dump the specified zone data to STDOUT
     clear-cache              Clear the DNS cache
     id=XX                    Specify the individual DomainID to build and reload
	 
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

     install url-only         Installs the client app to be a URL RR web server only
     enable url               Enables the URL RR web server support on a previous installation
```

#### Dump DNS Cache
>Example: `sudo php client.php dump-cache`

This parameter will dump the DNS cache via `rndc dumpdb -cache` and display the contents of the `dump-file` file (if it's configured if the `named.conf.* `files).

#### Clear DNS Cache
>Example: `sudo php client.php clear-cache`

This parameter clears the DNS cache via `rndc flush`.

#### Dump Zone Data
>Examples:
>>```
>>sudo php client.php dump-zone -D test-domain.com
>>sudo php client.php dump-zone -f /etc/bind/zones/master/zones.conf
>>```

This parameter dumps zone data to `STDOUT`. It will dump data for a single zone by passing `-D <zone_name>` or it will dump data for multiple zones by passing `-f /path/to/zones.conf`.

#### Build Zone Data
>Example: `sudo php client.php zones`

Instead of building all configuration files for bind (i.e. using `buildconf`), only the zone data can be built and reload using this parameter.

#### Build Specific Zone Data
>Example: `sudo php client.php zones id=3`

Building and reloading the zone data for a single zone can be achieved by passing the zone ID.

#### API Usage
>Examples:
>>```
>>php client.php setHost id=36 action=add name=www value=1.2.3.4 type=A ttl=500 createPTR=yes comment="some comment" status=active`
>>php client.php setHost id=36 action=update name="@" newvalue=10.0.0.2 type=A reload=yes
>>```

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

#### Install URL Server
>Example: `sudo php client.php install url-only`

In order to use [URL resource records](./settings.md#define-url-rr-web-servers), you may want to install the client component on a server that is not a DNS server.

#### Enable URL Server
>Example: `sudo php client.php enable url`

An fmDNS client that has already been installed can get enabled to serve [URL resource records](./settings.md#define-url-rr-web-servers).

