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
ms.openlocfilehash: 07efc7b86045de9e76669d4ffbf185aba9d94d1f
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236807"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="48745-103">PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て</span><span class="sxs-lookup"><span data-stu-id="48745-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="48745-104">この PowerShell スクリプトを使用して、Microsoft Teams でメッセージングポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="48745-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="48745-105">この PowerShell スクリプトの使い方について詳しくは、「[クイックスタート-教育機関向けチーム](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="48745-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="48745-106">PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="48745-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="48745-107">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="48745-107">Sample script</span></span>

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


