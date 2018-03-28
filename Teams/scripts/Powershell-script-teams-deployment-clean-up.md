---
title: PowerShell スクリプトのサンプルをクリーンアップをマイクロソフト チームの展開を支援します。
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: この PowerShell スクリプトを使用して、会社全体にわたるパブリックなチームを Teams で作成します。
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1466a08d493538eadb6cd2bfc2f50ac15acb0fa7
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="23883-103">PowerShell スクリプトのサンプルをマイクロソフトのチームの配置のクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="23883-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="23883-104">この PowerShell スクリプトは、マイクロソフトのチームのクリーンアップを実行ターゲットの machines\users から活用できます。</span><span class="sxs-lookup"><span data-stu-id="23883-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines\users.</span></span> <span data-ttu-id="23883-105">対象となるコンピューター上のすべてのユーザーのアクティビティが実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23883-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="23883-106">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="23883-106">Sample script</span></span>

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
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````


