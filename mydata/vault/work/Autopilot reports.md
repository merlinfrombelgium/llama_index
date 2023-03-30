# 1/16/2023 Topic 
 
## Participants 

 
 ![[Pasted image 20230116165755.png]]
---- 
 
## Preparation 
 
  
 
---- 
 
## Notes 
 
  - device ready for Autopilot?
	- name starts with ATP*
	- prereqs in place?
		- hash registered
		- deployment profile assigned
- device gone through Autopilot process?
	- compliant? ready for use?
	- Graph query?
- user affinity
	- no user affinity through AP
	- query CA/Defender/Log Analytics on user sign-in and match timestamp
- 

[managedDevice resource type - Microsoft Graph beta | Microsoft Learn](https://learn.microsoft.com/en-us/graph/api/resources/intune-devices-manageddevice?view=graph-rest-beta#properties)
| Property              | Type   | Description|
| --------------------- | ------ | ------------------------------------------------------------------------ |
| enrollmentProfileName | String | Name of the enrollment profile assigned to the device. Default value is empty string, indicating no enrollment profile was assgined. This property is read-only.|
| autopilotEnrolled     | Boolean | Reports if the managed device is enrolled via auto-pilot. This property is read-only.|
 
---- 
 
## Follow ups 
 
  let's discuss criteria in a technical work meeting
 
---- 
 
 