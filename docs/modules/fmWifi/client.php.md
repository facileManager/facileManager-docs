--8<--
client.php.md
--8<--

### fmWifi Parameters

!!! warning "Documentation Missing"
    To be written.

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