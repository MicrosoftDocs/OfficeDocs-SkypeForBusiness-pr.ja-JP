---
title: Microsoft Teams の展開のクリーン アップを支援する PowerShell スクリプトのサンプル
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
description: この PowerShell スクリプトを使用して、対象のマシン上の、または特定のユーザーの Microsoft Teams をクリーン アップします。
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
ms.openlocfilehash: 7a0d12fb59b8f5f513ed4f0c64502d6c9ff369e2
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011898"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="1fb93-103">PowerShell スクリプトのサンプル - Microsoft Teams の展開のクリーン アップ</span><span class="sxs-lookup"><span data-stu-id="1fb93-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="1fb93-104">この PowerShell スクリプトは、ターゲット コンピューターまたはユーザーからマイクロソフトのチームのクリーンアップを活用できます。</span><span class="sxs-lookup"><span data-stu-id="1fb93-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="1fb93-105">対象となるコンピューター上のすべてのユーザーのアクティビティが実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fb93-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="1fb93-106">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="1fb93-106">Sample script</span></span>

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


