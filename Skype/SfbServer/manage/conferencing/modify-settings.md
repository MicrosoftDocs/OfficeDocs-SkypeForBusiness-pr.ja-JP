---
title: 会議の構成設定を変更Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '概要: 会議の構成設定を変更する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 2f57f0a7d6bd445e84cf0d9feb43997613d35794
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848560"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>会議の構成設定を変更Skype for Business Server
 
**概要:** 会議の構成設定を変更する方法については、Skype for Business Server。
  
会議の構成設定は、コントロール パネルを使用するかSkype for Business Server管理シェルを使用してSkype for Business Server変更できます。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>コントロール パネルを使用して会議の構成Skype for Business Server変更する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。
    
4. 会議構成の一覧で、変更する構成をクリックし、[編集] をクリックし、[詳細の表示]**をクリックします**。
    
5. [**会議の構成の編集**] で、構成名以外の設定を変更します (構成名は変更不可です)。
    
6. [**確定**] をクリックします。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議の構成Skype for Business Server変更する

会議の構成設定を変更するには **、Set-CsMeetingConfiguration コマンドレットを使用** します。
  
次の例に示すコマンドは、Redmond サイト (-Identity site:Redmond) に割り当てられた会議構成設定を変更します。 この場合、DesignateAsPresenter プロパティの値は Everyone に設定されます。
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

パラメーターの完全なリストを含む詳細については [、「Set-CsMeetingConfiguration」を参照してください](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。
