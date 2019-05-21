---
title: Skype for Business Server で会議への参加とお知らせの脱退を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '概要: Skype for Business Server で会議の参加を管理する方法、およびお知らせを残す方法について説明します。'
ms.openlocfilehash: 3d9a14e36dfe6b8df51e5ee91dd329ce34452cda
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283796"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="23fe6-103">Skype for Business Server で会議への参加とお知らせの脱退を管理する</span><span class="sxs-lookup"><span data-stu-id="23fe6-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="23fe6-104">**概要:** Skype for Business Server で会議の参加を管理する方法、およびお知らせを残す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23fe6-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="23fe6-105">ダイヤルインユーザーが会議に参加しているとき、会議に参加しているときに、会議アナウンスメントアプリケーションは、トーンを再生したり名前を言ったりして、開始または終了することができます。</span><span class="sxs-lookup"><span data-stu-id="23fe6-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="23fe6-106">次のパラメーターを使用して、Skype for Business Server 管理シェルと**Set-csダイヤルイン会議**コマンドレットを使用して、お知らせの動作方法を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="23fe6-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="23fe6-p102">EnableNameRecording - 会議に出席する前に名前を記録するよう匿名参加者に依頼するかどうかを指定します。既定値は "$true" で、これは、会議に出席するときに名前を言うように匿名参加者に求めることを意味します (認証された参加者の場合は、表示名が代わりに使用されるため、名前を記録しません)。</span><span class="sxs-lookup"><span data-stu-id="23fe6-p102">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference. The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference. (Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="23fe6-p103">EntryExitAnnouncementsEnabledByDefault - 既定でアナウンス機能をオンまたはオフにするかどうかを示します。既定値は "$false" で、これは既定で、参加者が会議に出席または会議から退席するときにアナウンスが行われないことを意味します。ミーティング開催者は、ミーティングをスケジュールするときにこの設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="23fe6-p103">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default. The default value is "$false," which means that by default there are no announcements when participants join or leave a conference. The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="23fe6-p104">EntryExitAnnouncementsType - アナウンスが有効な会議に参加者が出席または退席するときに実行されるアクションを示します。既定値は "UseNames" で、これは、アナウンスをオンにすると、"Ken Myer が会議に参加しました" というようなアナウンスが行われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="23fe6-p104">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled. The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="23fe6-p105">これらの設定は、グローバル スコープまたはサイト スコープで構成できます。サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="23fe6-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="23fe6-117">会議への出退席のアナウンス方法を変更するには</span><span class="sxs-lookup"><span data-stu-id="23fe6-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="23fe6-118">コンピューターに RTCUniversalServerAdmins グループのメンバーとしてログオンするか、Cs-ServerAdministrator または CsAdministrator 役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="23fe6-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="23fe6-119">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="23fe6-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="23fe6-120">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23fe6-120">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="23fe6-121">このコマンドレットは、参加者が会議に参加するときに名前を記録する必要があるかどうか、また、参加者がダイヤルイン会議に参加または退出したときに Skype for Business Server がどのように応答するかに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="23fe6-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="23fe6-122">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23fe6-122">Run the following at the command prompt:</span></span>
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="23fe6-p106">次の例では、設定が Redmond のサイト スコープで定義されます。アナウンスはオンにされますが、会議に参加するときに名前を言うように参加者が求められることはありません。参加者が会議に出席または会議から退席するときには、トーン音が再生されます。</span><span class="sxs-lookup"><span data-stu-id="23fe6-p106">In the following example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference:</span></span>
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="23fe6-126">構文とパラメーターの完全な一覧を含む詳細については、「 [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23fe6-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

