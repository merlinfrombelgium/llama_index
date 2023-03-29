![[Pasted image 20220803130713.png]]

    "deviceActionResults": [

        {

            "@odata.type": "#microsoft.graph.locateDeviceActionResult",

            "actionName": "locateDevice",

            **"actionState": "pending",**

            "startDateTime": "2022-08-03T10:53:24.6222751Z",

            "lastUpdatedDateTime": "2022-08-03T10:53:24Z",

            "deviceLocation": null

        },

https://developer.microsoft.com/en-us/graph/graph-explorer?request=deviceManagement%2FmanagedDevices%2F%7BmanagedDevices-id%7D%3F%24select%3DdeviceActionResults&method=GET&version=beta&GraphUrl=https://graph.microsoft.com

    "@odata.context": "https://graph.microsoft.com/beta/$metadata#deviceManagement/managedDevices(deviceActionResults)/$entity",

    "deviceActionResults": [

        {

            "@odata.type": "#microsoft.graph.locateDeviceActionResult",

            "actionName": "locateDevice",

            "actionState": "done",

            "startDateTime": "2022-08-03T10:53:24.6222751Z",

            "lastUpdatedDateTime": "2022-08-05T08:19:18Z",

            "deviceLocation": {

                "lastCollectedDateTimeUtc": "2022-08-05T08:19:18Z",

                "lastCollectedDateTime": "2022-08-05T08:19:18Z",

                "longitude": 4.561,

                "latitude": 51.19,

                "altitude": 0,

                "horizontalAccuracy": 0,

                "verticalAccuracy": 0,

                "heading": 0,

                "speed": 0

            }

        },

Import-Module Microsoft.Graph.DeviceManagement

Get-MgDeviceManagementManagedDevice -ManagedDeviceId $managedDeviceId -Property "deviceActionResults" 

>> longitude and latitude are formatted as flat data, eg. 4561 and 5119, without decimals
>> use rest query instead

`$deviceLocation = (Invoke-MgGraphRequest -Uri https://graph.microsoft.com/beta/deviceManagement/managedDevices/$($deviceid)?select=deviceActionResults).deviceactionresults.deviceLocation

[How To: Use Logic Apps to Query Intune for Device Information | Greg's Systems Management Blog (gregramsey.net)](https://gregramsey.net/2020/04/07/how-to-use-logic-apps-to-query-intune-for-device-information/)

<ComplexType Name="deviceGeoLocation">

<Property Name="altitude" Type="Edm.Double" Nullable="false"/>

<Property Name="heading" Type="Edm.Double" Nullable="false"/>

<Property Name="horizontalAccuracy" Type="Edm.Double" Nullable="false"/>

<Property Name="lastCollectedDateTime" Type="Edm.DateTimeOffset" Nullable="false"/>

<Property Name="lastCollectedDateTimeUtc" Type="Edm.DateTimeOffset" Nullable="false"/>

<Property Name="latitude" Type="Edm.Double" Nullable="false"/>

<Property Name="longitude" Type="Edm.Double" Nullable="false"/>

<Property Name="speed" Type="Edm.Double" Nullable="false"/>

<Property Name="verticalAccuracy" Type="Edm.Double" Nullable="false"/>

</ComplexType>

![[Pasted image 20220831184608.png]]
![[Pasted image 20220902130859.png]]

![[Pasted image 20220831184622.png]]
![[Pasted image 20220831184633.png]]
![[Pasted image 20220902140319.png]]![[Pasted image 20220902140335.png]]
## Security and privacy information for lost mode and locate device actions

-   No device location information is sent to Intune until you turn on this action.
-   When you use the locate device action, the latitude and longitude coordinates of the device can be retrieved by using the Graph API.
-   The data is stored for 24 hours, then removed. You can't manually remove the location data.
-   The data for last known locations is stored for up to seven days, and then removed.
-   Location data is encrypted, both while stored and while being transmitted.

https://docs.microsoft.com/en-us/mem/intune/remote-actions/device-locate#security-and-privacy-information-for-lost-mode-and-locate-device-actions

## PowerShell
Connect-MgGraph -Scopes DeviceManagementManagedDevices.ReadWrite.All
Find-MgDeviceManagementManagedDevice -ManagedDeviceId b89278d3-53fa-436c-a62c-ed848fbe716d

![[Pasted image 20220902154741.png]]

[Quick Tip: How do I: Enable or disable Map and Filled Map visuals in PowerBI? – think about IT](https://thinkaboutit.be/2022/03/quick-tip-how-do-i-enable-or-disable-map-and-filled-map-visuals-in-powerbi/)

![[Pasted image 20220902155217.png]]