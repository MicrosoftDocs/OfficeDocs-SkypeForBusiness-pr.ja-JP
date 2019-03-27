---
title: ビジネス サーバーの Skype での会議ポリシーを割り当てる
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '概要: ビジネス サーバーの Skype での会議ポリシーを割り当てる方法を説明します。'
ms.openlocfilehash: 44e29842fd11d600aa5a692e98b5ddbb72149ade
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892633"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>ビジネス サーバーの Skype での会議ポリシーを割り当てる
 
**の概要:** ビジネス サーバーの Skype での会議ポリシーを割り当てる方法について説明します。
  
Skype をビジネス サーバー管理シェルを**与える CsConferencingPolicy**コマンドレットを使用してユーザーには、会議ポリシーを割り当てることができます。
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用して会議ポリシーを割り当てる

次の例では、SalesConferencingPolicy というポリシーを、"Ken Myer" という Identity のユーザーに割り当てます。
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

次の例では、会議ポリシー FinanceConferencingPolicy を、Finance という組織単位にアカウントがあるすべてのユーザーに割り当てます。同じポリシーを特定の組織単位 (OU) のすべてのユーザーに割り当てるため、Get-CsUser コマンドレットを使用して、その OU のすべてのアカウントを取得します。ユーザー アカウントを取得したら、次にその情報を Grant-CsConferencingPolicy コマンドレットにパイプ処理し、ポリシー FinanceConferencingPolicy をコレクション内の各ユーザーに割り当てます。
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

完全な構文とパラメーターの一覧を含む詳細については、[許可 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)を参照してください。
  

