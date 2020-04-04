---
title: PowerShell スクリプトのサンプル-メッセージポリシーの作成 & 割り当てる
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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffd564d421c07503fe5e19ace8f24a0379418b74
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140980"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="e0f44-103">PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て</span><span class="sxs-lookup"><span data-stu-id="e0f44-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="e0f44-104">この PowerShell スクリプトを使用して、Microsoft Teams でメッセージングポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e0f44-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="e0f44-105">この PowerShell スクリプトの使い方について詳しくは、「[クイックスタート-教育機関向けチーム](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0f44-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="e0f44-106">PowerShell をこれまでに使用したことがなく、使用開始のためのヘルプが必要な場合は、「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0f44-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="before-you-start"></a><span data-ttu-id="e0f44-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="e0f44-107">Before you start</span></span>
<span data-ttu-id="e0f44-108">[Skype For Business Online Connector モジュール](https://www.microsoft.com/download/details.aspx?id=39366)をダウンロードしてインストールし、メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e0f44-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="e0f44-109">詳細については、「 [Office 365 PowerShell で Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f44-109">View [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) for more.</span></span>


## <a name="sample-script"></a><span data-ttu-id="e0f44-110">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="e0f44-110">Sample script</span></span>

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


