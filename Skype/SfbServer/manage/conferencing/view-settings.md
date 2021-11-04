---
title: '[会議の構成設定を表示する] Skype for Business Server'
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '概要: 会議の構成設定を表示する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: db374c3db105b0ffcefe9d846c9c4c17904b14ee
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766545"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>[会議の構成設定を表示する] Skype for Business Server
 
**概要:** 会議の構成設定を表示する方法については、Skype for Business Server。
  
会議の構成設定は、コントロール パネルまたは管理シェルSkype for Business Server使用して表示Skype for Business Serverできます。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して会議Skype for Business Serverを表示する
<a name="BKMK_ViewJoinSettings"> </a>

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。
    
4. [**会議の構成**] ページで、表示する会議構成をクリックします。
    
5. [ **ファイル フィルターの編集] で**、[詳細の **表示] チェック ボックス** をオンにします。
    
    **会議の構成の \<policy\> 編集 -** が開き、選択したポリシーの設定が表示されます。
    
    設定の構成の詳細については、「会議の構成設定を作成する」を参照[Skype for Business Server。](create-settings.md)
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議の構成Skype for Business Server表示する
<a name="BKMK_ViewJoinSettings"> </a>

すべての会議構成設定に関する情報を表示するには **、Get-CsMeetingConfiguration コマンドレットを使用** します。
  
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

パラメーターの完全な一覧を含む詳細については [、「Get-CsMeetingConfiguration」を参照してください](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)。
