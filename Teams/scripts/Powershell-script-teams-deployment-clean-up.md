---
title: Microsoft Teams の展開のクリーン アップを支援する PowerShell スクリプトのサンプル
ms.reviewer: ''
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: この PowerShell スクリプトを使用して、対象のマシン上の、または特定のユーザーの Microsoft Teams をクリーン アップします。
localization_priority: Normal
ms.openlocfilehash: a047326a1598ea497318b77ce27c09c6807f25dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201680"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>PowerShell スクリプトのサンプル - Microsoft Teams の展開のクリーン アップ
-------------------------------------------------------------------------

この PowerShell スクリプトは、対象のマシンまたはユーザーから Microsoft Teams をクリーンアップするために利用することができます。 これは、対象のマシン上のユーザーそれぞれについて、実行する必要があります。 


## <a name="sample-script"></a>サンプル スクリプト

````powershell
<#
.SYNOPSIS
This script allows you to uninstall the Microsoft Teams app and remove Teams directory for a user.
.DESCRIPTION
Use this script to clear the installed Microsoft Teams application. Run this PowerShell script for each user profile for which the Teams App was installed on a machine. After the PowerShell has executed on all user profiles, Teams can be redeployed.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if (Test-Path -Path $TeamsUpdateExePath) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process -FilePath $TeamsUpdateExePath -ArgumentList "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    if (Test-Path -Path $TeamsPath) {
        Write-Host "Deleting Teams directory"
        Remove-Item –Path $TeamsPath -Recurse
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
````


