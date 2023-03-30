- Provisioning is a one-time per user and per-license process.
- Any given user and license pair can only have one Cloud PC provisioned for them.
- When a user in the Azure AD user group is assigned a Windows 365 license, Windows 365 automatically provisions a Cloud PC for the user.
- The Windows 365 service always uses the first assigned policy to provision the Cloud PC.
- It’s not possible to trigger different provisioning policies for different user licenses. Users with multiple licenses will be provisioned multiple Cloud PCs using the same provisioning policy.
- If you remove the user’s license or targeted provisioning policy, their Cloud PC is moved into a seven-day grace period. This grace period allows for errors and reinstatement without affecting the user.
  https://learn.microsoft.com/en-us/windows-365/enterprise/lifecycle#deprovision