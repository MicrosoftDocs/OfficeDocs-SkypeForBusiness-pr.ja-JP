---
title: Skype for Business Server の会議構成の設定を変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '概要: Skype for Business Server で会議構成の設定を変更する方法について説明します。'
ms.openlocfilehash: 2e9d8a737a2bfc48cdcbe39540a22e4c236003b3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992854"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server の会議構成の設定を変更する
 
**概要:** Skype for Business Server で会議の設定を変更する方法について説明します。
  
会議の設定を変更するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して会議の設定を変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
4. 会議構成の一覧で、変更する構成をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
5. [**会議の構成の編集**] で、構成名以外の構成設定を変更します (構成名は変更不可です)。
    
6. [**確定**] をクリックします。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議の設定を変更する

会議の構成設定を変更するには、**Set-CsMeetingConfiguration** コマンドレットを使用します。
  
次の例に示すコマンドは、Redmond サイト (-Identity site:Redmond) に割り当てられている会議構成設定を変更します。この場合、DesignateAsPresenter プロパティの値が "Everyone" に設定されています。
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

パラメーターの完全な一覧など、詳細については、「 [Cs会議構成](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)」を参照してください。
  

