---
title: PowerShell スクリプトを使用して情報バリア モードを変更する
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
description: この PowerShell スクリプトは、情報バリアを展開した後に使用して、テナント内のすべてのグループのモードをオープンから暗黙的に更新します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3030f40ed61eb2e0e86967132d9575de8334a6c6
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767656"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>PowerShell スクリプトを使用して情報バリア モードを変更する

この PowerShell スクリプトを使用して、テナント内のすべてのTeams接続されたグループの情報バリア (IB) モードを更新します。 情報バリアを展開した後、これらのグループのモードを更新する必要があります。 IB を有効にする前にプロビジョニングされたグループには *、オープン* モードが割り当てられます。 *オープン* モードでは、該当する IB ポリシーはありません。 IB を有効にすると、 *作成* した新しいグループの既定のモードが暗黙的になります。 ただし、既存のグループは引き続き *オープン* モードの構成を維持します。 このスクリプトを実行して、これらの既存のグループを *暗黙的* モードに変更します。

このスクリプトでは、Exchange Online PowerShell モジュールにある [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) コマンドレットを使用してモードを更新します。 PowerShell を使用したTeamsの管理の詳細については、PowerShell [の概要Teams](./teams-powershell-overview.md)参照してください。

## <a name="sample-script"></a>サンプル スクリプト

このスクリプトを実行するには、テナントのグローバル管理者ロールが割り当てられている職場または学校アカウントを使用する必要があります。

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```