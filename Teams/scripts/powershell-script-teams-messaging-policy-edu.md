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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 108272636925daadfb361c1e79ff14b9c04f514a
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021859"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="0a615-103">PowerShell スクリプトのサンプルを作成し、メッセージング ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0a615-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="0a615-104">この PowerShell スクリプトを使用して、マイクロソフトのチームでのメッセージング ポリシーを作成し、ユーザーに割り当てることにします。</span><span class="sxs-lookup"><span data-stu-id="0a615-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="0a615-105">この PowerShell スクリプトを使用しての詳細については、[教育用のクイック ・ スタート ・ チーム](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a615-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="0a615-106">PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0a615-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="0a615-107">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="0a615-107">Sample script</span></span>

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


