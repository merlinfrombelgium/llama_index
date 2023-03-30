## ... with a little help from our friends

PS 5 <> PS 7
wmi <> cim
convert through GPT?

[Get-WmiObject - PowerShell - SS64.com](https://ss64.com/ps/get-wmiobject.html)
## Get-WmiObject is **deprecated** in PowerShell 3.0 and above.

> The preferred cmdlet is now [Get-CIMInstance -Classname](https://ss64.com/ps/get-ciminstance.html) …
> 
> Run [Get-cimclass](https://ss64.com/ps/get-cimclass.html) to discover the new property names.
> 
> Basic [speed comparison](https://maikkoster.com/cim-vs-wmi-cmdlets-the-top-reasons-i-changed/) testing shows that CIM is significantly faster:
> 
> WMI: **35**.4 seconds.  
> CIM:    **2**.5 seconds.

==[CIM vs. WMI CmdLets – The top reasons I changed over – GivingSomethingBack (maikkoster.com)](https://maikkoster.com/cim-vs-wmi-cmdlets-the-top-reasons-i-changed/)

==[PowerShell CIM CmdLets – Working with embedded or keyless classes – GivingSomethingBack (maikkoster.com)](https://maikkoster.com/powershell-cim-cmdlets-working-with-embedded-or-keyless-classes/)
```
$Session = New-CimSession -ComputerName CM01
$LocalizedSettings= New-Object CimInstance $Session.GetClass("root\sms\site_TST", "SMS_Category_LocalizedProperties")

$LocalizedSettings.CategoryInstanceName = "Test Category"
$LocalizedSettings.LocaleID = 1033
```


[(4) Why do people say WMI is being deprecated? : PowerShell (reddit.com)](https://www.reddit.com/r/PowerShell/comments/t902o9/why_do_people_say_wmi_is_being_deprecated/)
> cause 99.99999% of the time I can literally replace the `Get-WmiObject` part with `Get-CimInstance` and carry on
> 
> the hard part with CIM is the methods and invoking those methods, that's called differently and at times harder to deal with

> The gist is that:
> 
> -   WMI opens too many ports
>     
> -   It uses a less secure method of authentication (this is the most important one)
>     
> -   Even if you do open high ports for WMI, you'll end up having to open WinRM ports anyway for other modern tools and PS in general
>     
> 
> I would really, really just recommend moving entirely to the CIM cmdlets, even in your older environments. It's faster, it's more user friendly, and when necessary it can use DCOM via a session parameter anyway.


[(4) Help converting deprecated WMI based Windows Powershell to Powershell core script : PowerShell (reddit.com)](https://www.reddit.com/r/PowerShell/comments/vo4s1u/help_converting_deprecated_wmi_based_windows/)

[WMI Data Types - powershell.one](https://powershell.one/wmi/datatypes)

