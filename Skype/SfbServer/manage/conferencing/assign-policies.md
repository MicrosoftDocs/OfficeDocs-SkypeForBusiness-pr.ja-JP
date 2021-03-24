---
title: Skype for Business サーバーで会議ポリシーを割り当てる
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '概要: Skype for Business サーバーで会議ポリシーを割り当てる方法の説明。'
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099163"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="527f2-103">Skype for Business サーバーで会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="527f2-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="527f2-104">**概要:** Skype for Business サーバーで会議ポリシーを割り当てる方法の説明。</span><span class="sxs-lookup"><span data-stu-id="527f2-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="527f2-105">会議ポリシーをユーザーに割り当てることができ、これを行うには Skype for Business Server 管理シェルと **Grant-CsConferencingPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="527f2-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="527f2-106">Skype for Business Server 管理シェルを使用して会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="527f2-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="527f2-107">次の例では、"Ken Myer" という ID を持つユーザーに、SalesConferencingPolicy というポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="527f2-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="527f2-108">その次の例では、組織部門 "Finance" のアカウントを持つすべてのユーザーに FinanceConferencingPolicy というポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="527f2-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="527f2-109">同じポリシーを特定の組織単位 (OU) のすべてのユーザーに割り当てるため、Get-CsUser コマンドレットを使用して、その OU のすべてのアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="527f2-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="527f2-110">ユーザー アカウントを取得したら、次にその情報を Grant-CsConferencingPolicy コマンドレットにパイプ処理し、ポリシー FinanceConferencingPolicy をコレクション内の各ユーザーに割り当てます:</span><span class="sxs-lookup"><span data-stu-id="527f2-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="527f2-111">完全な構文とパラメーターの一覧を含む詳細については、「[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="527f2-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
