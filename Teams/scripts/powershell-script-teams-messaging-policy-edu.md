---
title: PowerShell スクリプトのサンプルを作成し、メッセージング ポリシーを割り当てる
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: この PowerShell スクリプトを使用して、チームにメッセージング ポリシーを作成し、組織内のユーザーに割り当てることにします。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d65deff9f424fad8fed11d7b10cbe40ced387161
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463045"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell スクリプトのサンプルを作成し、メッセージング ポリシーを割り当てる
-------------------------------------------------------------------------

この PowerShell スクリプトを使用して、マイクロソフトのチームでのメッセージング ポリシーを作成し、ユーザーに割り当てることにします。 

この PowerShell スクリプトを使用しての詳細については、[教育用のクイック ・ スタート ・ チーム](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)を参照してください。

PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。


## <a name="sample-script"></a>サンプル スクリプト

````powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
````


