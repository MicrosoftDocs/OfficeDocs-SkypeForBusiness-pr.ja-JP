---
title: PowerShell のサンプル スクリプト - メッセージング ポリシー&を作成する
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: この PowerShell スクリプトを使用して、メッセージング ポリシーを Teams作成し、組織内のユーザーに割り当てる必要があります。
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
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="d2d40-103">PowerShell サンプル スクリプト - メッセージング ポリシーの作成と割り当て</span><span class="sxs-lookup"><span data-stu-id="d2d40-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="d2d40-104">この PowerShell スクリプトを使用して、メッセージング ポリシーを作成し、Microsoft Teamsに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="d2d40-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="d2d40-105">この PowerShell スクリプトの使用の詳細については、「クイック スタート - Teams for Education 」[を参照してください](../teams-quick-start-edu.yml)。</span><span class="sxs-lookup"><span data-stu-id="d2d40-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](../teams-quick-start-edu.yml).</span></span>

<span data-ttu-id="d2d40-106">このスクリプトでは、オンライン PowerShell モジュールの一覧にある[Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy)コマンドレットSkype for Business使用します。</span><span class="sxs-lookup"><span data-stu-id="d2d40-106">This script uses the [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="d2d40-107">PowerShell [Teams管理の詳細については、「PowerShell](../teams-powershell-overview.md)の概要」Teams参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2d40-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="d2d40-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="d2d40-108">Before you start</span></span>

<span data-ttu-id="d2d40-109">Skype for Business Online PowerShell モジュール をダウンロード[してインストールし](https://www.microsoft.com/download/details.aspx?id=39366)、メッセージが表示されたらコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d2d40-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="d2d40-110">さらに詳しくは[、「PowerShell を使用して Skype for Business Online を管理する」Office 365してください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d2d40-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="d2d40-111">サンプル スクリプト</span><span class="sxs-lookup"><span data-stu-id="d2d40-111">Sample script</span></span>

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
> <span data-ttu-id="d2d40-112">また、バッチ ポリシーの割り当てによって、またはユーザーがメンバーであるグループに大規模なメッセージング ポリシーを直接ユーザーに割り当てすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d2d40-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="d2d40-113">詳細については、「学校の大規模なユーザーに[ポリシー](../batch-group-policy-assignment-edu.md)を割り当てる」と「グループ内のユーザーにポリシーを割り当てる[」をTeams。](../assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d2d40-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>