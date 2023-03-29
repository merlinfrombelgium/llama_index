
## Welcome to Microsoft Windows 365!

Windows 365 is a cloud service that lets you access your personal Windows desktop from any device. We have assigned you a license to trial this service. This is a guide to getting started quickly.

The proof of concept at UCB is only available in the DEV environment. This means you will be able to log on to office.com or through the Microsoft 365 apps (Outlook, Teams, ...) using your regular UCB account. This allows you to test Windows 365 as a daily driver for your general office activities.

You will NOT be able to access any of the backend services or platforms, or network drives of UCB directly. This may be part of a future phase of evaluation of Windows 365, which would then integrate with the ACC and PROD environments of UCB.

## Getting started

1. First, make sure you have your DEV credentials.
	- If you need to reset your password, use [this link]([Security - Password Set/Reset or Account Unlock Request (onbmc.com)](https://ucb-dwp.onbmc.com/dwp/app/#/srm/profile/SRGAA5V0F4E83AO08M5MAOFKSVQ5K0/srm))
	- If your DEV account does not exist in Azure (yet), please [submit a request](https://ucb-dwp.onbmc.com/dwp/app/#/srm/profile/SRGAA5V0F7JC4AP48Y0XP3MBGDQN34/srm) through My IT, as per the below example:
	  ![[Pasted image 20230302155508.png]]
	  
2. To access your Windows 365 Cloud PC, you need to install the Windows 365 app
	   
>[!hint]
>If you can't install the app for some reason, or you're using someone else's computer, you can always access your cloud pc through [the Windows 365 website](https://windows365.microsoft.com)

- On a Windows device, get the Windows 365 app from the [Microsoft Store](https://apps.microsoft.com/store/detail/windows-365-preview/9N1F85V9T8BN)
- Open the app and enter your DEV credentials
- You can now manage and connect to your cloud pc(s)
	  ![[Pasted image 20230223170921.png]]


## Additional features

1. Restarting a Cloud PC from the Windows 365 app: 

	1. Open the Windows 365 app on your device. 
	2. Select the Cloud PC tab at the bottom of the screen. 
	3. Find your Cloud PC in the list and select it. 
	4. Select Restart from the top right corner of the screen and confirm your action by selecting Restart again in the pop-up window that appears. 

2. Restoring a Cloud PC from the Windows 365 app: 

	1. Open the Windows 365 app on your device. 
	2. Select the Cloud PC tab at the bottom of the screen. 
	3. Find your Cloud PC in the list and select it. 
	4. Select Restore from top right corner

### Troubleshooting

##### Authentication issue with error MSIS5000 or similar

Your device may be managed by another organization. Check with your IT administrator if this is the case. If you have privileged access to your device's settings, you may want to try and delete any conflicting certificates in the Local Certificate Manager. To do this, open ```certmgr.msc``` from the Windows Run prompt (Win + R) and expand into ```Personal > Certificates```. Now check for any certificates which contain Device Certificate 