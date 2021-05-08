---
title: PowerShell スクリプト サンプル - エクスポート マネージャーとその担当者
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: brandber
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、各マネージャーのチームをチーム メンバーとして作成する準備として、組織のマネージャーとその担当者のリストをエクスポートします。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7f2217bc39ead0abec48dafb75ff3f846681f20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117315"
---
# <a name="powershell-script-sample---export-managers-and-their-directs"></a><span data-ttu-id="485dd-103">PowerShell スクリプト サンプル - エクスポート マネージャーとその担当者</span><span class="sxs-lookup"><span data-stu-id="485dd-103">PowerShell script sample - Export managers and their directs</span></span>

<span data-ttu-id="485dd-104">この PowerShell スクリプトを使用して、組織のマネージャーとその担当者のリストをエクスポートし、チーム メンバーとして各マネージャーの People Manager チームを作成する準備をします。</span><span class="sxs-lookup"><span data-stu-id="485dd-104">Use this PowerShell script to export a list of managers and their directs for your organization, in preparation for creating a people manager team for each manager with their directs as team members.</span></span>

<span data-ttu-id="485dd-105">この PowerShell スクリプトの詳細については、「People Manager チームを作成 [する」を参照してください](../create-manager-directs-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="485dd-105">To learn about this PowerShell script, read [Create people manager teams](../create-manager-directs-teams.md).</span></span>

<span data-ttu-id="485dd-106">PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="485dd-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="export-managers-script"></a><span data-ttu-id="485dd-107">Export-Managers スクリプト</span><span class="sxs-lookup"><span data-stu-id="485dd-107">Export-Managers script</span></span>

```powershell
<# 
.SYNOPSIS 
  Name: Export-ManagersDirectsFromAAD.ps1 
  The purpose of this sample script is to build a list of managers and direct reports to use with the New-TeamsFromManagers.ps1 to create a team for each people manager and their directs.
   
.DESCRIPTION 
 This sample script create new Teams based on the tab delimited .txt file you provide of managers and direct reports. It assumes that DisplayName is not null.
 
.NOTES 
  &copy; 2020 Microsoft Corporation. All rights reserved. This document is provided 
    "as-is." Information and views expressed in this document, including URL and 
    other Internet Web site references, may change without notice.
 
.EXAMPLE 
  Export-ManagersDirectsFromAAD.ps1
#> 

#Also create a type that validated the users licenses to ease the create-team burden
#also add checks to see if the types are appropriately in place.

#region Configurable Inputs
$OutputFile = "ExportedManagersDirects.txt"
#endregion

#region Data Model
class DirectReport {
    [string] $UserPrincipalName
}
class Manager {
    [ValidateNotNullOrEmpty()] [string] $UserPrincipalName
    [string] $DisplayName
    [System.Collections.ObjectModel.Collection[DirectReport]]$DirectReports

    Manager (){
        $this.DirectReports = New-Object -TypeName System.Collections.ObjectModel.Collection["DirectReport"]
    }
}
#endregion

#region Helper Functions
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}
#endregion

#region Script Execution
#Step 1: Retrieve AAD users - attribute filtering off DirectReport cannot be applied
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to retrieve ALL Azure AD users."
$AllAADUsers = Get-AzureADUser -All $true -Filter "UserType eq 'Member' and AccountEnabled eq true"
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Azure AD Users Complete.. `n"

#Step 2: Iterate through users, identify Managers and Directs
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to Retrieve Directs Reports"
$Managers = New-Object -TypeName System.Collections.ObjectModel.Collection["Manager"]
foreach ($user in $AllAADUsers) {
    $directs = Get-AzureADUserDirectReport -ObjectId $user.UserPrincipalName
        if ($null -ne $directs) {
            if ($user.DisplayName -ne "") {
                $manager = New-Object -TypeName Manager
                $manager.UserPrincipalName = $user.UserPrincipalName
                $manager.DisplayName = $user.DisplayName

                foreach ($direct in $directs) {
                    $directReport = New-Object -TypeName DirectReport
                    $directReport.UserPrincipalName = $direct.UserPrincipalName
                    $manager.DirectReports.Add($directReport)
                }
                $Managers.Add($manager)
                
            }
        Write-Host "$(Get-Timestamp) Info: Added Manager: $($manager.UserPrincipalName)"
        $i++
    }
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Direct Reports Complete.. `n"

#Step 3: Output in tab delimited .txt format
$output = New-Object -TypeName System.Collections.ObjectModel.Collection["String"]
$header = "Name`tDisplayName`tDirects"
$output.Add($header)

foreach ($manager in $Managers) {
    [string] $directs = ""
    foreach ($direct in $manager.DirectReports)
    {
        $directs += $direct.UserPrincipalName + ','
    }
    $directs = $directs.Substring(0,$directs.Length-1)
    $row = "$($manager.UserPrincipalName)`t$($manager.DisplayName)`t$($directs)"
    $output.Add($row) 
}

#If Output File already exists from a previous run, it will be replaced.
$testPath = Test-Path .\$($OutputFile)
if ($testPath) {
    Remove-Item .\$($OutputFile)
}

foreach ($line in $output) {
    $line | Out-File -FilePath .\$($OutputFile) -Append
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Exported tab delimited output to $($OutputFile). `n"
#endregion



```