---
title: "会議移行サービス (MM) を設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Skype for Business のサービスをバック グラウンドで実行され、自動的に Skype ユーザー向けのビジネスや Microsoft チーム会議の更新プログラムは、会議の移行サービス (MM)。MMS は、会議の移行ツールを実行するユーザーが Skype for Business や Microsoft チームの会議を更新する必要を消すために設計されています。"
ms.openlocfilehash: 0d33efb2f60a06853ba26cd6e525f624114c95a5
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="47f30-104">会議移行サービス (MM) を設定します。</span><span class="sxs-lookup"><span data-stu-id="47f30-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="47f30-p102">Skype for Business のサービスをバック グラウンドで実行され、自動的に Skype ユーザー向けのビジネスや Microsoft チーム会議の更新プログラムは、会議の移行サービス (MM)。MMS は、会議の移行ツールを実行するユーザーが Skype for Business や Microsoft チームの会議を更新する必要を消すために設計されています。</span><span class="sxs-lookup"><span data-stu-id="47f30-p102">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>
  
 <span data-ttu-id="47f30-107">**要件**</span><span class="sxs-lookup"><span data-stu-id="47f30-107">**Requirements**</span></span>
  
<span data-ttu-id="47f30-108">MMS では、会議の開催者に Exchange Online のメールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="47f30-108">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="47f30-109">**主なシナリオ**</span><span class="sxs-lookup"><span data-stu-id="47f30-109">**Primary scenarios**</span></span>
  
