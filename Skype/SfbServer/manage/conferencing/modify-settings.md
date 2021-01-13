---
title: Skype for Business Server で会議の構成設定を変更する
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '概要: Skype for Business Server で会議の構成設定を変更する方法について説明します。'
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827997"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で会議の構成設定を変更する
 
**概要:** Skype for Business Server で会議の構成設定を変更する方法について説明します。
  
会議の構成設定は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して変更できます。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議の構成設定を変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。
    
4. 会議の構成の一覧で、変更する構成をクリックし、[編集]をクリックして、[詳細の表示]**をクリックします**。
    
5. [**会議の構成の編集**] で、構成名以外の設定を変更します (構成名は変更不可です)。
    
6. [**確定**] をクリックします。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議の構成設定を変更する

会議の構成設定を変更するには **、Set-CsMeetingConfiguration コマンドレットを使用** します。
  
次の例に示すコマンドは、Redmond サイト (-Identity site:Redmond) に割り当てられている会議の構成設定を変更します。 この場合、DesignateAsPresenter プロパティの値は Everyone に設定されます。
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

パラメーターの完全な一覧を含む詳細については [、「Set-CsMeetingConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。
  

