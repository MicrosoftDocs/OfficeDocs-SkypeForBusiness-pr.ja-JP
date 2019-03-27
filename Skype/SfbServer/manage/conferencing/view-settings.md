---
title: Skype ビジネス サーバーの構成設定の会議を表示
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '概要: を表示する方法を学習する Skype ビジネス サーバーの構成設定に対応します。'
ms.openlocfilehash: d7ef617050b31bd85732ee4a30d0faaed41f50d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899399"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Skype ビジネス サーバーの構成設定の会議を表示
 
**の概要:** 表示する方法を学習 Skype ビジネス サーバーの構成設定に対応します。
  
表示することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定の表示
<a name="BKMK_ViewJoinSettings"> </a>

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
4. [**会議の構成**] ページで、表示する会議構成をクリックします。
    
5. [**ファイル フィルターの編集**] で、[**詳細の表示**] チェック ボックスをオンにします。
    
    **会議設定の編集 -\<ポリシー\>** が開き、選択したポリシーの設定を表示します。
    
    詳細設定の構成については、[会議の Skype ビジネス サーバーの構成設定の作成](create-settings.md)を参照してください。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用して会議の構成設定の表示
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

パラメーターの完全な一覧を含む詳細については、 [Get CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)を参照してください。
  

