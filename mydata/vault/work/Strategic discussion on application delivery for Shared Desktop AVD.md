# 1/18/2023 2pm - 3.30pm

## Topic
To discuss and agree on app delivery methods for AVD.
 
## Participants 
 
  
 
---- 
 
## Preparation 
 
## Current situation
There is no app delivery method. All apps are included in the AVD shared desktop image. At the moment, the list of applications is as follows:

```csvtable
source: winget-list.csv
```



## Preparation
>[!Question]
>- What's the process for licensed apps (Snagit)?

From Azure Virtual Desktop (CBWS) Administrator Guide (v2.0):
![[Pasted image 20230118114136.png]]  

[Azure Virtual Desktop (AVD) Application Management - Nerdio (getnerdio.com)](https://getnerdio.com/academy/all-about-application-management-in-azure-virtual-desktop-avd/)
![[Pasted image 20230118141614.png]]

-   [List of Azure Virtual Desktop Installation Applications](https://getnerdio.com/academy/all-about-application-management-in-azure-virtual-desktop-avd/#h-list-of-azure-virtual-desktop-installation-applications)
    
    -   [1. Manual Install On Image](https://getnerdio.com/academy/all-about-application-management-in-azure-virtual-desktop-avd/#elementor-toc__heading-anchor-2) 
        
    -   [2. Scripted Action Install On Image](https://getnerdio.com/academy/all-about-application-management-in-azure-virtual-desktop-avd/#elementor-toc__heading-anchor-3) 
        
    -   [3. MEM Install On Image](https://getnerdio.com/academy/all-about-application-management-in-azure-virtual-desktop-avd/#elementor-toc__heading-anchor-4) 
        
    -   [4. Scripted Action Install On Session Hosts](https://getnerdio.com/academy/all-about-application-management-in-azure-virtual-desktop-avd/#elementor-toc__heading-anchor-5) 
        
    -   [5. MEM Install On Session Hosts](https://getnerdio.com/academy/all-about-application-management-in-azure-virtual-desktop-avd/#elementor-toc__heading-anchor-6)
 
---- 
 
## Notes 
 
- [[Ralph]] first external user expected mid-February
- [[Prasad]] 
	- let's aim for similar SLA as desktop apps
	- hosts can't be rebooted 3x per day
- [[Ralph]] approach for the first 4 weeks?
	- what is best cost-wise, manageability wise, ...
- [[Merlijn]] what about installations in user context? (MS Store, downloads, winget)
	- [[Joeri]] "user context" on shared VDI is not individual and not recommended
	- [[Merlijn]] how should we manage/control user-installed apps?
 - [[Rene]] presents [PPTX](https://ucb.sharepoint.com/:p:/r/teams/Project_Desktop_as_a_Service/Shared%20Documents/General/DAAS-Application%20Management%20v1.0F.pptx?d=w3bd4c8c3e5ce4ab5b631e34ab3602dfe&csf=1&web=1&e=BDmbt9)
	 - Option 1: multiple images and host pools
	 - Option 2: MSIX App Attach
	 - Option 3: FSLogix App Masking
	 - Option 4: Nerdio installed apps mgmt
 - [[Merlijn]] does the packaging team have MSIX packaging experience?
	 - [[Prasad]] [[Showreddy]] some, but was not a successful approach
 - [[Joeri]] recommends to use FS Logix masking + Nerdio Installed Apps mgmt
 - [[Prasad]] AVD hosts are managed through Intune already (device-targeted)
 - [[Ralph]] suggests
	 - to compare core software list on laptops with the VDI image
		 - Let's pick a few apps to include in the core VDI image
		   https://ucb-source-cd.veevavault.com/ui/#doc_info/506815/9/0		   ![[Pasted image 20230118150134.png]]
		   
	 - to test Nerdio IAM asap
		 - [[Merlijn]] to organize with [[Joeri]] and one of [[Rene]], [[Prasad]], [[Showreddy]]
		 - First, Nerdio permissions need to be restored (meeting next Friday: [[Nerdio Broken - Clarification]])
		 -
[[Rene]] personal/dedicated hosts are perhaps the desired approach
	[[Ralph]]
	- at this time, not an option (business decision)
	- Expectation to have 200-300 personal desktops, but 2000-3000 users on shared desktop
---- 
 
## Follow ups 
 
  - [[Ralph]] work on 3 streams
	  - Try to match the core VDI image with the core list of laptop applications > Prasad
		  - should fix 95% of expected app requests
	  - Work on Nerdio IAM + FSLogix masking > Merlijn 
	  - Work on SAP client to be installed/working in shared VDI > Prasad
 - Have weekly technical meetings
 - [[Rene]] What about
	 - licensed apps?
	 - apps with backend dependencies (DB, etc.)
 - [[Sebastian]] work started on [KB articles](https://teams.microsoft.com/l/entity/26bc2873-6023-480c-a11b-76b66605ce8c/_djb2_msteams_prefix_1128389639?context=%7B%22subEntityId%22%3Anull%2C%22channelId%22%3A%2219%3A690a3f3f99e849c0883d7a16e99fcfe1%40thread.tacv2%22%7D&groupId=466563d9-9ebf-46ec-abcd-35ec0b480c03&tenantId=237582ad-3eab-4d44-8688-06ca9f2e613b&allowXTenantAccess=false)
 - Follow-up meeting Friday, Jan 27
---- 
 
 