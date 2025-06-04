## fmSQLPass Settings
There are several settings available to set at **_Settings → fmSQLPass_**.

The fmSQLPass _Manage Settings_ or _Super Admin_ permission is required to change settings.

### Minimum Password Strength
>Default: `Strong`

This setting restricts the new passwords to a minimum strength:

>_Medium_ - The password must be at least seven (7) characters long containing letters and numbers.

>_Strong_ - The password must be at least eight (8) characters long containing uppercase and lowercase letters, numbers, and special characters ('&', '$', '@', etc.).

### Default Username
>Default: `none`

Default database user to login as. This will be overridden if the user is defined at the server level.

### Default Password
>Default: `none`

Default database user password to login with. This will be overridden if the password is defined at the server level.