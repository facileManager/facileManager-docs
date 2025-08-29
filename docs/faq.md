The purpose of this guide is to address some frequently asked questions among users of facileManager and its modules.

If you would like to see a new FAQ that you think would assist other users, [start a discussion](https://github.com/facileManager/facileManager/discussions) or [open an issue](https://github.com/facileManager/facileManager-docs/issues).

## facileManager
### Why is admin-modules.php not found?
In order for admin-modules.php to work, the `.htaccess` file must be present in your directory root (with all other fM files) and must contain [this content](https://raw.githubusercontent.com/facileManager/facileManager/refs/heads/master/server/.htaccess).

In addition, `AllowOverride All` must be present in your `<Directory /path/to/fM>` directive on your web server.

## fmDNS
### How do I import the entire BIND configuration?
This is currently not supported as the fmDNS import tool only supports importing views and zones.
