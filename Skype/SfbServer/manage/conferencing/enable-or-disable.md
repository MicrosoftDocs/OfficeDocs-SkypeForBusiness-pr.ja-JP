---
title: Skype for Business Server でダイヤルイン会議を有効または無効にする
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '概要: コントロール パネルまたは管理シェルを使用して Skype for Business Server でダイヤルイン会議を有効または無効にする方法について説明します。'
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119466"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Skype for Business Server でダイヤルイン会議を有効または無効にする
 
**概要:** コントロール パネルまたは管理シェルを使用して Skype for Business Server でダイヤルイン会議を有効または無効にする方法について説明します。
  
ダイヤルイン会議は、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して有効にできます。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してダイヤルイン会議を有効または無効にする

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. 電話会議ポリシーの一覧で、ダイヤルイン会議を有効にするポリシーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。 
    
5. ユーザーがダイヤルインで会議に参加できるようにするには、[**PSTN ダイヤルイン会議を有効にする**] チェック ボックスをオンにします。既定では、ユーザーは公衆交換電話網 (PSTN) を使用して、会議にダイヤルインできます。
    
6. [**確定**] をクリックします。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してダイヤルイン会議を有効または無効にする

ダイヤルイン会議を有効または無効にするには、次のように EnableDialInConferencing パラメーターを使用して **Set-CsConferencingPolicy** コマンドレットを使用します。
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
