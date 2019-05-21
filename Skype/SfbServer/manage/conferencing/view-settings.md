---
title: Skype for Business Server で会議構成の設定を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '概要: Skype for Business Server で会議の構成設定を表示する方法について説明します。'
ms.openlocfilehash: 13d91bc4c0335d8c069e0b0d9bc41efd8714f112
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280370"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で会議構成の設定を表示する
 
**概要:** Skype for Business Server で会議の構成設定を表示する方法について説明します。
  
会議の設定を表示するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して会議構成の設定を表示する
<a name="BKMK_ViewJoinSettings"> </a>

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
4. [**会議の構成**] ページで、表示する会議構成をクリックします。
    
5. [**ファイル フィルターの編集**] で、[**詳細の表示**] チェック ボックスをオンにします。
    
    [**会議の構成\<の\>編集]-** 選択したポリシーの設定が表示されたポリシーが開きます。
    
    設定の構成の詳細については、「 [Skype For Business Server で会議の構成設定を作成](create-settings.md)する」を参照してください。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議構成の設定を表示する
<a name="BKMK_ViewJoinSettings"> </a>

すべての会議の構成設定に関する情報を表示するには、**Get-CsMeetingConfiguration** コマンドレットを使用します。
  
```
Get-CsMeetingConfiguration
```

このコマンドは、次のような情報を返します。
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

パラメーターの完全な一覧を含む、詳細については、「 [Cs会議の構成](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)」を参照してください。
  

