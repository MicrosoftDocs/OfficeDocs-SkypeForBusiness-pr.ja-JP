---
title: Skype for Business Server 2015 での電話会議ポリシーの割り当て
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '概要: ビジネス サーバー 2015 の Skype での会議ポリシーを割り当てる方法を説明します。'
ms.openlocfilehash: 532065bee6f33b492639f5bcf949e29b082c5e84
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="assign-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="58d7c-103">Skype for Business Server 2015 での電話会議ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="58d7c-103">Assign conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="58d7c-104">**の概要:**ビジネス サーバー 2015 の Skype での会議ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58d7c-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="58d7c-105">Skype をビジネス サーバー管理シェルを**与える CsConferencingPolicy**コマンドレットを使用してユーザーには、会議ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="58d7c-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="58d7c-106">Skype ビジネス サーバー管理シェルを使用して会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="58d7c-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="58d7c-107">次の例では、SalesConferencingPolicy というポリシーを、"Ken Myer" という Identity のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="58d7c-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy

```

<span data-ttu-id="58d7c-p101">次の例では、会議ポリシー FinanceConferencingPolicy を、Finance という組織単位にアカウントがあるすべてのユーザーに割り当てます。同じポリシーを特定の組織単位 (OU) のすべてのユーザーに割り当てるため、Get-CsUser コマンドレットを使用して、その OU のすべてのアカウントを取得します。ユーザー アカウントを取得したら、次にその情報を Grant-CsConferencingPolicy コマンドレットにパイプ処理し、ポリシー FinanceConferencingPolicy をコレクション内の各ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="58d7c-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy

```

<span data-ttu-id="58d7c-111">完全な構文とパラメーターの一覧を含む詳細については、[許可 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58d7c-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

