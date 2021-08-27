---
title: 会議ポリシーを表示Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: '概要: 会議ポリシーを表示する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: f3e41eaa136674e7ab91af0b947daf6def872be5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578811"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>会議ポリシーを表示Skype for Business Server
 
**概要:** 会議ポリシーを表示する方法については、Skype for Business Server。
  
会議ポリシーは、コントロール パネルを使用するか、Skype for Business Server管理シェルを使用Skype for Business Server表示できます。
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用して会議ポリシー Skype for Business Server表示する

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2.  [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。
    
4. [**会議ポリシー**] ページで、表示する会議ポリシーをダブルクリックします。
    
5. [ **ファイル フィルターの編集] で**、[詳細の **表示] チェック ボックス** をオンにします。
    
    **会議ポリシーの編集 \<policy\> -** が開き、選択したポリシーの設定が表示されます。
    
    設定の構成の詳細については、「会議ポリシーを作成[する」を参照Skype for Business Server。](create-policies.md)
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>管理シェルを使用して会議ポリシー Skype for Business Server表示する

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
