Universal Print is a cloud service that utilizes Azure to allow for the printing of documents from various devices. The connector, which can be installed on a physical or virtual device running either Windows Server or Windows Client OS, is required to connect to the service. This connector device can be located on-premises or hosted in Azure. It is possible to install the connector on an existing print server to quickly add all the printers on that device to Universal Print.

#### Print Connector
The Print Connector acts as a proxy between your on-premises location and the Universal Print service if your printer does not support Universal Print. However, if your printer is Universal Print ready, such as some sold by Ricoh, it can be directly connected to the cloud without the need for an ExpressRoute or VPN connection. Once you have shared and connected your printers correctly, you can use Microsoft Endpoint Manager to assign them to virtual and physical Windows 10 Enterprise desktops.

#### Where does printed data go?
Universal Print stores all print queues in Office Data Storage, which is also used to store customers' Office 365 mailboxes and OneDrive files. A job remains in the print queue for a few days, and if it is not printed within three days, it is marked as aborted. After printing, a job may remain in Universal Print for up to an additional 10 days.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image5.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image5.png)

#### Built-in location detection – your printers follow you based on your location
Universal Print offers the option to assign a printer based on a location such as Building R8, S4 or a location at Anderlecht. And when working from home, your home printer gets auto-assigned to the print queue.

Universal Print allows for the use of filters based on location, such as country, city, building, and floor. Alternatively, it is also possible to use GPS-based location allocation. The Printer Administrator can configure the latitude and longitude of the printers in the Universal Print Admin portal. In order to track the location of the user, location sharing must be turned on on the user's physical endpoint device running Windows. This can be managed through an Intune policy or GPO.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-01-10_10-26-59.jpg)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-01-10_10-26-59.jpg)

