---
title: 会議でダイヤルイン会議を有効または無効にするSkype for Business Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '概要: コントロール パネルまたは管理シェルを使用して、ダイヤルイン会議を有効または無効にする方法についてSkype for Business Server。'
ms.openlocfilehash: 45a47d411570d20273c9a3a9ace3536641157fde
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766575"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>会議でダイヤルイン会議を有効または無効にするSkype for Business Server
 
**概要:** コントロール パネルまたは管理シェルを使用して、ダイヤルイン会議を有効または無効にする方法についてSkype for Business Server。
  
ダイヤルイン会議を有効にするには、Skype for Business Serverコントロール パネルを使用するか、Skype for Business Serverを使用します。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用してダイヤルイン会議を有効またはSkype for Business Serverする

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. 電話会議ポリシーの一覧で、ダイヤルイン会議を有効にするポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。 
    
5. ユーザーがダイヤルインで会議に参加できるようにするには、[**PSTN ダイヤルイン会議を有効にする**] チェック ボックスをオンにします。既定では、ユーザーは公衆交換電話網 (PSTN) を使用して、会議にダイヤルインできます。
    
6. [**確定**] をクリックします。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用してダイヤルイン会議を有効またはSkype for Business Serverする

ダイヤルイン会議を有効または無効にするには、次のように EnableDialInConferencing パラメーターを使用して **Set-CsConferencingPolicy** コマンドレットを使用します。
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
