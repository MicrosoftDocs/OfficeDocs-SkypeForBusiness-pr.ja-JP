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
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="1eca7-103">Skype for Business Server で会議ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="1eca7-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="1eca7-104">**概要:** Skype for Business Server で会議ポリシーを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1eca7-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="1eca7-105">会議ポリシーは、Skype for Business Server コントロール パネルを使用するか、Skype for Business Server 管理シェルを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="1eca7-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1eca7-106">Skype for Business Server コントロール パネルを使用して会議ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="1eca7-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1eca7-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1eca7-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1eca7-108">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1eca7-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1eca7-109">左側のナビゲーション バーで、[会議] **をクリック** し、[会議ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1eca7-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="1eca7-110">[**会議ポリシー**] ページで、表示する会議ポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1eca7-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="1eca7-111">[ **ファイル フィルターの編集] で**、[詳細の **表示] チェック ボックス** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="1eca7-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="1eca7-112">**会議ポリシーの編集 \<policy\> -** が開き、選択したポリシーの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1eca7-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="1eca7-113">設定の構成の詳細については、「Skype for Business Server で会議ポリシーを [作成する」を参照してください](create-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1eca7-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1eca7-114">Skype for Business Server 管理シェルを使用して会議ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="1eca7-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1eca7-115">会議ポリシーを表示するには **、Get-CsConferencingPolicy コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="1eca7-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="1eca7-116">コマンドレットは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="1eca7-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="1eca7-117">完全な構文の説明とパラメーターの一覧を含む詳細については [、「Get-CsConferencingPolicy」を参照してください](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1eca7-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
