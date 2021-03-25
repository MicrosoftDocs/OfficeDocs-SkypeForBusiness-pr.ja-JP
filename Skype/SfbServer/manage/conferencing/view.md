---
title: Skype for Business Server で会議ポリシーを表示する
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
ms.openlocfilehash: afe86f0a77e73c3fa7bf96339c4865598a7bc609
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119406"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Skype for Business Server で会議ポリシーを表示する
 
**概要:** Skype for Business Server で会議ポリシーを表示する方法について説明します。
  
会議ポリシーは、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して表示できます。
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して会議ポリシーを表示する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. [**会議ポリシー**] ページで、表示する会議ポリシーをダブルクリックします。
    
5. [ **ファイル フィルターの編集] で**、[詳細の **表示] チェック ボックス** をオンにします。
    
    **会議ポリシーの編集 \<policy\> -** が開き、選択したポリシーの設定が表示されます。
    
    設定の構成の詳細については、「Skype for Business Server で会議ポリシーを [作成する」を参照してください](create-policies.md)。
    
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

完全な構文の説明とパラメーターの一覧を含む詳細については [、「Get-CsConferencingPolicy」を参照してください](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。
