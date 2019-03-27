---
title: 有効にするか、ビジネスのサーバーの Skype では、ダイヤルイン会議を無効にします。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '概要: は、コントロール パネルまたは管理シェルを使用して、有効またはビジネス サーバーの Skype では、ダイヤルイン会議を無効にする方法を説明します。'
ms.openlocfilehash: 216973e8d3a887dcae308fc5efa6d67b2415493b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895357"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>有効にするか、ビジネスのサーバーの Skype では、ダイヤルイン会議を無効にします。
 
**の概要:** ビジネス サーバーの Skype では、ダイヤルイン会議を無効にするを有効または、コントロール パネルまたは管理シェルを使用する方法について説明します。
  
ビジネス サーバーのコントロール パネルの Skype を使用して、または Skype ビジネス サーバー管理シェルを使用して、ダイヤルイン会議を有効にできます。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、ダイヤルイン会議を無効にするを有効または

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
4. 電話会議ポリシーの一覧で、ダイヤルイン会議を有効にするポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。 
    
5. ユーザーがダイヤルインで会議に参加できるようにするには、[**PSTN ダイヤルイン会議を有効にする**] チェック ボックスをオンにします。既定では、ユーザーは公衆交換電話網 (PSTN) を使用して、会議にダイヤルインできます。
    
6. [**確定**] をクリックします。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>有効にするか、Skype ビジネス サーバー管理シェルを使用してダイヤルイン会議を無効にします。

ダイヤルイン会議を有効または無効にするには、次のように **Set-CsConferencingPolicy** コマンドレットを使用し、EnableDialInConferencing パラメーターを指定します。
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。
  

