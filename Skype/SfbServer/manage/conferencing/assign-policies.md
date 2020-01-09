---
title: Skype for Business Server で会議のポリシーを割り当てる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '概要: Skype for Business Server で会議ポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: f5e88e14c9516785cb3c45b5682bac13865b20ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991912"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="9dc58-103">Skype for Business Server で会議のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9dc58-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="9dc58-104">**概要:** Skype for Business Server で会議ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9dc58-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="9dc58-105">Skype for Business Server 管理シェルと**Grant-set-csconferencingpolicy**コマンドレットを使用して、ユーザーに会議ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9dc58-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9dc58-106">Skype for Business Server 管理シェルを使用して会議のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9dc58-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9dc58-107">次の例では、SalesConferencingPolicy というポリシーを、"Ken Myer" という Identity のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9dc58-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="9dc58-p101">次の例では、会議ポリシー FinanceConferencingPolicy を、Finance という組織単位にアカウントがあるすべてのユーザーに割り当てます。同じポリシーを特定の組織単位 (OU) のすべてのユーザーに割り当てるため、Get-CsUser コマンドレットを使用して、その OU のすべてのアカウントを取得します。ユーザー アカウントを取得したら、次にその情報を Grant-CsConferencingPolicy コマンドレットにパイプ処理し、ポリシー FinanceConferencingPolicy をコレクション内の各ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9dc58-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="9dc58-111">完全な構文とパラメーターの一覧を含む詳細については、「 [Grant-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc58-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

