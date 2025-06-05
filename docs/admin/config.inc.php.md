The configuration file consists of variables ranging from database connection details to disabling features.

## Database Credentials
These variables are set during installation.

#### `$__FM_CONFIG['db']['host']`
> The hostname or IP address containing the database.

> !!! example
    ``` php
    $__FM_CONFIG['db']['host'] = 'localhost';
    ```

#### `$__FM_CONFIG['db']['user']`
> The username used to connect to the database.

> !!! example
    ``` php
    $__FM_CONFIG['db']['user'] = 'fM';
    ```


#### `$__FM_CONFIG['db']['pass']`
> The passphrase used to connect to the database.

> !!! example
    ``` php
    $__FM_CONFIG['db']['pass'] = 'secret-passphrase';
    ```

#### `$__FM_CONFIG['db']['name']`
> The database name.

> !!! example
    ``` php
    $__FM_CONFIG['db']['name'] = 'facileManager';
    ```

## Database SSL connection settings
If your database is optionally secured with SSL then you can specify the certificate details.

#### `$__FM_CONFIG['db']['key']`
> The key file path.

> !!! example
    ``` php
    $__FM_CONFIG['db']['key'] = '/path/to/ssl.key';
    ```

#### `$__FM_CONFIG['db']['cert']`
> The certificate file path.

> !!! example
    ``` php
    $__FM_CONFIG['db']['cert'] = '/path/to/ssl.cer';
    ```

#### `$__FM_CONFIG['db']['ca']`
> The CA certificate path.

> !!! example
    ``` php
    $__FM_CONFIG['db']['ca'] = '/path/to/ca.pem';
    ```

#### `$__FM_CONFIG['db']['capath']`
> The directory path containing trusted CA files.

> !!! example
    ``` php
    $__FM_CONFIG['db']['capath'] = '/path/to/trusted/cas';
    ```

#### `$__FM_CONFIG['db']['cipher']`
> The cipher to use.

> !!! example
    ``` php
    $__FM_CONFIG['db']['cipher'] = null;
    ```

## Disable Features
Sometimes it may be necessary to disable a feature (or functional check) based on your environment.

#### `FM_NO_AUTH`
> If all super-admin users get locked out, the authentication can be disabled.  This will set **Authentication Method** to _None_ in the **_Settings → General_**.

> !!! example
    ``` php
    define('FM_NO_AUTH', true);
    ```

>You should remove this configuration entry once the authentication method is reset otherwise it will continue to get reset.

#### `FM_NO_HTACCESS`
> facileManager performs checks to ensure the **_.htaccess_** file is present in the document root. In some cases, it may be necssary to disable the check. For example, you may opt to put the contents in the virtual host directive of your web server configuration.

> !!! example
    ``` php
    define('FM_NO_HTACCESS', true);
    ```


#### `FM_NO_REWRITE_TEST`
> facileManager performs checks to ensure the rewrites (typically found in _.htaccess_) are working properly. In some cases, it may be necessary to disable the check. For example, you may need to disable this check if your web server is behind a proxy.

> !!! example
    ``` php
    define('FM_NO_REWRITE_TEST', true);
    ```

