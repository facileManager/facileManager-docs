facileManager has its core settings which can be adjusted and several modules have additional settings specific to the application.

## General
There are several settings available to set at **_Settings → General_**.

_The **Manage Settings** or **Super Admin** permission is required to change settings._

### Authentication
There are three types of authentication supported by facileManager:

`None`
>Every user will be automatically logged in as the default super-admin account that was created during the installation process.

`Built-in Authentication`
>Authenticates against the facileManager database using solely the users defined at **_Admin → Users_**.

`LDAP Authentication`
>Users are authenticated against a defined LDAP server. Upon success, users are created in the facileManager database using the selected template account for granular permissions within the environment. If no template is selected then user authentication will fail (this is another method of controlling access to facileManager). These users cannot be disabled nor can their passwords be changed within facileManager. The PHP LDAP extensions must be installed before this option is available.

You can reset the authentication method by setting the following in config.inc.php:

```
define('FM_NO_AUTH', true);
```

### Password Reset Expiry
Sets the amount of time the e-mailed password reset links are valid for.

### Login Message
Define a message to be displayed at login (such as a terms and conditions) and optionally require users to acknowledge the message for authenication to succeed.

### Client Registration
You can choose to allow clients to automatically register in the database or not during installation.

### API Support
By enabling API support, users are able to create keypairs to authenticate with through the client scripts. This opens up the ability to make a limited selection of module changes without using the web interface.

### Two-Factor Authentication
By enabling the 2FA requirement, all users will be emailed a one-time passcode during login attempts. Users may update their profile to utilize an authenticator app instead (if the [2FA modules are installed](../getting-started/basic-install.md#two-factor-authentication)).

### One-Time Passcode Expiry
Sets the amount of time the e-mailed one-time passcodes are valid for.

### SSL
You can choose to have facileManager enforce the use of SSL when a user tries to access the web app.

### Mailing
There are a few things facileManager and its modules may need to send an e-mail about (such as OTP and password reset links). These settings allow you to configure the mailing settings to use for your environment and enable/disable mailing altogether.

### Proxy Server
Set the appropriate configuration if facileManager is behind a proxy server for Internet access.

### Date and Time
Set your preferred timezone, date format, and time format for facileManager to use throughout all aspects of the app. What you select is how all dates and times will be display including any client configuration files.

### Logging Method
There are three logging methods supported by facileManager:

`Built-in`
>Events will only be logged in the facileManager database.

`syslog`
>Events will only be logged to syslog.

`Built-in + syslog`
>Events will be logged to facileManager and syslog.

### Show Errors
Choose whether you want facileManager errors to be displayed as they occur or not. This can be useful if you are having trouble adding or editing objects.

### Temporary Directory
Periodically facileManager and its modules may need to create temporary files or directories on your webserver. Specify the local path for it to use.

### Software Update
Choose whether or not facileManager will automatically check for software updates. If you opt in, then you choose the minimum release types to be notified about and the frequency of checks.

### SSH Username
When servers are configured to receive updates via SSH, this username will be created (if not already present) on your clients and will be used for the client interaction.

### SSH Key Pair
In order for client configs to be updated via SSH, facileManager needs a 2048-bit passwordless key pair generated. Without this key pair, clients cannot use the SSH update method. Click the 'Generate' button to have facileManager automatically generate the necessary key pair.

### Image Branding
Add your own image to brand facileManager. This image will be used on the login screen, navigation header, and automated e-mails. You need to manually add it to the document root on the web server and specify the relative URI path.

### Enable Maintenance Mode
Only users with Super Admin or Module Management privileges are able to authenticate. This is useful during application upgrades.

---
--8<--
fmDHCP/src/settings.md
--8<--

---
--8<--
fmDNS/src/settings.md
--8<--

---
--8<--
fmSQLPass/src/settings.md
--8<--

---
--8<--
fmWifi/src/settings.md
--8<--

--8<--
footer.md
--8<--