Supported hardware partners for Universal Print
Universal Print is a platform that can be enhanced with add-on solutions from software vendors. If your hardware printer is a Universal Print ready printer through one of the hardware solutions mentioned, it can be directly connected to the Universal Print service in the cloud without the need for a Universal Print connector in the on-premises environment. This allows for a more streamlined printing process. _Consult the full list of partners here: [Partner Integrations – Universal Print | Microsoft Docs](https://docs.microsoft.com/en-us/universal-print/fundamentals/universal-print-partner-integrations)

## Universal Print ready printers

Provider/Vendor | Universal Print ready models | PIN release option
-- | -- | :--:
Brother | [Brother](https://support.brother.com/g/b/oscontents.aspx?ossid=23)
Canon US | [imageRUNNER ADVANCE DX Series](https://www.usa.canon.com/internet/portal/us/home/products/list/copiers-mfps-fax-machines/multifunction-copiers/multifunction-copiers)
Canon Europe | [imageRUNNER ADVANCE DX Series](https://www.canon-europe.com/business-printers-and-faxes/imagerunner-advance-dx/) [imageRUNNER ADVANCE III Series](https://www.canon-europe.com/business-printers-and-faxes/imagerunner-advance-iii-series/) [i-SENSYS MF832Cdw](https://www.canon-europe.com/business-printers-and-faxes/i-sensys-mf832cdw/)
Epson | [Epson](https://techcommunity.microsoft.com/t5/universal-print-blog/universal-print-ready-printers-by-epson/ba-p/2170239) | Yes
FujiFilm | [FujiFilm](https://techcommunity.microsoft.com/t5/universal-print-blog/fujifilm-offers-universal-print-ready-printers/ba-p/3025475)
HP | [HP](https://developers.hp.com/workpath-sdk/compatible-devices)
Konica Minolta | [Konica Minolta](https://kmbs.konicaminolta.us/kmbs/technology/i-series)
Kyocera | [Kyocera](https://www.kyoceradocumentsolutions.com/support/universal_print/)
Lexmark | [Lexmark](https://www.lexmark.com/en_us/solutions/print-solutions/microsoft-universal-print/universal-print-ready-product.html)
Ricoh | [Ricoh](https://www.ricoh-usa.com/en/support-and-download)
Sharp | [Sharp](https://global.sharp/products/copier/info/info_ms_universal_print.html) | Yes
ToshibaTec | [ToshibaTec](https://www.toshibatec.com/supported_models/Universal_Print.html)
Triumph-Adler | [Triumph-Adler](https://www.triumph-adler.de/ta-de-de/software/mobile-und-cloud/universal-print)
Xerox | [Xerox](https://www.office.xerox.com/en-us/software-solutions/universal-print)

#### **Universal Print licensing

Universal Print is – next to other Microsoft 365 services, like Azure Virtual Desktop – part of almost all the common Microsoft 365 licenses. UCB subscribes to, amongst others, Microsoft 365 E3 and E5 licenses and is covered for Universal Print.

_See below all the supported licenses. Click here to go to the official documentation for the most recent list too._ [_https://docs.microsoft.com/en-us/universal-print/fundamentals/universal-print-preview-access#which-subscriptions-are-eligible_](https://docs.microsoft.com/en-us/universal-print/fundamentals/universal-print-preview-access#which-subscriptions-are-eligible)

-   Microsoft 365 Enterprise F3, E3, or E5
-   Windows 10 Enterprise E3 or E5
-   Microsoft 365 Education A3 or A5
-   Windows 10 Education A3 or A5
-   Microsoft 365 Business Premium

### Requirements

-   Endpoints should be joined to Azure Active Directory. Hybrid AAD (HAADJ) joined devices/virtual desktops are also supported.
-   **Eligible** Microsoft 365 or Windows SKUs **license** as listed above, not a TRIAL license but a normal production license.Universal Print licenses assigned to the Azure AD tenant via the Global Administrator
-   A Universal Print supported printer that can connect directly to the Cloud – without connector
-   A normal USB or Network Printer (via Connector)
-   To configure Universal Print, the administrator doing the work should have either the Printer Administrator – Azure AD role, or should just be the Global Administrator.
    -   Windows 10 physical and virtual desktops must be enrolled with Microsoft Endpoint Manager
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


### Deploy Universal Print

The environment must be either Hybrid Azure Active Directory enabled or Azure AD joined. _Read more about the process here:_ [Configure hybrid Azure Active Directory join for managed domains | Microsoft Docs](https://docs.microsoft.com/en-us/azure/active-directory/devices/hybrid-azuread-join-managed-domains)

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-01-09_11-25-59.jpg)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-01-09_11-25-59.jpg)

### Configure Universal Print licensing

This requires one of the afore mentioned Microsoft 365 (not Office 365) or Windows SKUs and a tenant that is NOT a trial tenant, but a production Microsoft 365 tenant.

_**Note**: Trial licenses will not accept the Universal Print license, you MUST run the steps below as production tenant – or one test tenant with normal Microsoft 365 licenses._

Go to the M365 admin portal.

[https://admin.microsoft.com/adminportal/home?#/homepage](https://admin.microsoft.com/adminportal/home?#/homepage)

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image8.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image8.png)

Go to Purchase services

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image9.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image9.png)

Scroll to the bottom of the page and click **“Add-ons”**

[![](https://www.christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-04-11_15-25-05.jpg)](https://www.christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-04-11_15-25-05.jpg)

Click on **Details** under **Universal Print**

![](https://www.christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-04-11_15-24-50.jpg)

Click on Buy

![](https://www.christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-04-11_15-24-39.jpg)

Assign the licenses to a predetermined user group – via the users menu in the admin portal.

To delegate access, to configure the Universal Print service with an account other than the Global Administrator, assign the Printer Administrator and Printer Tech roles to a user account or group.

![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image15.png)

### Start the Universal Print configuration in the Azure Portal

Go to the Azure Portal – and logon with either our Global Administrator or the account with the Printer admin/tech roles assigned.

[https://portal.azure.com](https://portal.azure.com/)

Search for Universal Print

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image16.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image16.png)

Make sure you have a Universal Print license assigned.

![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image17.png)


[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image3.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image3.png)

> [!NOTE] - Rewrite for Ricoh printer
> Setup Universal Print – on a Lexmark Universal Print Ready printer
> 
> You can perform the following steps if your printer is Universal Print ready. If it’s not, please start your configuration journey [here](https://www.christiaanbrinkhoff.com/2021/01/15/modernize-your-print-server-environment-learn-how-to-implement-and-deploy-with-mem-new-cloud-service-universal-print-to-simplify-the-way-you-manage-your-printers/#10).
> 
> _**N****ote**: Other printers like Canon, Brother, and Konica Minolta are supported too. Here’s a full list [Partner Integrations – Universal Print | Microsoft Docs](https://docs.microsoft.com/en-us/universal-print/fundamentals/universal-print-partner-integrations)_
> 
> **Open** the **Web management console** of your Lexmark printer
> 
> **Go** to the **Network/Ports** menu under **Settings**
> 
> ![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-04-11_11-04-45.jpg)
> 
> **Scroll** **down** to the **Universal Print** section
> 
> Click on **Register** 
> 
> ![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-04-11_11-04-19.jpg)
> 
> **Logon** with your **Printer** **Operator** – or **Global Administrator** Azure AD account credentials.
> 
> [![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-04-11_11-12-04.jpg)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/2021-04-11_11-12-04.jpg)
> 
> You Printer has **successfully** be **registered** to Universal Print. _**Continue the Print sharing and Publishing steps [here](https://www.christiaanbrinkhoff.com/2021/01/15/modernize-your-print-server-environment-learn-how-to-implement-and-deploy-with-mem-new-cloud-service-universal-print-to-simplify-the-way-you-manage-your-printers/#13).**
>
> 


#### Set up the Universal Print connector – to connect to your On-Premises location/printers.

Please perform the following steps if your own printers are not able to connect with Universal Print (not Universal Print ready) directly and do require a bridge/proxy which has to be done with the Universal Print connector

**_Note:_** You can also install the software on one of your legacy print-servers to connect them to the Universal Print service. The Print Connector must run in order to connect to the printer, it’s possible to let other users print via a printer that is connected via a print connector on someone else’s desktop.

Install the Universal Print Connector on your local physical desktop, that is in the same network as your Printers.

Download the latest Print Connector here: [https://aka.ms/UPConnectorMSI](https://aka.ms/UPConnectorMSI)

Install the Print Connector. Click Install

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image18.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image18.png)

Once the installation is ready. Click on Launch

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image19.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image19.png)

Click on Ok – to confirm the diagnostic data prompt.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image20.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image20.png)

Click on Login

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image21.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image21.png)

Logon with your users Azure AD credentials

> [!NOTE]
> No need to use the Print Administrator / Global Administrator account.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image22.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image22.png)

Enter a name for the Connector – the connector will show up later in the Universal Print – admin portal as proxy for that designated printer(s).

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image23.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image23.png)

 The Connector will now be registered to the Universal Print Service.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image24.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image24.png)

In the Connectors menu – you’ll see the Connector name showing up.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image25.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image25.png)

You can click on the connector name to see some of the details of that specific machine and its status.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image26.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image26.png)

### Enable hybrid AD configuration – via the Universal Print Connector

**_Note_**: This step only applies to Azure Virtual Desktop or any other Hybrid Azure AD physical endpoint scenario.

Activate Hybrid Azure AD in the Universal Print connector.

Tick the box to ON

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image27.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image27.png)

### Register your own custom Printers to Universal Print

We are ready with the connection part; we now need to make them available in the Cloud – as part of the Universal print service.

Select the printers that you want to add – _the list of available printers is being detected from the printers attached to the desktop/server you install the Printer Connector on._

Select the Printers – in the available Printers list. Click on Register

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image28.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image28.png)

 The printers are being added to the Cloud. The status is in progress. This takes a minute or so.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image29.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image29.png)

### Share your Printers with your users

We’ve done all the pre-steps now, the printers are now all visible in the Printers list – however, as you can see, they aren’t shared yet. That’s something we are going to do now.

Go to the Universal Print Portal – and open Printers. _As you can see, they have the status “Not shared”_

Select the Printer(s) you want to share. Click on Share

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image30.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image30.png)

### Assign permissions to use Printer(s)

Now we are ready with the Print sharing/publishing steps, the users are still not allowed to see and use the printers. Therefore, we need to add either an Azure AD Group – or the users directly to the list of members.

You can also select the “Allow access to everyone in my organization” option to allow all users to print.

Select your AAD users or groups. Once ready, click on Share Printer

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image31.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image31.png)

_The printer is being shared…_

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image32.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image32.png)

The printer is now ready to test within your desktop – as the status is Printer Shared.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image33.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image33.png)

### Test your printer assignment – logon to your virtual or physical Desktop

Logon as an Azure AD user to your Azure Virtual Desktop – that is assigned to one of the previously shared printers within Universal Print.

Go and search for Printers & scanners – in the start menu

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image34.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image34.png)

Click on Add a printer or scanner

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image35.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image35.png)

Click on Search Universal Print for printers – your assigned Cloud printers should pop up automatically.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image36.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image36.png)

Click on Add device to add the Cloud-based printer to your virtual or physical desktop

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image37.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image37.png)

The printer has now been added and is ready to test.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image38.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image38.png)

Open the Cloud-based Printer – Click on Manage

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image39.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image39.png)

