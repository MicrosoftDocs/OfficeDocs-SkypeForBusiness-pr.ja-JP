---
title: Skype for Business Server で会議への参加および退出のアナウンスを管理する
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
description: '概要: Skype for Business Server で会議への参加および退出のアナウンスを管理する方法について学習します。'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828107"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="87211-103">Skype for Business Server で会議への参加および退出のアナウンスを管理する</span><span class="sxs-lookup"><span data-stu-id="87211-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="87211-104">**概要:** Skype for Business Server で会議への参加および退出のアナウンスを管理する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="87211-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="87211-105">ダイヤルイン ユーザーが会議に参加または会議から退出すると、会議アナウンス アプリケーションは、トーンを再生するか、名前を言って、開始または退出をアナウンスできます。</span><span class="sxs-lookup"><span data-stu-id="87211-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="87211-106">Skype for Business Server 管理シェルおよび **Set-CsDialinConferencing** コマンドレットを使用して、次のパラメーターを使用して、アナウンスの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="87211-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="87211-107">EnableNameRecording - 会議に参加する前に、匿名の参加者に名前の記録を求めるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="87211-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="87211-108">既定値は "$true" で、匿名の参加者は会議に参加するときに名前を入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87211-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="87211-109">(認証された参加者は、表示名が代わりに使用されるので、名前は記録されません)。</span><span class="sxs-lookup"><span data-stu-id="87211-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="87211-110">EntryExitAnnouncementsEnabledByDefault - アナウンスが既定でオンまたはオフになっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="87211-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="87211-111">既定値は "$false" です。これは、参加者が会議に参加または会議から退出するときにアナウンスが既定で行えなを意味します。</span><span class="sxs-lookup"><span data-stu-id="87211-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="87211-112">会議の開催者は、会議のスケジュール時にこの設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="87211-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="87211-113">EntryExitAnnouncementsType - アナウンスが有効になっている会議に参加者が参加または会議から離れるたびに実行されるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="87211-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="87211-114">既定値は "UseNames" です。これは、アナウンスがオンになっているときに"Ken Myer が会議に参加しました" のようなアナウンスが表示されるという意味です。</span><span class="sxs-lookup"><span data-stu-id="87211-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="87211-p105">これらの設定は、グローバル スコープまたはサイト スコープで構成できます。 サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="87211-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="87211-117">会議への出退席のアナウンス方法を変更するには</span><span class="sxs-lookup"><span data-stu-id="87211-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="87211-118">RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="87211-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="87211-119">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87211-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="87211-120">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="87211-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="87211-121">このコマンドレットは、参加者が会議に参加するときに名前を記録する必要があるかどうか、および参加者がダイヤルイン会議に参加またはダイヤルイン会議から退出するときに Skype for Business Server がどのように応答するかに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="87211-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="87211-122">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="87211-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="87211-123">次の例では、Redmond のサイト スコープで設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="87211-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="87211-124">アナウンスはオンにされますが、会議に参加するときに名前を言うよう参加者が求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="87211-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="87211-125">参加者が会議に参加または会議から退出すると、トーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="87211-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="87211-126">構文やパラメーターの完全な一覧など、詳細については [、「Set-CsDialInConferencingConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="87211-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

