---
title: Skype for Business サーバーで会議ポリシーを割り当てる
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '概要: Skype for Business サーバーで会議ポリシーを割り当てる方法の説明。'
ms.openlocfilehash: e63e59f806bcef14a50f75924527aa0f8733799b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767835"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Skype for Business サーバーで会議ポリシーを割り当てる
 
**概要:** Skype for Business サーバーで会議ポリシーを割り当てる方法の説明。
  
会議ポリシーをユーザーに割り当てることができ、これを行うには Skype for Business Server 管理シェルと **Grant-CsConferencingPolicy** コマンドレットを使用します。
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議ポリシーを割り当てる

次の例では、"Ken Myer" という ID を持つユーザーに、SalesConferencingPolicy というポリシーを割り当てます。
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

次の例では、会議ポリシー FinanceConferencingPolicy を "財務" という組織単位にアカウントがあるすべてのユーザーに割り当てています。同じポリシーを特定の組織単位 (OU) のすべてのユーザーに割り当てるため、Get-CsUser コマンドレットを使用して、その OU のすべてのアカウントを取得します。ユーザー アカウントを取得したら、次にその情報を Grant-CsConferencingPolicy コマンドレットにパイプ処理し、ポリシー FinanceConferencingPolicy をコレクション内の各ユーザーに割り当てます。
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

完全な構文とパラメーターの一覧を含む詳細については、「[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)」を参照してください。
