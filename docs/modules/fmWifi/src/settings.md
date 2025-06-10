## fmWifi
There are a few settings available at **_Settings → fmWifi_**.

_The fmWifi **Manage Settings** or **Super Admin** permission is required to change settings._

### Include WLAN PSK
>Default: `disabled`

Always include the WLAN PSK even when users are defined.

### Use ebtables
>Default: `enabled`

Block clients with `ebtables` in addition to deny list. The `ebtables` package is required on the access point (AP) and the AP must be configured as a bridge.

This option is recommended for Raspbian systems.

!!! note
    The ACL functionality of hostapd (`macaddr_acl`) does not seem to work with Raspbian. Therefore, the use of `ebtables` is recommended to deny clients.