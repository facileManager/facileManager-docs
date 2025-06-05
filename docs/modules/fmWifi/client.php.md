--8<--
client.php.md
--8<--

## fmWifi Parameters
fmWifi has additional parameters that can be passed to `client.php` that are specific to this module.

```
     block=XX                 Specify the MAC address to block (option may be used more than once)
                                Example: client.php block=00:11:22:aa:bb:cc
  -e|ebtables                 Block the MAC with ebtables
                                Example: client.php block=00:11:22:aa:bb:cc -e
  -o (human|web)              Specify the output type (default: human)
                                Example: client.php -o web
     show-clients             Show connected clients
     status                   Get status of access point
     status-all               Get full status of access point
```

#### Block MAC address
>Example: `sudo php client.php block=00:11:22:aa:bb:cc`

This parameter will block the specified MAC address from connecting to the access point.

#### Block using ebtables
>Example: `sudo php client.php block=00:11:22:aa:bb:cc -e`

This parameter will block the specified MAC address from connecting to the access point using ebtables.

#### Show Connected Clients
>Example: `sudo php client.php show-clients`

This parameter will provide a list of connected clients.

#### Show AP Status
>Example: `sudo php client.php status`

This parameter will show the current status of the access point.

#### Disable SSL
>Example: `sudo php client.php status-all`

This parameter will show the full status of the access point.

#### Output Format
>Example: `sudo php client.php status -o web`

This parameter will format the output either for `human`-readable or for `web`. This is to be used with `show-clients`, `status`, and `status-all`.
