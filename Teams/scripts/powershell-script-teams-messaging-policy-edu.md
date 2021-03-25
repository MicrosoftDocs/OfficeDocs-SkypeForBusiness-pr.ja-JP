---
title: PowerShell スクリプトのサンプル - メッセージング &割り当てる
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、Teams でメッセージング ポリシーを作成し、組織内のユーザーに割り当てします。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117275"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="9e4c5-103">PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て</span><span class="sxs-lookup"><span data-stu-id="9e4c5-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="9e4c5-104">Microsoft Teams でメッセージング ポリシーを作成し、ユーザーに割り当てるには、この PowerShell スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="9e4c5-105">この PowerShell スクリプトの使用の詳細については、「クイック スタート [- Teams for Education」を参照してください](../teams-quick-start-edu.yml)。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](../teams-quick-start-edu.yml).</span></span>

<span data-ttu-id="9e4c5-106">このスクリプトでは、Skype for Business Online PowerShell モジュールにある [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-106">This script uses the [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="9e4c5-107">PowerShell [を使用した Teams の](../teams-powershell-overview.md) 管理の詳細については、Teams PowerShell の概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="9e4c5-108">始める前に</span><span class="sxs-lookup"><span data-stu-id="9e4c5-108">Before you start</span></span>

<span data-ttu-id="9e4c5-109">Skype for [Business Online PowerShell](https://www.microsoft.com/download/details.aspx?id=39366)モジュールをダウンロードしてインストールし、メッセージが表示されたらコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="9e4c5-110">さらに詳しくは [、「Skype for Business Online with Office 365 PowerShell」をご覧ください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="9e4c5-111">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="9e4c5-111">Sample script</span></span>

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
> <span data-ttu-id="9e4c5-112">また、バッチ ポリシーの割り当てまたはユーザーがメンバーであるグループに対して、大規模なメッセージング ポリシーをユーザーに直接割り当てすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="9e4c5-113">詳細については、「学校の大規模 [な](../batch-group-policy-assignment-edu.md) ユーザー セットにポリシーを割り当てる」および「Teams のユーザーにポリシーを割り当てる」 [を参照してください](../assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>