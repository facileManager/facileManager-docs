All aspects of WLAN configuration takes place in the WLAN menu item. From there you can add, edit, and delete WLANs and options depending on your user permissions.

## WLANs
WLANs can be defined at WLAN → Manage. In the add/edit WLAN window, select and define the SSID, APs to serve the WLAN, mode, security, channel, and country options.

!!! note
    If WPA is enabled, fmWifi will only configure WPA2.

_The 'Manage WLANs' or 'Super Admin' permission is required to add, edit, and delete WLANs._


## Options
Options can be defined globally or server-based which is controlled by the servers drop-down menu in the upper right. Currently, the options configuration is rudimentary and can be defined at Config → Options.

!!! note
    Server-level options always supercede global options.

_The 'Server Management' or 'Super Admin' permission is required to manage WLAN options._


## Users
If you want to use individual user accounts, they need to be defined at WLAN → Users. Users allow unique passphrases for each connecting MAC address (client) to the WLAN. These will override the WLAN WPA2 passphrase which may or may not be included in the WLAN configuration which can be defined in the Settings.

_The 'Manage WLAN Users' or 'Super Admin' permission is required to manage views._


## ACLs
Access Control Lists are defined at WLAN → ACLs to define which MAC addresses (clients) are allowed or denied access to the WLAN.

When defining an ACL, specify the WLANs it applies to, the client MAC address, and the action.

_The 'Manage WLAN Users' or 'Super Admin' permission is required to manage ACLs._