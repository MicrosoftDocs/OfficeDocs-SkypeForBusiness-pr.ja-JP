---
title: Skype for Business Server 2015 での会議の構成設定の表示
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '概要: を表示する方法を説明する会議出席ビジネス サーバー 2015 の Skype の設定を構成します。'
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での会議の構成設定の表示
 
**の概要:**表示する方法について説明会議出席ビジネス サーバー 2015 の Skype の設定を構成します。
  
表示することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定の表示
<a name="BKMK_ViewJoinSettings"> </a>

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。
    
4. [**会議の構成**] ページで、表示する会議構成をクリックします。
    
5. [**ファイル フィルターの編集**] で、[**詳細の表示**] チェック ボックスをオンにします。
    
    **会議設定の編集 -\<ポリシー\>**が開き、選択したポリシーの設定を表示します。
    
    詳細設定の構成については、[会議ビジネス サーバー 2015 の Skype での構成設定の作成](create-settings.md)を参照してください。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用して会議の構成設定の表示
<a name="BKMK_ViewJoinSettings"> </a>

すべての会議の構成設定に関する情報を表示するには、**Get-CsMeetingConfiguration** コマンドレットを使用します。
  
```
Get-CsMeetingConfiguration
```

このコマンドは、次のような情報を返します。
  
```
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

```

パラメーターの完全な一覧を含む詳細については、 [Get CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)を参照してください。
  

