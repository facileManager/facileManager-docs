## `client.php`
Most modules make use of a client app, but some may not. The modules with a client will have a `client.php` file found in `/usr/local/facileManager/<module_name>/` and it will utilize core functionality found in facileManager-core. Here we will break down the parameters available to all client apps.

You can always invoke the client help file at the CLI:
```
php client.php help
```

### Core Parameters

```
php client.php [options]

  -b|buildconf                Build server configuration and associated files
  -c|cron                     Run in cron mode
  -d|debug                    Enter debug mode for more output
  -h|help                     Display this help
  -n|dryrun                   Do not save any files - just output what will happen
  -p|purge                    Delete old configuration files before writing
  -s|no-ssl                   Do not use SSL to retrieve the configs
  -v|version                  Display the client version
     no-sudoers               Do not create/update the sudoers file at install time
     no-update                Do not update the server configuration from the client
     apitest                  Perform basic API functionality tests

     install                  Install the client components
  -o|options                  Installation options comma-delimited to avoid prompts
                                Valid options: 
                                    FMHOST    fM host url
                                    SERIALNO  Server serial number (or 0 to auto-generate)
                                    method    Update method to use (cron, ssh, http)
                                Examples: install -o FMHOST=https://example.com/fm/,method=cron
                                          install options FMHOST=fm.example.com,SERIALNO=0,method=ssh
     upgrade                  Upgrade the client components
     reinstall                Reinstall the client components
```

#### Help File
>Example: `php client.php help`

Invokes the client help file.

#### Version
>Example: `php client.php version`

Print the client app version.

#### Cron
>Example: `sudo php client.php cron`

If the client is setup to receive updates from the facileManager server via cron, this parameter will invoke the client to check for any pending configurations. This is also the parameter used to define the crontab job during [installation](../../getting-started/basic-install.md#client-installation).

!!! note
    This parameter only works if the client is configured to receive updates via cron.

#### Build Configuration
>Example: `sudo php client.php buildconf`

The client app exists to build the configuration for the system. Use this parameter to build the server configuration and associated files.

#### Debug Mode
>Example: `sudo php client.php buildconf debug`

Sometimes your desired configuration may not get deployed to the client and enabling debug mode will provide more information which may help in troubleshooting.

#### Dry-run
>Example: `php client.php buildconf dryrun`

Instead of applying the configuration on the client, this parameter will show you want will be applied without saving any files.

#### Purge Existing Configuration
>Example: `sudo php client.php buildconf purge`

There may be old configuration files (or files unmaintained by fM and its modules) that you want to delete.

#### Disable SSL
>Example: `sudo php client.php buildconf no-ssl`

This parameter will force the client to communicate with the fM server via http only.

#### Skip sudoers
>Example: `sudo php client.php install no-sudoers`

During the [client installation](../../getting-started/basic-install.md#client-installation), use this parameter to prevent the necessary sudoers entry from being made. This might be useful if you maintain the sudoers files by other means.

#### Disable Client Information Updates
>Example: `sudo php client.php install no-update`

The client will send information to the server about itself (OS, OS version, client version, app version). This parameter will prevent the information from being sent and populating the database.

#### Test API Functionality
>Example: `php client.php apitest`

Use this parameter to test the API communication.

#### Client Installation
>Example: `sudo php client.php install`

This parameter invokes the [client installer](../../getting-started/basic-install.md#client-installation) which asks a series of questions to correctly configure the client.

#### Installation Options
>Examples:
>>```
>>sudo php client.php install -o FMHOST=https://example.com/fm/,method=cron
>>sudo php client.php install options FMHOST=fm.example.com,SERIALNO=0,method=ssh
>>```

Instead of being prompted during installation, this parameter followed by the desired options will be passed to the installer.

>**Valid options:**
>
>| Option | Description |
>|--------|-------------|
>| `FMHOST` | fM host URL |
>| `SERIALNO` | Server serial number (or 0 to auto-generate) |
>| `method` | Update method to use (cron, ssh, http) |

#### Client Upgrade
>Example: `sudo php client.php upgrade`

This parameter will upgrade the client app to the latest available version.

#### Client Reinstallation
>Example: `sudo php client.php reinstall`

This parameter invokes the installer on a previously installed client.
