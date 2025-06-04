## Server Upgrade

Ensure software update checks are enabled in **_Settings → General_**
>![Software Tree Selection](../images/SoftwareTree.png)

When there is an upgrade availabe, navigate to Modules and click **_Update Core_**.
>![Core Upgrade Available](../images/CoreUpgradeAvailable.png)

This process will automatically download the latest facilemanager-core package and extract it in the document root. The next step is to update the database which forces all authenticated users to logout and only super-admin users can upgrade the database.

!!! note
    Ensure your document root for facileManager is writable by the web server user.

    !!! example
         ```
         sudo chown -R www:www /var/www/html/facileManager
         ```

### Alternative Method
1. Make a backup of your database manually or by using the built-in tool via the UI.
2. Make a backup of your config.inc.php file.
3. Delete your old facileManager files.
4. Extract/upload the new files from the server directory.
5. Copy your backup of config.inc.php to the document root.
   (i.e. /var/www/html/facileManager/)
6. Login as a super-admin to facileManager and follow the wizard to upgrade 
   your database.
7. Once fM is upgraded, you will be redirected to the admin-modules page where
   you can upgrade your modules individually.

## Client Upgrade

You can update the clients through the UI (**_Admin → Servers_**) or by running the following on the clients:

`sudo php /usr/local/facileManager/<module_name>/client.php upgrade`

### Alternative Method
1. Make a backup of your config.inc.php file.
>`cp /usr/local/facileManager/config.inc.php .`
2. Move the contents of the client directory to /usr/local/ on your client
   servers to manage.
>`sudo mv facileManager/client/facileManager /usr/local/`
3. Restore your backup of config.inc.php to /usr/local/facileManager.
>`sudo mv config.inc.php /usr/local/facileManager`