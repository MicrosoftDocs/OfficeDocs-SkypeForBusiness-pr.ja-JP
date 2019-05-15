---
title: Microsoft Teams の展開のクリーン アップを支援する PowerShell スクリプトのサンプル
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: ターゲット マシン上または特定のユーザーに対して、マイクロソフトのチームをクリーンアップするには、この PowerShell スクリプトを使用します。
localization_priority: Normal
ms.openlocfilehash: f89f35bb34ec3b72cfaec79c651b4c95d5e5bbdd
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "33993857"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>PowerShell スクリプトのサンプルをマイクロソフトのチームの配置のクリーンアップします。
-------------------------------------------------------------------------

この PowerShell スクリプトは、ターゲット コンピューターまたはユーザーからマイクロソフトのチームのクリーンアップを活用できます。 対象となるコンピューター上のすべてのユーザーのアクティビティが実行する必要があります。 


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


