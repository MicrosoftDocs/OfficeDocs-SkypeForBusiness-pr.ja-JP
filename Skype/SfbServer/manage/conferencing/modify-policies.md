---
title: 会議の会議ポリシーを変更Skype for Business Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '概要: 会議ポリシーを変更する方法については、Skype for Business Server。'
ms.openlocfilehash: e7976cfd41be223aa0766f7a34d58563a21cb08e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773657"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>会議の会議ポリシーを変更Skype for Business Server
 
**概要:** 会議ポリシーを変更する方法については、Skype for Business Server。
  
会議ポリシーは、コントロール パネルを使用するかSkype for Business Server管理シェルを使用Skype for Business Server変更できます。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して会議Skype for Business Server変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. 会議ポリシーの一覧で、変更するポリシーをクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。
    
5. [ **会議ポリシーの編集**] で、変更できないポリシー名以外のポリシー設定を変更します。
    
6. [**確定**] をクリックします。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議ポリシー Skype for Business Server変更する

会議ポリシーを変更するには **、Set-CsConferencingPolicy コマンドレットを使用** します。
  
次の使用例は、会議ポリシー SalesConferencingPolicy のプロパティ値を変更します。 このコマンドは、AllowConferenceRecording プロパティの値を False に設定します。
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

完全な構文とパラメーターの一覧を含む詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
