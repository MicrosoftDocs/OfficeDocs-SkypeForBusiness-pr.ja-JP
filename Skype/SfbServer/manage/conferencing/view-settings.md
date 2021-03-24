---
title: Skype for Business Server で会議の構成設定を表示する
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '概要: Skype for Business Server で会議構成設定を表示する方法について説明します。'
ms.openlocfilehash: 81f5ef1bc0ce28c7741aa99529e7ba107ff4127f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096703"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Skype for Business Server で会議の構成設定を表示する
 
**概要:** Skype for Business Server で会議構成設定を表示する方法について説明します。
  
会議の構成設定は、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して表示できます。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議の構成設定を表示する
<a name="BKMK_ViewJoinSettings"> </a>

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。
    
4. [**会議の構成**] ページで、表示する会議構成をクリックします。
    
5. [ **ファイル フィルターの編集] で**、[詳細の **表示] チェック ボックス** をオンにします。
    
    **会議の構成の \<policy\> 編集 -** が開き、選択したポリシーの設定が表示されます。
    
    設定の構成の詳細については [、「Create meeting configuration settings in Skype for Business Server」を参照してください](create-settings.md)。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議の構成設定を表示する
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
