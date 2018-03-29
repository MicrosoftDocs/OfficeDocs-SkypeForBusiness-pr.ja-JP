---
title: Skype for Business Server 2015 での電話会議ポリシーの変更
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: '概要: ビジネス サーバー 2015 の Skype での会議ポリシーを変更する方法を説明します。'
ms.openlocfilehash: b0456db5d0c6131b3b3999a87fc824d6ee3b4b30
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="modify-conferencing-policies-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での電話会議ポリシーの変更
 
**の概要:**ビジネス サーバー 2015 の Skype での会議ポリシーを変更する方法について説明します。
  
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
  

