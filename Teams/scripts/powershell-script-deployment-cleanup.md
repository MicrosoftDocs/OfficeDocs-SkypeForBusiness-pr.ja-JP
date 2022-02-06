---
title: PowerShell のサンプル スクリプト - Teamsクリーンアップ
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、Teamsをアンインストールし、ユーザー Teamsフォルダーを削除します。
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: 'NOINDEX, NOFOLLOW'
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell のサンプル スクリプト - Teamsのクリーンアップ

このスクリプトを使用して、このスクリプトをTeams。 このスクリプトは、Teamsをアンインストールし、ユーザー Teamsフォルダーを削除します。 コンピューターにインストールされたユーザー プロファイルごとにTeamsスクリプトを実行します。


## <a name="sample-script"></a>サンプル スクリプト

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

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
- [新しいTeamsを使用Microsoft 365 Apps](/deployoffice/teams-install)
