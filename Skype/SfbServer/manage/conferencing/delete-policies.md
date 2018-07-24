---
title: ビジネス サーバーの Skype での会議ポリシーを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '概要: ビジネス サーバーの Skype での会議ポリシーを削除する方法を説明します。'
ms.openlocfilehash: 157307fc81bf5e5d0e93bd65b9a513f92b317a68
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012624"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>ビジネス サーバーの Skype での会議ポリシーを削除します。
 
**の概要:** ビジネス サーバーの Skype での会議ポリシーを削除する方法について説明します。
  
ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、会議ポリシーを削除できます。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、会議ポリシーを削除します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
4. 電話会議ポリシーのリストで、削除するサイト ポリシーまたはユーザー ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用して会議ポリシーを削除します。

電話会議ポリシーを削除するには、**Remove-CsConferencingPolicy** コマンドレットを使用します。
  
次のコマンドは、Identity が RedmondConferencingPolicy の電話会議ポリシーを削除します。
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

次のコマンドは、外部ユーザーに電話会議の記録を許可するすべての電話会議ポリシーを削除します。
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

詳細については、完全な構文とパラメーターのリストを含む[削除 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)を参照してください。
  

