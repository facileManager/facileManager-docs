## fmDHCP Parameters
fmDHCP has additional parameters that can be passed to `client.php` that are specific to this module.

#### -l (dump|delete)
Leases can be managed by invoking `-l` followed by an option to `dump` or `delete` them.

!!! example
  ```
  sudo php client.php -l dump
  sudo php client.php -l delete=10.1.1.100
  ```

#### -o `<(human|web)>`
When dumping the leases, you can specify the output style -- either `human`-readable or used for `web`.

!!! example
  ```
  sudo php client.php -l dump -o web
  ```
