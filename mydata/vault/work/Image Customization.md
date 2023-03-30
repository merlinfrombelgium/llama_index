If none of the default gallery images meet your requirements, you can upload ==up to 20== of your own custom device images.

## [Image requirements](https://learn.microsoft.com/en-us/windows-365/enterprise/device-images#image-requirements)

-   Windows 10 Enterprise version 20H2 or later.
-   Windows 11 Enterprise 21H2 or later.
-   Generation 2 images.
-   Generalized VM image.
-   Single Session VM images (multi-session isn’t supported).
-   No recovery partition. For information about how to remove a recovery partition, see the [Windows Server command: delete partition](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/delete-partition).
-   Default 64-GB OS disk size. The OS disk size will be automatically adjusted to the size specified in SKU description of the Windows 365 license.
-   Exist in an Azure subscription.
-   Is stored as a managed image in Azure.

> [!Note]
Storing a managed image on Azure incurs storage costs. However, customers can delete the managed image from Azure once they've successfully uploaded it as a Custom Image to Microsoft Endpoint Manager.


## [](https://learn.microsoft.com/en-us/windows-365/enterprise/device-images#gallery-images)Gallery images

Windows 365 provides a built-in gallery of Windows Enterprise images accessible through the provisioning policy creation flow. They're replicated to all Azure regions to give you a quick provisioning experience. These images are updated monthly with the latest security updates so that end users have a secure and seamless experience.

There are two sets of images available to choose from across the different versions of Windows Enterprise:

-   **Images with pre-installed Microsoft 365 Apps**: Microsoft 365 Apps and Teams optimizations are already installed. The following settings are pre-applied:
    -   IsWVDEnvironment reg key (Teams).
    -   C++ Runtime (Teams).
    -   WebRTC Redirector (Teams).
    -   Microsoft Teams (Teams).
    -   Microsoft Edge settings like sleeping tabs, startup boost, and first time optimizations based on Azure AD and synchronization.
    -   Microsoft Outlook first-time configuration settings (auto log-on based on Azure AD profile, support for other profiles).
-   **Images with OS optimizations**: These are Windows Enterprise images optimized for improved performance on virtualized environments and on lower end hardware configurations. The following settings are pre-applied:
    -   Services optimized for virtualization.
    -   UWP packages removed.
    -   Task scheduler actions disabled.