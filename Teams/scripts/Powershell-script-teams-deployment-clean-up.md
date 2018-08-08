---
title: PowerShell スクリプトのサンプルをクリーンアップをマイクロソフト チームの展開を支援します。
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: ターゲット マシン上または特定のユーザーに対して、マイクロソフトのチームをクリーンアップするには、この PowerShell スクリプトを使用します。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e159c06a27151523e52db5bf7e0aa2eab33620a9
ms.sourcegitcommit: dba47a65b0725806c98702bb7362a1b105cc93df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "21249193"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="eb1e8-103">PowerShell スクリプトのサンプルをマイクロソフトのチームの配置のクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="eb1e8-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="eb1e8-104">この PowerShell スクリプトは、ターゲット コンピューターまたはユーザーからマイクロソフトのチームのクリーンアップを活用できます。</span><span class="sxs-lookup"><span data-stu-id="eb1e8-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="eb1e8-105">対象となるコンピューター上のすべてのユーザーのアクティビティが実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb1e8-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="eb1e8-106">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="eb1e8-106">Sample script</span></span>

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


