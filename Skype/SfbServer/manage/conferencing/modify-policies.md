---
title: Skype for Business Server で会議ポリシーを変更する
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '概要: Skype for Business Server で会議ポリシーを変更する方法について説明します。'
ms.openlocfilehash: eafeb56dd9b0c36afffab07830a9efb71bde18fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828007"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server で会議ポリシーを変更する
 
**概要:** Skype for Business Server で会議ポリシーを変更する方法について説明します。
  
会議ポリシーは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して変更できます。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議ポリシーを変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. 会議ポリシーの一覧で、変更するポリシーをクリックし、[編集] をクリックして、[詳細の表示]**をクリックします**。
    
5. [ **会議ポリシーの編集**] で、変更できないポリシー名を除くすべてのポリシー設定を変更します。
    
6. [**確定**] をクリックします。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議ポリシーを変更する

会議ポリシーを変更するには **、Set-CsConferencingPolicy コマンドレットを使用** します。
  
次の例では、会議ポリシー SalesConferencingPolicy のプロパティ値を変更します。 このコマンドは、AllowConferenceRecording プロパティの値を False に設定します。
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

完全な構文やパラメーターの一覧など、詳細については [、「Set-CsConferencingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

