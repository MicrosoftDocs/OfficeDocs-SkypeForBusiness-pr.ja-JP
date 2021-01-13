---
title: Skype for Business Server での会議ポリシーの表示
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
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: '概要: Skype for Business Server で会議ポリシーを表示する方法について説明します。'
ms.openlocfilehash: 39b37a1335f8b257f9dec1fff28bea90ac7a6db9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817507"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server での会議ポリシーの表示
 
**概要:** Skype for Business Server で会議ポリシーを表示する方法について説明します。
  
会議ポリシーは、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して表示できます。
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議ポリシーを表示する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. [**会議ポリシー**] ページで、表示する会議ポリシーをダブルクリックします。
    
5. [ **ファイル フィルターの編集] で**、[詳細の表示 **] チェック ボックス** をオンにします。
    
    **会議ポリシーの編集 \<policy\> -** が開き、選択したポリシーの設定が表示されます。
    
    設定の構成の詳細については、「Skype for Business Server での会議ポリシーの作成 [」を参照してください](create-policies.md)。
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議ポリシーを表示する

会議ポリシーを表示するには **、Get-CsConferencingPolicy コマンドレットを使用** します。
  
```PowerShell
Get-CsConferencingPolicy
```

コマンドレットは、次のような情報を返します。
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

完全な構文の説明やパラメーターの一覧など、詳細については [、Get-CsConferencingPolicy を参照してください](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。
  

