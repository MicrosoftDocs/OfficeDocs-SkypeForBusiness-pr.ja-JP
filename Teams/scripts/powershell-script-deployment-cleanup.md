---
title: PowerShell スクリプトのサンプル - Teams 展開のクリーンアップ
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して Teams をアンインストールし、ユーザーの Teams フォルダーを削除します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4b0bac09e18a9c6378623066889d6b1a891a4a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809487"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell スクリプトのサンプル - Teams の展開のクリーンアップ

Teams を削除するには、このスクリプトを使用します。 このスクリプトは Teams をアンインストールし、ユーザーの Teams フォルダーを削除します。 Teams がコンピューターにインストールされた各ユーザー プロファイルに対して、このスクリプトを実行します。


## <a name="sample-script"></a>サンプル スクリプト

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
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

## <a name="related-topics"></a>関連項目

- [Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする](../msi-deployment.md)
- [Microsoft 365 アプリで Teams を展開する](https://docs.microsoft.com/deployoffice/teams-install)
