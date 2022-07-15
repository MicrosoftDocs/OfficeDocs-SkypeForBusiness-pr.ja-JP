---
title: PowerShell スクリプト サンプル - Teams 展開のクリーンアップ
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して Teams をアンインストールし、ユーザーの Teams フォルダーを削除します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7875cb01b928567d5883f36e21eb2f0de0bccf6
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825691"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell スクリプト サンプル - Teams の展開クリーンアップ

このスクリプトを使用して Teams を削除します。 このスクリプトは Teams をアンインストールし、ユーザーの Teams フォルダーを削除します。 Teams がコンピューターにインストールされたユーザー プロファイルごとに、このスクリプトを実行します。


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
- [Microsoft 365 Appsを使用して Teams を展開する](/deployoffice/teams-install)