<span data-ttu-id="47f30-110">MMS では、次の 2 つの主なシナリオのユーザーの Skype 会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="47f30-110">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="47f30-111">ユーザーが内部設置型の Skype から for Business Server に移行 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="47f30-111">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="47f30-112">ときに管理者は、そのユーザーの会議の電話会議情報を更新が必要となるユーザーの電話会議の設定に変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="47f30-112">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="47f30-113">**一般的なシナリオを MMS を使うことはできません。**</span><span class="sxs-lookup"><span data-stu-id="47f30-113">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="47f30-p103">ここでは、いくつかの一般的なシナリオに適用することがあります。移行のサポートされているすべてのシナリオです。ただし、MMS は、次のシナリオで実行できないため、代わりに、[会議の移行ツール](https://go.microsoft.com/fwlink/p/?linkid=626047)を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47f30-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="47f30-117">ユーザーのメールボックスが Exchange Server を自</span><span class="sxs-lookup"><span data-stu-id="47f30-117">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="47f30-118">サードパーティ電話会議プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="47f30-118">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="47f30-119">Skype for Business Online から内部設置型の Skype サーバーにユーザーを移行</span><span class="sxs-lookup"><span data-stu-id="47f30-119">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="47f30-120">オンプレミスのユーザーを移行 Skype for Business Online ときに、会議を更新</span><span class="sxs-lookup"><span data-stu-id="47f30-120">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="47f30-p104">これは、場所 MMS に役立つ滑らかなユーザーの画面切り替えを作成する最も一般的なシナリオです。ユーザーから移行されるを内部設置型の Skype for Business Server skype for Business Online、MMS は、新しいユーザーを検出し、Skype for Business と Microsoft チーム会議のユーザーの予定表をスキャンします。今後のすべての会議は、そのユーザーの新しい情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="47f30-p104">This is the most common scenario where MMS can help create a smoother transition for your users. When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="47f30-124">現在、電話会議に Skype Server 2015 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="47f30-124">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="47f30-125">このシナリオで MMS に最適な操作性の下にあるベスト プラクティスに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47f30-125">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="47f30-126">MMS には、Exchange Online では、上にも、オンプレミスの Exchange Server にもから移行する場合は、ユーザーのメールボックスが必要であるために、最初に Exchange Online にユーザーのメールボックスを移動します。</span><span class="sxs-lookup"><span data-stu-id="47f30-126">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="47f30-p105">実行する前に、ユーザーに**電話会議**ライセンスを割り当てて、`Move-CSUser`コマンドレット ユーザーを移行します。MMS は、ユーザーの電話会議の設定が変更されたときにも会議を更新するためです。最初にライセンスを割り当ててしない、MMS が更新のすべての会議もう一度ライセンスを割り当てるとされます。</span><span class="sxs-lookup"><span data-stu-id="47f30-p105">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="47f30-130">現在、サードパーティ電話会議プロバイダー (ACP) を使用している場合</span><span class="sxs-lookup"><span data-stu-id="47f30-130">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="47f30-p106">サードパーティ acp を MMS を実行するかどうかは、組織の電話会議の設定に依存します。**電話会議**ライセンスをユーザーに割り当てるときに、ACP からダイヤルイン番号が自動的に置き換えることができます。その一方で、しまわないようにし、ACP からダイヤルイン番号を保持する必要があります。組織の設定を表示するには、次の Windows PowerShell コマンドを実行して、パラメーターの値をチェック`AutomaticallyReplaceAcpProvider`します。PowerShell でヘルプを必要がある場合は、この記事の最後にある [ [PowerShell による Skype for Business の組織の管理](setting-up-the-meeting-migration-service-mms.md#WPSInfo)] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47f30-p106">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP. To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="47f30-p107">このパラメーターの値が $true の場合は、MMS がユーザーには、**電話会議**のライセンスが割り当てられているときに実行し、会議を更新します。**電話会議**のライセンスが割り当てられるまで、ACP からダイヤルイン番号が保持されます。</span><span class="sxs-lookup"><span data-stu-id="47f30-p107">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="47f30-p108">このパラメーターの値が $false の場合は、[MMS を更新しません会議場合でも、ユーザーには、**電話会議**には、ライセンスが割り当てられています。ユーザーが手動で自動的にプロビジョニング Business 管理センター」または「Windows PowerShell を使用するため Skype で電話会議になるまで ACP からダイヤルイン番号が保持されます。</span><span class="sxs-lookup"><span data-stu-id="47f30-p108">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="47f30-140">ユーザーの電話会議の設定を変更するときに、会議を更新</span><span class="sxs-lookup"><span data-stu-id="47f30-140">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="47f30-141">次のような場合、ビジネスや Microsoft チーム会議の既存の Skype MMS が更新されます。</span><span class="sxs-lookup"><span data-stu-id="47f30-141">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="47f30-142">ときに、割り当てるか、**音声会議**ライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="47f30-142">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="47f30-143">有効にすると、または電話会議を無効にします。</span><span class="sxs-lookup"><span data-stu-id="47f30-143">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="47f30-144">変更するか、一般向けの会議を使うように構成するユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="47f30-144">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="47f30-145">ユーザーを新しい電話会議ブリッジに移動するとします。</span><span class="sxs-lookup"><span data-stu-id="47f30-145">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="47f30-p109">電話番号では、電話会議ブリッジの割り当てはできません。これは、複雑な状況で、追加の手順が必要です。詳細については、[変更の有料またはフリー ダイヤルの無料番号で電話会議ブリッジ](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47f30-p109">When a phone number is unassigned from a audio conferencing bridge. This is a complex scenario which requires additional steps. For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="47f30-p110">MMS では、Microsoft ブリッジを使用している場合に会議を更新のみです。ユーザーが自分の会議を更新する必要がありますサードパーティ電話会議プロバイダーを使用している場合は、手動でします。この例では、[会議の移行ツール](https://go.microsoft.com/fwlink/p/?linkid=626047)を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="47f30-p110">MMS only updates meetings when you're using the Microsoft bridge. If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="47f30-p111">ユーザーの電話会議の設定をすべての変更は、MMS を開始します。具体的には、次の 2 つの変更は、会議の更新 MMS で発生するされません。</span><span class="sxs-lookup"><span data-stu-id="47f30-p111">Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="47f30-154">(SIP ユーザー名またはドメインの) 会議の開催者の SIP アドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="47f30-154">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="47f30-155">[更新 CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442)コマンドを使用して、組織の会議 URL を変更するとします。</span><span class="sxs-lookup"><span data-stu-id="47f30-155">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="47f30-156">MMS 会議を更新するときの動作</span><span class="sxs-lookup"><span data-stu-id="47f30-156">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="47f30-157">MMS では、ユーザーの会議を更新する必要があることを検出すると、次の操作を行いますが。</span><span class="sxs-lookup"><span data-stu-id="47f30-157">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="47f30-158">すべての Skype for Business および Microsoft チームの会議をユーザーは、今後のスケジュールを特定します。</span><span class="sxs-lookup"><span data-stu-id="47f30-158">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="47f30-159">MMS の実行時に、前に発生した Business または Microsoft チーム会議の Skype をスキップします。</span><span class="sxs-lookup"><span data-stu-id="47f30-159">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="47f30-160">開催者である会議のみの更新します。</span><span class="sxs-lookup"><span data-stu-id="47f30-160">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="47f30-161">置換、オンライン会議で、会議の詳細情報のブロック</span><span class="sxs-lookup"><span data-stu-id="47f30-161">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="47f30-162">会議の開催者の代わりに会議のすべての受信者に更新を送信します。</span><span class="sxs-lookup"><span data-stu-id="47f30-162">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="47f30-163">**MMS を実行するはどのくらい時間がかかりますか。**</span><span class="sxs-lookup"><span data-stu-id="47f30-163">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="47f30-p112">会議を移行する MMS にかかる時間は、ユーザーの数が影響を受けると Business または Microsoft チーム会議の各ユーザーには、予定表での Skype の合計数によって異なります。最低でも、そのを実行する 10 分しか時間がかかります。大規模ないくつかの移行には、最大 12 時間がかかる場合も、中には、"1 hour"内にほとんどの移行が完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47f30-p112">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. At a minimum, it will take 10 minutes to run. While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="47f30-167">**制限と潜在的な問題**</span><span class="sxs-lookup"><span data-stu-id="47f30-167">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="47f30-p113">[Skype for Business または Microsoft チームの会議がスケジュールされているは、Web 版 Outlook に**追加する Skype 会議**] をクリックして、または Outlook で Skype 会議アドインを使用しているのみは移行されます。つまり、ユーザーは、コピーし、新しい会議を 1 つの会議から Skype のオンライン会議の情報を貼り付けます、その他の会議が更新されません。</span><span class="sxs-lookup"><span data-stu-id="47f30-p113">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="47f30-p114">オンライン会議の情報をすべてブロックする会議を移行する場合 MMS 置き換えます。このため、ユーザーがそのブロックを編集した場合、変更内容が上書きされます。会議の詳細であるすべての内容をオンライン会議の情報の外部でブロックは影響されません。</span><span class="sxs-lookup"><span data-stu-id="47f30-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![会議のブロック MMS によって更新を取得します。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="47f30-p115">MMS を実行した後、会議を作成または (ホワイト ボード、ポーリングなど)、会議に添付されたコンテンツは保持されません。会議の開催者、会議には、コンテンツを事前に接続された、コンテンツは MMS の実行後に再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47f30-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="47f30-p116">予定表のアイテムでメモの共有の会議へのリンクもから内での Skype 会議もは上書きされます。実際の会議のメモを OneNote に保存されている場合でもはあるメモには、共有のノートには上書きされますリンクのみです。</span><span class="sxs-lookup"><span data-stu-id="47f30-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="47f30-178">会議出席者は 250 を超える (開催者を含む) は移行されません。</span><span class="sxs-lookup"><span data-stu-id="47f30-178">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="47f30-179">招待状の本文に UNICODE 文字の一部可能性がありますが正しく更新されない次の特殊文字のいずれかに: ï、¿、½、します。</span><span class="sxs-lookup"><span data-stu-id="47f30-179">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="47f30-180">ユーザーに表示 MMS が、会議を更新するとよいですか。</span><span class="sxs-lookup"><span data-stu-id="47f30-180">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="47f30-p117">MMS を会議の移行ツールと同じようには、ユーザーの代理として会議の更新を送信します。このためはの会議の会議の通知を承諾] が表示だけです。変更を行った場合電話会議をトリガー MMS に移行したオンプレミスから Skype for Business Online や場合だけでなく事前にユーザーに通知することをお勧めように、ユーザーは、混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47f30-p117">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="47f30-184">MMS を管理します。</span><span class="sxs-lookup"><span data-stu-id="47f30-184">Managing MMS</span></span>

<span data-ttu-id="47f30-p118">Windows PowerShell を使用して MMS を管理し、継続的な移行の状態を確認する必要があります。このセクションの情報は、使い慣れた PowerShell を使用して、Skype for Business の組織を管理するものとします。新しい PowerShell 場合は、この記事の最後にある [ [PowerShell による Skype for Business の組織の管理](setting-up-the-meeting-migration-service-mms.md#WPSInfo)] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47f30-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="47f30-188">会議の移行の状態を確認する方法は?</span><span class="sxs-lookup"><span data-stu-id="47f30-188">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="47f30-p119">使用する、`Get-CsMeetingMigrationStatus`コマンドレットに移行する場合に会議の状態を確認します。以下は、いくつかの例です。</span><span class="sxs-lookup"><span data-stu-id="47f30-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="47f30-191">すべての MMS 移行のステータスの概要を移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="47f30-191">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="47f30-192">これにより、次のようなすべての移行の状態の表形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="47f30-192">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="47f30-193">状態 UserCount--</span><span class="sxs-lookup"><span data-stu-id="47f30-193">State UserCount---------------</span></span><br/> <span data-ttu-id="47f30-194">保留中の 21</span><span class="sxs-lookup"><span data-stu-id="47f30-194">Pending 21</span></span><br/><span data-ttu-id="47f30-195">InProgress 6</span><span class="sxs-lookup"><span data-stu-id="47f30-195">InProgress 6</span></span><br/> <span data-ttu-id="47f30-196">失敗 2</span><span class="sxs-lookup"><span data-stu-id="47f30-196">Failed 2</span></span> <br/> <span data-ttu-id="47f30-197">成功 131</span><span class="sxs-lookup"><span data-stu-id="47f30-197">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="47f30-p120">任意の移行に失敗した場合は、可能な限り早くこれらの問題を解決するのには処理します。ユーザーはこれらに対処するまでは、それらのユーザーが開催する会議にダイヤルインすることはできません。参照してください、[エラーが発生する場合は何ですか?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="47f30-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="47f30-p121">すべての移行の完全な詳細情報を移動するには、特定の期間内で、使用することができます、`StartTime`と`EndTime`パラメーターします。たとえば、次のコマンド完全な詳細情報が発生したすべての移行に 2016 年 10 月 1 日からに戻ります 2016 年 10 月 8 日。</span><span class="sxs-lookup"><span data-stu-id="47f30-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="47f30-p122">するには、特定のユーザーの移行の状態を確認し、使用することができます、`UserId`そのパラメーターします。たとえば、次のコマンドでは、ユーザー ashaw@contoso.com の状態が返されます。</span><span class="sxs-lookup"><span data-stu-id="47f30-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="47f30-205">エラーがある場合は、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="47f30-205">What do I do if there is an error?</span></span>
<span data-ttu-id="47f30-206"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="47f30-206"></span></span>

<span data-ttu-id="47f30-207">実行すると、`Get-CsMeetingMigrationStatus`コマンドレットをサマリー ビューを取得し、失敗状態に移行する場合がありますが、実行する必要があるかを示します。</span><span class="sxs-lookup"><span data-stu-id="47f30-207">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="47f30-p123">どのユーザーには影響を確認します。影響を受けるユーザー] の一覧と特定のエラーが報告されたにアクセスするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="47f30-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="47f30-210">これらのユーザーごとに、自分の会議を手動で移行するのには、[会議の移行ツール](https://go.microsoft.com/fwlink/p/?linkid=626047)を実行します。</span><span class="sxs-lookup"><span data-stu-id="47f30-210">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="47f30-211">移行を会議の移行ツールを使用して解消されない場合は、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="47f30-211">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="47f30-212">新しい Skype 会議を作成するユーザーが存在します。</span><span class="sxs-lookup"><span data-stu-id="47f30-212">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="47f30-213">[連絡先をサポート](https://go.microsoft.com/fwlink/p/?LinkID=518322)します。</span><span class="sxs-lookup"><span data-stu-id="47f30-213">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="47f30-214">有効にして、MMS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="47f30-214">Enabling and disabling MMS</span></span>
<span data-ttu-id="47f30-215"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="47f30-215"></span></span>

<span data-ttu-id="47f30-p124">MMS が既定では、組織全体で有効になっているが、必要に応じて、無効にできます。たとえば、すべての会議を手動で移行する場合、またはサードパーティ電話会議プロバイダーを使っている場合を実行している MMS いない必要があります。また、MMS を一時的に無効にすることもできます。たとえば、することがあるよりも大幅変更電話会議の設定] を組織のおよび操作 MMS にすべての変更が完了するまで動作しません。</span><span class="sxs-lookup"><span data-stu-id="47f30-p124">MMS is enabled by default for all organizations, but it can be disabled as needed. For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. You may also choose to temporarily disable MMS. For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="47f30-p125">表示する、組織の MMS が有効になっているかどうかは、次のコマンドを実行しの値を確認、`MeetingMigrationEnabled`パラメーターします。このパラメーターが $true に設定されている場合は、MMS が有効になります。</span><span class="sxs-lookup"><span data-stu-id="47f30-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="47f30-222">MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="47f30-222">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="47f30-223">MMS を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="47f30-223">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="47f30-224">有効にして、電話会議の変更に関するのみ MMS を無効にします。</span><span class="sxs-lookup"><span data-stu-id="47f30-224">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="47f30-225"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="47f30-225"></span></span>

<span data-ttu-id="47f30-p126">電話会議の変更に関するのみ MMS 無効にすることもできます。ユーザーから移行される Skype ビジネス オンプレミス用 skype for Business Online ときも実行されます。電話会議の更新プログラムの現在の MMS 状態を確認するには、次のコマンドを実行しての値を確認、`AutomaticallyMigrateUserMeetings`パラメーターします。このパラメーターが $true に設定されている場合は、MMS が電話会議の設定が変更されたときに、ユーザーの会議を更新する設定されています。</span><span class="sxs-lookup"><span data-stu-id="47f30-p126">You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="47f30-230">電話会議を MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="47f30-230">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="47f30-231">電話会議を MMS を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="47f30-231">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="47f30-232">実行方法会議移行手動で特定のユーザーのですか。</span><span class="sxs-lookup"><span data-stu-id="47f30-232">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="47f30-233"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="47f30-233"></span></span>

<span data-ttu-id="47f30-p127">に加えて、会議の自動移行する場合、**開始 CsExMeetingMigration**コマンドレットを実行して手動で特定のユーザーの会議の移行を実行することもできます。このコマンドレットでは、会議の移行キュー内のユーザーを追加します。移行サービスの会議、ユーザー リクエストし、会議を移行します。コマンドレット**Get CsMeetingMigrationStatus**移行を会議の状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="47f30-p127">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**. This cmdlet adds the user in meeting migration queue. Meeting Migration Service will read the user request and migrate their meetings. You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="47f30-238">ユーザー ashaw@contoso.com の会議の移行を開始する例を示します。</span><span class="sxs-lookup"><span data-stu-id="47f30-238">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="47f30-239">PowerShell を使用して、Skype for Business の組織を管理するには</span><span class="sxs-lookup"><span data-stu-id="47f30-239">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="47f30-240"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="47f30-240"></span></span>

 <span data-ttu-id="47f30-241">**3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="47f30-241">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="47f30-242">3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="47f30-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="47f30-243">**Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="47f30-243">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="47f30-p128">バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="47f30-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="47f30-p129">Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="47f30-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="47f30-250">さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47f30-250">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="47f30-251">**Windows PowerShell セッションを開始します。**</span><span class="sxs-lookup"><span data-stu-id="47f30-251">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="47f30-252">**[スタート] メニュー**から > **Windows PowerShell**します。</span><span class="sxs-lookup"><span data-stu-id="47f30-252">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="47f30-253">**Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="47f30-253">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47f30-254">Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。</span><span class="sxs-lookup"><span data-stu-id="47f30-254">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="47f30-255">詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47f30-255">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="47f30-p130">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47f30-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="47f30-259">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="47f30-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="47f30-260">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="47f30-260">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="47f30-p131">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="47f30-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="47f30-263">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="47f30-263">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="47f30-264">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="47f30-264">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="47f30-265">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="47f30-265">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="47f30-266">関連トピック</span><span class="sxs-lookup"><span data-stu-id="47f30-266">Related topics</span></span>

[<span data-ttu-id="47f30-267">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="47f30-267">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