Click on – Print a test page. The test page has been sent to the printer. You can open the print queue to see if something happens.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image40.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image40.png)

_The test print job has been sent to the printer._

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image41.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image41.png)

If everything goes fine, the print job should be available and listed in the Universal Print – Admin portal too. You can find the jobs in the Universal Print portal by clicking on the Printer, followed by jobs.

You should see the job as status Completed.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image42.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image42.png)

#### Assign and deploy Cloud-printers with Microsoft Endpoint Manager

In the previous section, you’ve learned about all the basics as well as the manual process of assigning printers. This process is also possible to perform via Microsoft Endpoint Manager (as explained earlier) – as a more Enterprise-ready approach to e.g., assign hundreds of printers across the globe to your users.

First, **download** the **Universal** **Print** – provisioning **tool** via [Download Universal Print printer provisioning tool (preview) from Official Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=101453)

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image43.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image43.png)

Make the CSV list ready for deployment as the Microsoft Endpoint Manager enrolment will be using the CSV as source. You can find the printers.CSV file in the tool – as part of SamplePolicy.zip.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image44.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image44.png)

Add all the Universal Print – Printer Share Name and Share IDs – and if the printer should become the default printer – into the CSV file in the following order.

SharedId,SharedName,IsDefault

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image45.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image45.png)

 Look up the Printer Share Names and Share IDs that you want to add via Microsoft Endpoint Manager.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image46.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image46.png)

