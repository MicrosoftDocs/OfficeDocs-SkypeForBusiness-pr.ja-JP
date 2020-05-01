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
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951062"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="75062-103">PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て</span><span class="sxs-lookup"><span data-stu-id="75062-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="75062-104">この PowerShell スクリプトを使用して、Microsoft Teams でメッセージングポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="75062-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="75062-105">この PowerShell スクリプトの使い方について詳しくは、「[クイックスタート-教育機関向けチーム](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="75062-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="75062-106">このスクリプトは、Skype for Business Online PowerShell モジュールの[Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="75062-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="75062-107">PowerShell を使用したチーム管理の詳細については、「 [Teams PowerShell の概要](../teams-powershell-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75062-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="75062-108">始める前に</span><span class="sxs-lookup"><span data-stu-id="75062-108">Before you start</span></span>

<span data-ttu-id="75062-109">[Skype For Business Online PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366)をダウンロードしてインストールし、メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="75062-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="75062-110">詳細については、「 [Office 365 PowerShell を使って Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75062-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>


## <a name="sample-script"></a><span data-ttu-id="75062-111">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="75062-111">Sample script</span></span>

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

> [!NOTE]
> <span data-ttu-id="75062-112">また、バッチポリシーの割り当てを使用して、メッセージングポリシーを多数のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="75062-112">You can also use batch policy assignment to assign a messaging policy to large sets of users.</span></span> <span data-ttu-id="75062-113">詳細については、「[学校の多数のユーザーにポリシーを割り当て](../batch-policy-assignment-edu.md)、 [Teams のユーザーにポリシーを割り当てる](../assign-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75062-113">For more information see [Assign policies to large sets of users in your school](../batch-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
