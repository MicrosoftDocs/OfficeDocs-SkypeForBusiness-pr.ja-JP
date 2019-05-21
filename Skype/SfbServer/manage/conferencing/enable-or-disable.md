---
title: Skype for Business Server でダイヤルイン会議を有効または無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '概要: コントロールパネルまたは管理シェルを使用して、Skype for Business Server でダイヤルイン会議を有効または無効にする方法について説明します。'
ms.openlocfilehash: 6723c3501b226d11977ad176a804210540f1a2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294258"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Skype for Business Server でダイヤルイン会議を有効または無効にする
 
**概要:** コントロールパネルまたは管理シェルを使用して、Skype for Business Server でダイヤルイン会議を有効または無効にする方法について説明します。
  
Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用して、ダイヤルイン会議を有効にすることができます。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ダイヤルイン会議を有効または無効にする

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
4. 電話会議ポリシーの一覧で、ダイヤルイン会議を有効にするポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。 
    
5. ユーザーがダイヤルインで会議に参加できるようにするには、[**PSTN ダイヤルイン会議を有効にする**] チェック ボックスをオンにします。既定では、ユーザーは公衆交換電話網 (PSTN) を使用して、会議にダイヤルインできます。
    
6. [**確定**] をクリックします。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して、ダイヤルイン会議を有効または無効にする

ダイヤルイン会議を有効または無効にするには、次のように **Set-CsConferencingPolicy** コマンドレットを使用し、EnableDialInConferencing パラメーターを指定します。
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
  

