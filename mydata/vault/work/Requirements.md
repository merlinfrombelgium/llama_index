### Requirements

-   Your desktops should be joined to Azure Active Directory. Hybrid AAD (HAADJ) joined devices/virtual desktops are also supported.
-   **Eligible** Microsoft 365 or Windows SKUs **license** as listed here: [[High-level#**Universal Print is most likely already part of your existing Microsoft 365 license**]] Trial licenses do not apply.Universal Print licenses assigned to the Azure AD tenant by the Global Administrator.
-   A Universal Print supported printer that can connect directly to the Cloud – without connector.
-   A normal USB or Network Printer (via Connector)
-   To configure Universal Print, the administrator doing the work should have either the Printer Administrator – Azure AD role, or the Global Administrator role.
-   Windows 10 physical and virtual desktops must be enrolled with Microsoft Intune.
-   Window 10 client device – on version 1903 or later
    -   Windows 10 devices need to have the latest Windows Update installed:
    -   Windows 10, version 2004: KB4571744
    -   For Windows 10, versions 1903 and 1909: KB4566116
    -   Windows 10, version 2004: KB4571744
    -   For Windows 10, versions 1903 and 1909: KB4566116
-   Universal Print connector host
-   Network requirements – The connectors and your Desktops should be able to connect the Universal Print – service URLs below.
    -   [https://login.microsoftonline.com](https://login.microsoftonline.com/)
    -   [https://aadcdn.msftauth.net](https://aadcdn.msftauth.net/)
    -   *.[print.microsoft.com](http://print.microsoft.com/)