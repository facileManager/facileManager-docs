## General Usage
Instead of writing your own interface to the API, the associated module's `client.php` script can be used as an API client. You can use the client app on any existing client or you may install it on a system that will be used for API interaction without any other module functionality.

If you choose to use the API from a system that is not a module client, you still need to install the client scripts, but may enable the API functionality within the module `client.php` script:

`sudo php /usr/local/facileManager/fmDNS/client.php install api`

### fmDNS
The supported API parameters can be viewed from the client help file:
```
php /usr/local/facileManager/fmDNS/client.php help
...
     api                      Invokes an API call (cannot be used with no-ssl)
     apitest                  Perform basic API functionality tests
     apicreds=/path/to/file   Filename containing API key and secret (default: config.inc.php)

    API parameters:
     action=XX                Defines API action to take on a record (add, update, delete)
     type=XX                  Defines the RR type (A, AAAA, CNAME, DNAME, MX, NS, PTR, TXT)
     name=XX                  Defines the name of the RR
     value=XX                 Defines the value of the RR
     ttl=XX                   Defines the TTL of the RR
     priority=XX              Defines the priority of the RR (MX only)
     append=XX                Defines whether to append the zone name or not (yes, no)
     comment=XX               Defines the record comment
     status=XX                Defines the record status (active, disabled)
     newname=XX               Defines the new record name (when action=update)
     newvalue=XX              Defines the new record value (when action=update)
     setPTR=XX                Defines whether to automatically create/update the PTR (yes, no)
     soa-only=XX              Defines whether to only increment the SOA serial number (yes, no)
     reload=XX                Defines whether to reload the zone or not (yes, no)
```

#### Add Record

```
sudo php /usr/local/facileManager/fmDNS/client.php api action=add id=4 type=A name=test value=192.0.2.10
Response: (202) Success
```

As long as the reverse zone already exists or can be automatically created, new A records can be created with along with the corresponding PTR.
```
sudo php /usr/local/facileManager/fmDNS/client.php api action=add id=4 type=A name=test value=192.0.2.10 setPTR=yes
Response: (201) Success
```

#### Update Record

```
sudo php /usr/local/facileManager/fmDNS/client.php api action=update id=4 type=A name=test value=192.0.2.10 newvalue=192.0.2.11 reload=yes    
Response: (200) Success
```

#### Delete Record

```
sudo php /usr/local/facileManager/fmDNS/client.php api action=delete id=4 type=A name=test
Response: (204) Success
```

#### Update SOA Serial Number

```
sudo php /usr/local/facileManager/fmDNS/client.php api id=4 soa-only=yes
Response: (200) Success
```

#### Reload Zone

```
sudo php /usr/local/facileManager/fmDNS/client.php api id=4 reload=yes
Response: (200) Success
```

--8<--
footer.md
--8<--
