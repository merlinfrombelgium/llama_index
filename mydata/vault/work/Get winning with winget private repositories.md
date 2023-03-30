
**Description:** winget is great as a software catalogue with prepackaged applications. But if you're looking to distribute licensed apps, you're left in the cold. And in Intune, you can't even get apps from the community-curated repository! Learn how to take matters in your own hands and create and manage a private repository. 
  
**What you will learn:  
- Can we distribute licensed and LOB apps?
- Curate (white-list) the available apps in your repo.  
- Pros and cons of the private repo.  
- 
  
**Primary Category:** Endpoint Management  
  
Additional Categories:["Windows 10\\11"]  
Session Type: Deep dive  
Email Address: [Merlinfrombelgium@gmail.com](mailto:Merlinfrombelgium@gmail.com)  
Name: Merlijn Van Waeyenberghe  
  
Requestd Co-Speaker:  
Requestd Co-Speaker Email:  
  
Additional Comments: As this session deals with early-release code and issues, and the Intune integration with winget is in preview at time of writing, content and advice may change between now and May.  
Submitted (UTC):   
  
Bio:Consultant @itsobvus | #Intune #ConfigMgr expert | #PowerShell #PowerPlatform addict | #community speaker | globe-trotter | CPL(H) #HelicopterPilot | biker | VR/XR enthousiast

### Convert winget output to table

```PowerShell
class WingetListItem
{
    [string]$Name
    [string]$Id
    [string]$Version
    [string]$AvailableSource
}

function ConvertWingetListToTable()
{
    $wingetList = winget list
    $wingetListItems = @()
    foreach ($item in $wingetList) {
        if ($item -match "^(\S+)\s+(\S+)\s+(\S+)\s+(\S+)$") {
            $wingetListItems += [WingetListItem]@{
                Name = $matches[1]
                Id = $matches[2]
                Version = $matches[3]
                AvailableSource = $matches[4]
            }
        }
    }
    $wingetListItems | Format-Table Name, Id, Version, AvailableSource -AutoSize
}```

### Prompt for selection using WinForms
[Under The Stairs: Windows Forms - working in PowerShell 7 Preview2 (tfl09.blogspot.com)](https://tfl09.blogspot.com/2019/07/windows-forms-working-in-powershell-7.html)

```PowerShell
Add-Type -Assembly System.Windows.Forms

# Create a multi-select list box
$form = New-Object System.Windows.Forms.Form
$form.Text = "Winget List"
$form.Size = New-Object System.Drawing.Size(300,250)

$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Size = New-Object System.Drawing.Size(280, 200)
$listBox.SelectionMode = [System.Windows.Forms.SelectionMode]::MultiExtended

# Populate the list box with the winget list items
foreach ($item in $wingetListItems) {
    $listBox.Items.Add($item.Name)
}

$form.Controls.Add($listBox)

# Create a button to confirm the selection
$okButton = New-Object System.Windows.Forms.Button
$okButton.Text = "OK"
$okButton.Location = New-Object System.Drawing.Size(215, 210)
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

# Show the form
$result = $form.ShowDialog()

# If the OK button was clicked, return the selected items
if ($result -eq [System.Windows.Forms.DialogResult]::OK) {
    $selectedItems = @()
    foreach ($index in $listBox.SelectedIndices) {
        $selectedItems += $wingetListItems[$index]
    }
    $selectedItems
}

```

[jdhitsolutions/WingetTools: A set of PowerShell tools for working with the winget package manager. (github.com)](https://github.com/jdhitsolutions/WingetTools)