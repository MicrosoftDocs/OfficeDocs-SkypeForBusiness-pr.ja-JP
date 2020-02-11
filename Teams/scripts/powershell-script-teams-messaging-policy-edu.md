---
title: PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、Teams でメッセージングポリシーを作成し、組織内のユーザーに割り当てます。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b45eef7792ce9c0930c9e78249259caedb325c5
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888746"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て
-------------------------------------------------------------------------

この PowerShell スクリプトを使用して、Microsoft Teams でメッセージングポリシーを作成し、ユーザーに割り当てます。 

この PowerShell スクリプトの使い方について詳しくは、「[クイックスタート-教育機関向けチーム](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)」をご覧ください。

PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。


## <a name="sample-script"></a>サンプル スクリプト

```powershell
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
```


