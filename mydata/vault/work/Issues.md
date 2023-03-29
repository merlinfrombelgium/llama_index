Error CAA20004 upon discovering AVD through RD Client with UPN
[CAA20004 - AADSTS65005 - The app needs access to a service - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/azure-virtual-desktop/caa20004-aadsts65005-the-app-needs-access-to-a-service/m-p/1403787)

1.  Open a browser and begin the admin consent flow to the Windows Virtual Desktop server app.  [https://login.microsoftonline.com/common/adminconsent?client_id=5a0aa725-4958-4b0c-80a9-34562e23f3b7...](https://login.microsoftonline.com/common/adminconsent?client_id=5a0aa725-4958-4b0c-80a9-34562e23f3b7&redirect_uri=https%3A%2F%2Frdweb.wvd.microsoft.com%2FRDWeb%2FConsentCallback)
2.  Sign in to the Windows Virtual Desktop consent page with a global administrator account.
3.  Click Accept
4.  Wait a minute for Azure AD to record consent
5.  Open a browser and begin the admin consent flow to the Windows Virtual Desktop client app. [https://login.microsoftonline.com/common/adminconsent?client_id=fa4345a4-a730-4230-84a8-7d9651b86739...](https://login.microsoftonline.com/common/adminconsent?client_id=fa4345a4-a730-4230-84a8-7d9651b86739&redirect_uri=https%3A%2F%2Frdweb.wvd.microsoft.com%2FRDWeb%2FConsentCallback)
6.  Sign in to the Windows Virtual Desktop consent page as global administrator, as you did in step 2
7.  Select Accept