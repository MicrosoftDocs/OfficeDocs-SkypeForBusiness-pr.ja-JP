---
title: Skype for Business Server 2015 での電話会議への入退出のアナウンスの管理
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '概要: は、会議の参加を管理し、お知らせの Skype ビジネス サーバー 2015 のままにする方法を説明します。'
ms.openlocfilehash: 33e01efebc7d188fe329c1c39718aaf661af1e44
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server-2015"></a><span data-ttu-id="7264c-103">Skype for Business Server 2015 での電話会議への入退出のアナウンスの管理</span><span class="sxs-lookup"><span data-stu-id="7264c-103">Manage conference join and leave announcements in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7264c-104">**の概要:**会議の参加を管理し、お知らせの Skype ビジネス サーバー 2015 のままにする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="7264c-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7264c-105">ダイヤルイン ユーザーは、参加または会議のままにして、会議アナウンス アプリケーションの開始を発表したり、音を再生するか、名前を言うまでに終了します。</span><span class="sxs-lookup"><span data-stu-id="7264c-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="7264c-106">Skype ビジネス サーバー管理シェルは、次のパラメーターを使用して**セット CsDialinConferencing**コマンドレットを使用して、お知らせがどのように動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7264c-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="7264c-p102">EnableNameRecording - 会議に出席する前に名前を記録するよう匿名参加者に依頼するかどうかを指定します。既定値は "$true" で、これは、会議に出席するときに名前を言うように匿名参加者に求めることを意味します (認証された参加者の場合は、表示名が代わりに使用されるため、名前を記録しません)。</span><span class="sxs-lookup"><span data-stu-id="7264c-p102">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference. The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference. (Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="7264c-p103">EntryExitAnnouncementsEnabledByDefault - 既定でアナウンス機能をオンまたはオフにするかどうかを示します。既定値は "$false" で、これは既定で、参加者が会議に出席または会議から退席するときにアナウンスが行われないことを意味します。ミーティング開催者は、ミーティングをスケジュールするときにこの設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="7264c-p103">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default. The default value is "$false," which means that by default there are no announcements when participants join or leave a conference. The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="7264c-p104">EntryExitAnnouncementsType - アナウンスが有効な会議に参加者が出席または退席するときに実行されるアクションを示します。既定値は "UseNames" で、これは、アナウンスをオンにすると、"Ken Myer が会議に参加しました" というようなアナウンスが行われることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7264c-p104">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled. The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="7264c-p105">これらの設定は、グローバル スコープまたはサイト スコープで構成できます。サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="7264c-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="7264c-117">会議への出退席のアナウンス方法を変更するには</span><span class="sxs-lookup"><span data-stu-id="7264c-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="7264c-118">コンピューターに RTCUniversalServerAdmins グループのメンバーとしてログオンするか、Cs-ServerAdministrator または CsAdministrator 役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="7264c-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="7264c-119">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7264c-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7264c-120">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7264c-120">Run the following at the command prompt:</span></span>
    
  ```
  Get-CsDialinConferencingConfiguration
  ```

<span data-ttu-id="7264c-121">このコマンドレットでは、参加者が会議に参加するときに自分の名前を記録する必要がかどうかと、参加者の参加またはダイヤルイン会議のままにするときの Skype ビジネス サーバーの応答に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="7264c-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="7264c-122">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7264c-122">Run the following at the command prompt:</span></span>
    
  ```
  Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
[-EnableNameRecording <$true | $false>]
[-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
[-EntryExitAnnouncementsType <UseNames | ToneOnly]
  ```

<span data-ttu-id="7264c-p106">次の例では、設定が Redmond のサイト スコープで定義されます。アナウンスはオンにされますが、会議に参加するときに名前を言うように参加者が求められることはありません。参加者が会議に出席または会議から退席するときには、トーン音が再生されます。</span><span class="sxs-lookup"><span data-stu-id="7264c-p106">In the following example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference:</span></span>
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="7264c-126">詳細については、構文やパラメーターの完全なリストを含む[セット CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7264c-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

