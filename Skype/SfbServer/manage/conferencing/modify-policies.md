---
title: Skype for Business Server での会議ポリシーの変更
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
ms.openlocfilehash: 6bbba82c9785e074da492eb66cbdd943dc0cea35
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119426"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server での会議ポリシーの変更
 
**概要:** Skype for Business Server で会議ポリシーを変更する方法について説明します。
  
会議ポリシーは、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して変更できます。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議ポリシーを変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. 会議ポリシーの一覧で、変更するポリシーをクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。
    
5. [ **会議ポリシーの編集**] で、変更できないポリシー名以外のポリシー設定を変更します。
    
6. [**確定**] をクリックします。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議ポリシーを変更する

会議ポリシーを変更するには **、Set-CsConferencingPolicy コマンドレットを使用** します。
  
次の使用例は、会議ポリシー SalesConferencingPolicy のプロパティ値を変更します。 このコマンドは、AllowConferenceRecording プロパティの値を False に設定します。
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

完全な構文とパラメーターの一覧を含む詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
