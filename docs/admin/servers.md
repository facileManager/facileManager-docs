## Enable Server
Once you have the [module activated](manage-modules.md/#activate-modules) and the [client app installed](../getting-started/basic-install.md#client-installation) (if applicable) on your servers, you will want to review the configuration to make sure the installer grabbed the correct information.

Go to **_Config → Servers_** and review the servers.  Once everything is correct, you can enable the server by clicking on the slider in the **_Actions_** column of the server listing.

![Enable Server](../images/modules/common/ServerEnable.png)

_The **Server Management** or **Super Admin** permission is required to add, edit, and delete servers._

## Preview Configuration
The configuration for each server can be previewed by going to **_Config → Servers_** and click on the magnifying glass in the **_Actions_** column of the server to preview.

![Preview Config](../images/modules/common/ServerPreviewConfig.png)

## Build Configuration
Any time a server's configuration needs to be built, the background will turn blue to signify the server needs a configuration built.

![Server Flagged for Build Config](../images/modules/common/Servers.png)

When you are ready to build the configuration and deploy it, there are three ways of accomplishing this:

>**Wrench icon**
>> Click on the wrench (or spanner) icon in the server actions column.

>> ![Build Config](../images/modules/common/ServerBuildConfig.png)

>**Bulk action**
>> Tick the box for each server you want to build the configuration for and select **Config Build** from the **_Bulk Actions_** menu and then click **_Apply_**.

>> ![Bulk Build Config](../images/modules/common/ServerBuildConfigBulk.png)

>**Process all updates**
>> Click the **_Process all updates_** icon in the upper right.

>> ![Process all updates](../images/modules/common/ProcessAllUpdates.png)

>> !!! warning
       This will process all available updates for all servers and zones.

_The **Build Server Configs** or **Super Admin** permission is required to build the server configurations._

--8<--
footer.md
--8<--
