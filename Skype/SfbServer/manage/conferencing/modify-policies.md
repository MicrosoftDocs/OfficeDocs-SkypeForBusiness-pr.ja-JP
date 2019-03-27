---
title: ビジネス サーバーの Skype での会議ポリシーを変更します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '概要: ビジネス サーバーの Skype での会議ポリシーを変更する方法を説明します。'
ms.openlocfilehash: 36b6cb92ddb1a6628186198906da87c5dec29532
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878043"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>ビジネス サーバーの Skype での会議ポリシーを変更します。
 
**の概要:** ビジネス サーバーの Skype での会議ポリシーを変更する方法について説明します。
  
ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、会議ポリシーを変更できます。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、会議ポリシーを変更します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
4. 電話会議ポリシーの一覧で、変更するポリシーをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
5. [**会議ポリシーの編集**] で、変更できないポリシー名以外のポリシー設定のいずれかを変更します。
    
6. [**確定**] をクリックします。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用して会議ポリシーを変更します。

会議ポリシーを変更するには、**セット CsConferencingPolicy**コマンドレットを使用します。
  
次の例では、電話会議ポリシー SalesConferencingPolicy のプロパティ値を変更します。 このコマンドにより、AllowConferenceRecording プロパティの値が False に設定されます。
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

詳細については、完全な構文とパラメーターのリストを含む[セット CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。
  

