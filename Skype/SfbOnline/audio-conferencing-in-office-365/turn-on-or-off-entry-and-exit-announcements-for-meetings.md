---
title: Skype for Business Online で会議のエントリと退出のお知らせを有効または無効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business 管理センターを使用して、Skype for Business Online 会議で、エントリと退出のお知らせを有効または無効にする方法を説明します。 '
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779037"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="d6750-103">Skype for Business Online で会議のエントリと退出のお知らせを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="d6750-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="d6750-104">Microsoft Teams でのエントリと退出のお知らせについては、「[Microsoft Teams でエントリと退出のお知らせを有効または無効にする](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6750-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="d6750-105">Office 365 で電話会議を設定する場合、電話会議ブリッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6750-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="d6750-106">会議ブリッジには、ユーザーが Skype for Business 会議にコールインするのに使用する 1 つ以上の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d6750-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="d6750-107">会議ブリッジは、電話機を使用して会議にダイヤルインしようとしているユーザーの呼び出しに答えます。</span><span class="sxs-lookup"><span data-stu-id="d6750-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="d6750-108">会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="d6750-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="d6750-109">Skype for Business 会議の開催者には PIN が付与され、呼び出し元が Skype for Business アプリを使用して会議を開始できない場合は、その PIN を使用して会議を開始させることができます。</span><span class="sxs-lookup"><span data-stu-id="d6750-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="d6750-110">ただし、会議を開始するのに PIN が必要ないように設定をすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d6750-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="d6750-111">会議の参加オプションの設定</span><span class="sxs-lookup"><span data-stu-id="d6750-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="d6750-112">**Skype for Business 管理センター**の左側にあるナビゲーションで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="d6750-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="d6750-113">[ **会議参加のエクスペリエンス**] の下にある[**会議のエントリと退出の通知を有効にする**] を選択するかクリアします。</span><span class="sxs-lookup"><span data-stu-id="d6750-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="d6750-114">既定ではこれはすでに選択されています。</span><span class="sxs-lookup"><span data-stu-id="d6750-114">This is selected by default.</span></span> <span data-ttu-id="d6750-115">クリアすると、すでに会議に参加しているユーザーには、他のユーザーが会議にエントリ、または会議から退出した場合でも通知がされなくなります。</span><span class="sxs-lookup"><span data-stu-id="d6750-115">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="d6750-116">[**エントリ/退出のお知らせの種類**] の下にある [**名前または電話番号**] または [**トーン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6750-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="d6750-117">[**会議に参加する前に名前を記録するように参加者に依頼する**] をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="d6750-117">Ask callers to record their name before joining the meeting</span></span>
    
5. <span data-ttu-id="d6750-118">変更したら [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6750-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d6750-119">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="d6750-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d6750-120">時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6750-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="d6750-p104">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6750-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d6750-124">Windows PowerShell を使用しなければならない理由</span><span class="sxs-lookup"><span data-stu-id="d6750-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d6750-125">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="d6750-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="d6750-126">Windows PowerShell には、一度に多くのユーザー向けの設定変更をする場合など、速度、簡単さ、生産性の面で Office 365 管理センターだけを使用するよりも多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="d6750-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="d6750-127">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="d6750-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="d6750-128">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="d6750-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d6750-129">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="d6750-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d6750-130">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="d6750-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="d6750-p106">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="d6750-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d6750-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d6750-133">Related topics</span></span>

[<span data-ttu-id="d6750-134">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="d6750-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
