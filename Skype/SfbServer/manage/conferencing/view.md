---
title: Skype for Business Server で会議のポリシーを表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: '概要: Skype for Business Server で会議ポリシーを表示する方法について説明します。'
ms.openlocfilehash: 2273e694ce2f34c8d395f87f207de85b409e18af
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818448"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server で会議のポリシーを表示する
 
**概要:** Skype for Business Server で会議ポリシーを表示する方法について説明します。
  
会議のポリシーを表示するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して会議のポリシーを表示する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。
    
4. [**会議ポリシー**] ページで、表示する会議ポリシーをダブルクリックします。
    
5. [**ファイル フィルターの編集**] で、[**詳細の表示**] チェック ボックスをオンにします。
    
    [**会議ポリシーの\<編集\> ]-** 選択したポリシーの設定が表示されたポリシーが開きます。
    
    設定の構成の詳細については、「 [Skype For Business Server で会議ポリシーを作成](create-policies.md)する」を参照してください。
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して会議のポリシーを表示する

会議ポリシーを表示するには、**Get-CsConferencingPolicy** コマンドレットを使用します。
  
```PowerShell
Get-CsConferencingPolicy
```

コマンドレットを実行すると、次のような情報が返されます。
  
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

詳細については、「 [Get-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)」を参照してください。
  

