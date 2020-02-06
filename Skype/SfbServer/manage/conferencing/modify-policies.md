---
title: Skype for Business Server の会議ポリシーを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '概要: Skype for Business Server の会議ポリシーを変更する方法について説明します。'
ms.openlocfilehash: 4f78a956754e4375ac1dfa7460222b1fb1bbf9ef
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818508"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server の会議ポリシーを変更する
 
**概要:** Skype for Business Server の会議ポリシーを変更する方法について説明します。
  
会議のポリシーを変更するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して会議のポリシーを変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
4. 電話会議ポリシーの一覧で、変更するポリシーをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
5. [**会議ポリシーの編集**] で、変更できないポリシー名以外のポリシー設定のいずれかを変更します。
    
6. [**確定**] をクリックします。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議のポリシーを変更する

会議ポリシーを変更するには、 **set-csconferencingpolicy**コマンドレットを使用します。
  
次の例では、電話会議ポリシー SalesConferencingPolicy のプロパティ値を変更します。 このコマンドにより、AllowConferenceRecording プロパティの値が False に設定されます。
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

完全な構文とパラメーターの一覧を含む詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
  

