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
ms.openlocfilehash: f6e6f54bb1e0a4098994f4fb17b167f8ae02dd70
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827585"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>PowerShell スクリプトのサンプル-Microsoft Teams の展開クリーンアップ
-------------------------------------------------------------------------

この PowerShell スクリプトは、ターゲットコンピューターまたはユーザーから Microsoft Teams をクリーンアップするために活用できます。 ターゲットコンピューター上のすべてのユーザーに対して実行する必要があります。 


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
        Remove-Item -Path $TeamsPath -Recurse
                    
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
````