Generate the custom Win32 application package that includes the new .CSV file with the correct printer share names and IDs.

Download the – Microsoft Win32 Content Prep Tool.

Unzip the tool e.g. on the C:\ drive (you could pick a random folder as well)

[https://github.com/Microsoft/Microsoft-Win32-Content-Prep-Tool](https://github.com/Microsoft/Microsoft-Win32-Content-Prep-Tool)

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image47.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image47.png)

Open PowerShell – and change directory to the Intune Prep tool location e.g. C:`\Microsoft-Win32-Content-Prep-Tool-master

Cd “C:`\Microsoft-Win32-Content-Prep-Tool-master”

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image48.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image48.png)

Run .\ntuneWinAppUtil.exe and fill in the following requirements:

-   Source folder: The folder where list of printers (printers.csv) and InstallPolicy.cmd files are present.
-   Setup file: Path of the InstallPolicy.cmd file (or any other script that will be used to copy the printers.csv file on users’ devices)
-   Output Folder: Folder where you will like the generated intunewin package file to be stored.
-   Do you want to specify catalog folder (Y/N): Enter N.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image49.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image49.png)

The .\\intunewin package is ready to use within Microsoft Endpoint Manager

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image50.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image50.png)

 Open the Microsoft Endpoint Manager Console via – [endpoint.microsoft.com](http://endpoint.microsoft.com/)

Open the Apps menu

Click on Add

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image51.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image51.png)

Choose for Windows app (Win32)

Click on Select

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image52.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image52.png)

Click on – Select app package file and browse to the .intunewim _file output – e.g InstallPolicy.intunewin in folder C:\Microsoft-Win32-Content-Prep-Tool-master_

Click on Ok

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image53.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image53.png)

 Give the app a custom name such as the _Install HP Printers_ example below. Click next

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image54.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image54.png)

Take over the line below in the Install and Uninstall command field. Make sure it’s a User installed application.

InstallPolicy.cmd user install

InstallPolicy.cmd user uninstall 

Click on Next

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image55.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image55.png)

Take over the requirements as baseline OS version.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image56.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image56.png)

 Fil in the detection rule based on the CSV file – that included your printers to be added. Add the location below in the path section and printers.csv in the file or folder field.

%AppData%\UniversalPrintPrinterProvisioning\Configuration

Make sure Detection method is set to File or folder exists. Click Ok.

Click Next

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image57.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image57.png)

Filter the list of printers in the assignment’s menu to e.g. AD groups per department.

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image58.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image58.png)

 Confirm the settings, click on Next and Create

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image59.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image59.png)

Your printers are now being pushed to your users and virtual desktops!

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image60.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image60.png)

### Need help? Visit the Universal Print FAQ

**Please visit the official Universal Print FAQ here**: [Universal Print – Frequently Asked Questions (FAQ) | Microsoft Docs](https://docs.microsoft.com/en-us/universal-print/fundamentals/universal-print-faqs) – or join [join the Universal Print community](https://techcommunity.microsoft.com/t5/universal-print/ct-p/UniversalPrint) on Tech Community to ask questions directly to the product group – or provide feedback on the service!

[![](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image61.png)](https://christiaanbrinkhoff.com/wp-content/uploads/2021/01/1610186967_image61.png)