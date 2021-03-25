---
title: Skype for Business Server で会議への参加と退出のお知らせを管理する
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '概要: Skype for Business Server で会議への参加とアナウンスを管理する方法について学習します。'
ms.openlocfilehash: 796266dd3b571e525f657d5dbe712d1577779cae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119456"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="f538e-103">Skype for Business Server で会議への参加と退出のお知らせを管理する</span><span class="sxs-lookup"><span data-stu-id="f538e-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="f538e-104">**概要:** Skype for Business Server で会議への参加とアナウンスを残す方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="f538e-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="f538e-105">ダイヤルイン ユーザーが会議に参加または退出する場合、会議アナウンス アプリケーションは、トーンを再生するか、名前を言って、自分の入り口または退出をアナウンスできます。</span><span class="sxs-lookup"><span data-stu-id="f538e-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="f538e-106">次のパラメーターを使用して、Skype for Business Server 管理シェルと **Set-CsDialinConferencing** コマンドレットを使用して、アナウンスの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f538e-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="f538e-107">EnableNameRecording - 匿名の参加者が会議に参加する前に自分の名前を記録するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f538e-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="f538e-108">既定値は "$true" で、匿名の参加者は会議に参加するときに名前を入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f538e-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="f538e-109">(認証された参加者は、表示名が代わりに使用されるので、自分の名前は記録されません)。</span><span class="sxs-lookup"><span data-stu-id="f538e-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="f538e-110">EntryExitAnnouncementsEnabledByDefault - アナウンスが既定でオンまたはオフになっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f538e-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="f538e-111">既定値は "$false" で、参加者が会議に参加または退会するときに、既定ではアナウンスはありません。</span><span class="sxs-lookup"><span data-stu-id="f538e-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="f538e-112">会議の開催者は、会議をスケジュールするときにこの設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="f538e-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="f538e-113">EntryExitAnnouncementsType - 参加者が会議に参加または会議を離れるたびに実行されるアクションを示します。アナウンスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f538e-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="f538e-114">既定値は "UseNames" です。これは、アナウンスがオンになっているときに"Ken Myer が会議に参加しました" のようなアナウンスが発生します。</span><span class="sxs-lookup"><span data-stu-id="f538e-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="f538e-p105">これらの設定は、グローバル スコープまたはサイト スコープで構成できます。 サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="f538e-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="f538e-117">会議への出退席のアナウンス方法を変更するには</span><span class="sxs-lookup"><span data-stu-id="f538e-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="f538e-118">RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f538e-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="f538e-119">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f538e-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f538e-120">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f538e-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="f538e-121">このコマンドレットは、会議に参加するときに参加者が自分の名前を記録する必要があるかどうか、および参加者がダイヤルイン会議に参加または退出するときに Skype for Business Server がどのように応答するかに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="f538e-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="f538e-122">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f538e-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="f538e-123">次の例では、Redmond のサイト スコープで設定が構成されています。</span><span class="sxs-lookup"><span data-stu-id="f538e-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="f538e-124">アナウンスはオンにされますが、会議に参加するときに名前を言うよう参加者が求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="f538e-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="f538e-125">参加者が会議に参加または退出すると、トーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="f538e-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="f538e-126">構文やパラメーターの完全なリストを含む詳細については [、「Set-CsDialInConferencingConfiguration」を参照してください](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f538e-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
