# 1/27/2023  
 
## Participants 
 
 
[[Ralph]]
[[Joeri]]
[[Prasad]]
[[Showreddy]]
[[Suresh]]
[[Merlijn]]

 
---- 
 
## Preparation 
 
  Follow-ups from [[Strategic discussion on application delivery for Shared Desktop AVD]]
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
---- 
 
## Notes 
[[Merlijn]]
- overview of status
[[Joeri]] 
  - checking Nerdio if everything in place to match expectations
  - we need FSLogix + app masking (talk to IAM > [[Merlijn]])
  - we need a concrete plan on application deployments
[[Showreddy]] 
- operationally, maintenance on session hosts is very challenging as the business is involved
[[Ralph]]
- we need to have active involvement from the business 
 [[Joeri]] 
 - Nerdio can really help in this maintenance
 - but we need to find common ground with DCS and business (all stakeholders)
 [[Prasad]]
 - align on app delivery methods
	 - Intune is best candidate
[[Ralph]] 
- stick with what we have/what works
- collaborate with [[Joeri]] on all issues
[[Prasad]]
- progress on app deployment and user experience
[[Joeri]]
- work on adding apps in Intune (DEV) and test
[[Ralph]]
- keep track on status through [[file]]
- so we can report on what is in the image
[[Joeri]]
- mention if status is blocked and why
[[Showreddy]] / [[Prasad]] / [[Joeri]]
- scheduled task to update hosts every 8 hours
- discussion on using Intune to update image (pooled/shared)
	- image master (sandbox image) is not onboarded with Intune
		- provisioning this to production is a big pain atm (DCS involved)
		- aiming to have Nerdio do away with this overhead
	- we want to keep the image light-weight
	- working on "engineering" (fat) image with lots of apps
	   + ad hoc deployments through Intune
[[Ralph]]
- let's aim to meet 70-80% of expectations
- business expectations set that applications can take 1 week to arrive
- focus on making progress on apps coming 7-10 days
- official go-live 1 March
	- aim to be ready mid-February

---- 
 
## Follow ups 
 
-  Keep reaching out to [[Joeri]] for all issues/ideas/questions
-  Next follow-up meeting Friday Feb 3rd > [[Merlijn]] to schedule
---- 
 
 