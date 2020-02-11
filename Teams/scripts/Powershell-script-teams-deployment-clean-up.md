---
title: Microsoft Teams の展開のクリーン アップを支援する PowerShell スクリプトのサンプル
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
audience: admin
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: この PowerShell スクリプトを使用して、対象のコンピューターまたは特定のユーザーに対して Microsoft Teams をクリーンアップします。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.openlocfilehash: c02b918d0fe3d686266fd385a5378e47d98e2508
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888256"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>PowerShell スクリプトのサンプル-Microsoft Teams の展開クリーンアップ
-------------------------------------------------------------------------

この PowerShell スクリプトは、ターゲットコンピューターまたはユーザーから Microsoft Teams をクリーンアップするために活用できます。 ターゲットコンピューター上のすべてのユーザーに対して実行する必要があります。 


## <a name="sample-script"></a>サンプル スクリプト

```powershell
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
        Remove-Item -Path $TeamsPath -Recurse
                    
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
```


