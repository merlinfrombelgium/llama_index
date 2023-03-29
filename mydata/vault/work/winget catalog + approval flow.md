
```ad-abstract
title: Idea

- Present winget repo (public/private) as software catalog to users.
- Upon approval, publish app through Intune
- Watch magic unfold

```

[winget-cli-restsource/new-winget-rest-source-azure.md at main · microsoft/winget-cli-restsource · GitHub](https://github.com/microsoft/winget-cli-restsource/blob/main/Tools/PowershellModule/doc/new-winget-rest-source-azure.md)

[Hosting your own WinGet private repository - Info Support Blog](https://blogs.infosupport.com/hosting-your-own-winget-private-repository/)
[Adding a package to your private WinGet.RestSource feed using its API - Info Support Blog](https://blogs.infosupport.com/adding-a-package-to-your-private-winget-restsource-feed-using-its-api/)

[winget.run | Finding winget packages made simple.](https://winget.run/)
[Winget private repository hosting / REST API](https://winget.pro/)

[[Get winning with winget private repositories#Convert winget output to table]]

[jdhitsolutions/WingetTools: A set of PowerShell tools for working with the winget package manager. (github.com)](https://github.com/jdhitsolutions/WingetTools)

Winget in Sandbox:
1. Download https://github.com/microsoft/winget-cli/releases/download/v1.4.10173/Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle
2. Download [aka.ms](https://aka.ms/Microsoft.VCLibs.x64.14.00.Desktop.appx)
3. Copy packages to sandbox desktop
4. Add-AppxPackage -Path .\Desktop\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle -InstallAllResources -DependencyPath .\Desktop\Microsoft.VCLibs.x64.14.00.Desktop.appx
