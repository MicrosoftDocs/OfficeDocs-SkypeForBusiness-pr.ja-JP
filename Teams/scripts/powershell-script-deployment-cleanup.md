---
title: PowerShell スクリプト サンプル - Teams展開のクリーンアップ
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、Teamsをアンインストールし、ユーザーのTeams フォルダーを削除します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 246c47b74fc90ddfb7b38a0474bc88bff5321559
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402651"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell スクリプト サンプル - Teamsデプロイのクリーンアップ

このスクリプトを使用してTeamsを削除します。 このスクリプトは、Teamsをアンインストールし、ユーザーのTeams フォルダーを削除します。 Teamsがコンピューターにインストールされたユーザー プロファイルごとに、このスクリプトを実行します。


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
- [Microsoft 365 Appsを使用してTeamsをデプロイする](/deployoffice/teams-install)
