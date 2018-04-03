---
title: Meeting Migration Service (MMS) のセットアップ
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Meeting Migration Service (MMS) は Skype for Business サービスの 1 つで、バックグラウンドで動作して、ユーザーのために Skype for Business および Microsoft Teams 会議を自動的に更新します。MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。
ms.openlocfilehash: 46f7c0223c88b7a4a3aa3a553e14df85ce86835d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="9fe07-104">Meeting Migration Service (MMS) のセットアップ</span><span class="sxs-lookup"><span data-stu-id="9fe07-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="9fe07-p102">[] Meeting Migration Service (MMS) は Skype for Business サービスの 1 つで、バックグラウンドで動作して、ユーザーのために Skype for Business および Microsoft Teams 会議を自動的に更新します。MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p102">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>
  
 <span data-ttu-id="9fe07-107">**要件**</span><span class="sxs-lookup"><span data-stu-id="9fe07-107">**Requirements**</span></span>
  
<span data-ttu-id="9fe07-108">MMS では、会議の開催者のメールボックスを Exchange Online で利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fe07-108">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="9fe07-109">**主要シナリオ**</span><span class="sxs-lookup"><span data-stu-id="9fe07-109">**Primary scenarios**</span></span>
  
<span data-ttu-id="9fe07-110">MMS は次の 2 つの主要シナリオでユーザーのために Skype 会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-110">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="9fe07-111">ユーザーがオンプレミスの Skype for Business Server から Skype for Business Online に移行される場合。</span><span class="sxs-lookup"><span data-stu-id="9fe07-111">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="9fe07-112">管理者が、ユーザーの会議内の電話会議情報を更新する必要が生じる変更を、ユーザーの電話会議設定に対して行う場合。</span><span class="sxs-lookup"><span data-stu-id="9fe07-112">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="9fe07-113">**MMS を使用できない一般的なシナリオ**</span><span class="sxs-lookup"><span data-stu-id="9fe07-113">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="9fe07-p103">該当する可能性のある一般的なシナリオを次に示します。これらのシナリオはすべて移行でサポートされます。ただし、MMS はこれらのシナリオでは動作せず、代わりに [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="9fe07-117">ユーザーのメールボックスが Exchange Server のオンプレミスにある</span><span class="sxs-lookup"><span data-stu-id="9fe07-117">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="9fe07-118">サードパーティ電話会議プロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="9fe07-118">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="9fe07-119">Skype for Business Online からオンプレミスの Skype Server に移行する</span><span class="sxs-lookup"><span data-stu-id="9fe07-119">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="9fe07-120">オンプレミスのユーザーが Skype for Business Online に移行されるときに会議を更新する</span><span class="sxs-lookup"><span data-stu-id="9fe07-120">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="9fe07-p104">これは、MMS がユーザーのスムーズな移行に役立つ、最も一般的なシナリオです。ユーザーがオンプレミスの Skype for Business Server から Skype for Business Online に移行されるときに、MMS は新しいユーザーを検出してそのユーザーの予定表に Skype for Business 会議と Microsoft Teams 会議がないかスキャンします。今後の会議はすべて、そのユーザーの新しい情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p104">This is the most common scenario where MMS can help create a smoother transition for your users. When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="9fe07-124">現在 Skype Server 2015 を電話議で使用している場合</span><span class="sxs-lookup"><span data-stu-id="9fe07-124">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="9fe07-125">このシナリオでは、MMS による最高のエクスペリエンスを得るために下記のベスト プラクティスに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9fe07-125">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="9fe07-126">MMS ではユーザーのメールボックスを Exchange Online で利用できる状態にする必要があるため、オンプレミスの Exchange Server からの移行も実行している場合は、先にユーザーのメールボックスを Exchange Online に移動します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-126">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="9fe07-p105">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.</span><span class="sxs-lookup"><span data-stu-id="9fe07-p105">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="9fe07-130">現在サードパーティの音声会議プロバイダー (ACP) を使用している場合</span><span class="sxs-lookup"><span data-stu-id="9fe07-130">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="9fe07-p106">サードパーティの ACP では、MMS が動作するかしないかは所属する組織のダイヤルイン会議設定に応じて変わります。 **電話会議**ライセンスをユーザーに割り当てるときに、自動的に ACP からのダイヤルイン番号を置き換えることを選べます。一方、そのようにせずに、ダイヤルイン番号を ACP からのダイヤルイン番号を保持する必要がある場合もあります。所属する組織の設定を確認するには、次の Windows PowerShell コマンドを実行して、パラメーター  `AutomaticallyReplaceAcpProvider` の値を確認します。PowerShell についてサポートが必要な場合は、この記事の終わりにある「[PowerShell を使用した Skype for Business の組織の管理](setting-up-the-meeting-migration-service-mms.md#WPSInfo)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p106">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP. To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="9fe07-p107">このパラメーターの値が $true の場合、MMS はユーザーに **電話会議**ライセンスが割り当てられるときに動作して、会議を更新します。 **電話会議**ライセンスが割り当てられるまで、ACP からのダイヤルイン番号は保持されます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p107">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="9fe07-p108">このパラメーターの値が $false の場合、ユーザーに **電話会議**ライセンスが割り当てられても MMS は会議を更新しません。ユーザーが Skype for Business 管理センターで、または Windows PowerShell を使用して電話会議に対して手動でプロビジョニングされるまで、ACP からのダイヤルイン番号は保持されます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p108">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="9fe07-140">ユーザーの電話会議の設定が変更されるときの会議の更新</span><span class="sxs-lookup"><span data-stu-id="9fe07-140">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="9fe07-141">MMS は次の場合に既存の Skype for Business Online および Microsoft Teams の会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-141">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="9fe07-142">**電話会議**ライセンスを割り当てる、または削除する場合</span><span class="sxs-lookup"><span data-stu-id="9fe07-142">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="9fe07-143">電話会議を有効または無効にする場合</span><span class="sxs-lookup"><span data-stu-id="9fe07-143">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="9fe07-144">パブリック会議を使用するよう構成されたユーザーの会議 ID を変更またはリセットする場合</span><span class="sxs-lookup"><span data-stu-id="9fe07-144">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="9fe07-145">ユーザーを新しい電話会議ブリッジに移行する場合</span><span class="sxs-lookup"><span data-stu-id="9fe07-145">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="9fe07-p109">電話番号が電話会議ブリッジから割り当てられていない場合。これは複雑なシナリオで、追加手順を必要とします。詳細については、「[電話会議ブリッジの有料または無料の電話番号を変更する](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p109">When a phone number is unassigned from a audio conferencing bridge. This is a complex scenario which requires additional steps. For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="9fe07-p110">Microsoft ブリッジを使用している場合、MMS は会議の更新のみを行います。サードパーティの電話会議プロバイダーを使用している場合、ユーザーは会議を手動で更新する必要があります。この場合、[Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p110">MMS only updates meetings when you're using the Microsoft bridge. If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="9fe07-p111">ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。特に、次の 2 つの変更では、MMS によって会議が更新されません。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p111">Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="9fe07-154">会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)</span><span class="sxs-lookup"><span data-stu-id="9fe07-154">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="9fe07-155">[Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) コマンドを使用して組織の会議 URL を変更する場合。</span><span class="sxs-lookup"><span data-stu-id="9fe07-155">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="9fe07-156">MMS が会議を更新するときに発生すること</span><span class="sxs-lookup"><span data-stu-id="9fe07-156">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="9fe07-157">MMS がユーザーの会議を更新する必要があることを検出すると、次の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-157">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="9fe07-158">ユーザーが今後にスケジュールしたすべての Skype for Business 会議および Microsoft Teams 会議を識別する</span><span class="sxs-lookup"><span data-stu-id="9fe07-158">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="9fe07-159">MMS が動作する前に発生したすべての Skype for Business 会議および Microsoft Teams 会議がスキップされる</span><span class="sxs-lookup"><span data-stu-id="9fe07-159">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="9fe07-160">ユーザーが開催者である会議のみが更新される</span><span class="sxs-lookup"><span data-stu-id="9fe07-160">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="9fe07-161">会議の詳細のオンライン会議の情報ブロックを置き換える</span><span class="sxs-lookup"><span data-stu-id="9fe07-161">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="9fe07-162">会議の開催者に代わって、更新内容をすべての会議出席依頼の受信者に送信する</span><span class="sxs-lookup"><span data-stu-id="9fe07-162">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="9fe07-163">**MMS が動作するまでにかかる時間**</span><span class="sxs-lookup"><span data-stu-id="9fe07-163">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="9fe07-p112">MMS が会議を移行するのにかかる時間の量は、影響するユーザーの数、各ユーザーが予定表に抱えている Skype for Business 会議および Microsoft Teams 会議の合計数によって変わります。少なくとも、動作するのに 10 分はかかります。一部の大規模な移行は最大 12 時間かかりますが、多くの移行は 1 時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p112">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. At a minimum, it will take 10 minutes to run. While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="9fe07-167">**制限事項と潜在的な問題**</span><span class="sxs-lookup"><span data-stu-id="9fe07-167">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="9fe07-p113">Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。このため、ユーザーがある会議から新しい会議に Skype オンライン会議の情報をコピーして貼り付ける場合は、その新しい会議は更新されません。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p113">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="9fe07-p114">MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="9fe07-p115">作成された、または会議に添付された会議コンテンツ (ホワイトボード、投票など) は、MMS が動作すると保持されません。会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="9fe07-p116">予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。OneNote に保存される実際の会議ノートは引き続きその場所に存在し、共有のノートへのリンクのみが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="9fe07-178">(開催者を含めて) 250 人を超える参加者がいる会議は移行できません。</span><span class="sxs-lookup"><span data-stu-id="9fe07-178">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="9fe07-179">会議出席依頼の本文の UNICODE 文字の一部が間違って特殊文字 ï、¿、½、� に置き換えられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fe07-179">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="9fe07-180">MMS によって会議が更新されるときにユーザーには何が表示されますか。</span><span class="sxs-lookup"><span data-stu-id="9fe07-180">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="9fe07-p117">会議移行ツールと同様に、MMS はユーザーに代わって会議の更新を送信します。このため、ユーザーに表示されるのは、別の機会の会議承諾通知のみになります。これはユーザーにとって分かりにくい可能性があるため、ユーザーをオンプレミスから Skype for Business Online に移行するときだけではなく、MMS をトリガーする電話会議の変更を行うときにも、ユーザーに事前に通知することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p117">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="9fe07-184">MMS の管理</span><span class="sxs-lookup"><span data-stu-id="9fe07-184">Managing MMS</span></span>

<span data-ttu-id="9fe07-p118">Windows PowerShell を使用して MMS を管理し、進行中の移行のステータスを確認する必要があります。このセクションの情報は、PowerShell を使用した Skype for Business の組織の管理に慣れていることを前提としています。新しい PowerShell を使用する場合は、この記事の最後にある「[PowerShell を使用した Skype for Business の組織の管理](setting-up-the-meeting-migration-service-mms.md#WPSInfo)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="9fe07-188">会議の移行のステータスを確認する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-188">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="9fe07-p119">`Get-CsMeetingMigrationStatus` コマンドレットを使用して、会議の移行のステータスを確認します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="9fe07-191">すべての MMS の移行に関する概要ステータスを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-191">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="9fe07-192">これによって、すべての移行状態が次のように表形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-192">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="9fe07-193">UserCount の状態--</span><span class="sxs-lookup"><span data-stu-id="9fe07-193">State UserCount---------------</span></span><br/> <span data-ttu-id="9fe07-194">保留中の 21</span><span class="sxs-lookup"><span data-stu-id="9fe07-194">Pending 21</span></span><br/><span data-ttu-id="9fe07-195">InProgress 6</span><span class="sxs-lookup"><span data-stu-id="9fe07-195">InProgress 6</span></span><br/> <span data-ttu-id="9fe07-196">失敗 2</span><span class="sxs-lookup"><span data-stu-id="9fe07-196">Failed 2</span></span> <br/> <span data-ttu-id="9fe07-197">成功 131</span><span class="sxs-lookup"><span data-stu-id="9fe07-197">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="9fe07-p120">移行が失敗したことを確認した場合は、それらの問題を解決する措置をできるだけ早く行います。問題に対処するまで、これらのユーザーによって開催される会議にダイヤルインすることはできません。詳細については、「[エラーが発生した場合の対処方法を教えてください。](setting-up-the-meeting-migration-service-mms.md#Troubleshooting)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="9fe07-p121">特定の期間内におけるすべての移行の詳細を取得する場合に、 `StartTime` および `EndTime` パラメーターを使用できます。たとえば、次のコマンドを実行すると、2016 年 10 月 1 日から 2016 年 10 月 8 日に発生したすべての移行の詳細が返されます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="9fe07-p122">特定のユーザーに関する移行のステータスを確認することもできます。この場合は  `UserId` パラメーターを使用できます。たとえば、次のコマンドを実行すると、ユーザー ashaw@contoso.com に関するステータスが返されます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="9fe07-205">エラーが発生した場合の対処方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-205">What do I do if there is an error?</span></span>
<span data-ttu-id="9fe07-206"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="9fe07-206"></span></span>

<span data-ttu-id="9fe07-207">`Get-CsMeetingMigrationStatus` コマンドレットを実行して概要ビューを表示すると、状態が 失敗となっている移行が確認される場合があります。対処方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9fe07-207">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="9fe07-p123">影響を受けているユーザーを特定します。次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="9fe07-210">これらのユーザーそれぞれに対して、[会議移行ツール](https://go.microsoft.com/fwlink/p/?linkid=626047)を実行して、手動で会議を移行します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-210">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="9fe07-211">会議移行ツールを使用しても移行が機能しない場合には、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="9fe07-211">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="9fe07-212">ユーザーに新しい Skype 会議を作成してもらいます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-212">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="9fe07-213">[サポートに問い合わせます](https://go.microsoft.com/fwlink/p/?LinkID=518322)。</span><span class="sxs-lookup"><span data-stu-id="9fe07-213">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="9fe07-214">MMS の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="9fe07-214">Enabling and disabling MMS</span></span>
<span data-ttu-id="9fe07-215"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="9fe07-215"></span></span>

<span data-ttu-id="9fe07-p124">MMS は既定ではすべての組織で有効になっていますが、必要に応じて無効にすることができます。たとえば、すべての会議を手動で移行する場合や、サードパーティ電話会議プロバイダーを使用する場合は、MMS の動作は必要ありません。また、MMS を一時的に無効にすることがあります。たとえば、組織の電話会議の設定に多数の変更を加える場合で、すべての変更作業が完了するまで MMS を動作させないようにするときがこれに該当します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p124">MMS is enabled by default for all organizations, but it can be disabled as needed. For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. You may also choose to temporarily disable MMS. For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="9fe07-p125">所属する組織で MMS が有効になっているかどうかを確認するには、次のコマンドを実行して、 `MeetingMigrationEnabled` パラメーターの値を確認します。このパラメーターが$true に設定されている場合、MMS が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="9fe07-222">MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-222">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="9fe07-223">MMS を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-223">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="9fe07-224">電話会議の変更に対して限定した MMS の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="9fe07-224">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="9fe07-225"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="9fe07-225"></span></span>

<span data-ttu-id="9fe07-p126">電話会議の変更に対してのみ、MMS を無効にすることもできます。これは、ユーザーがオンプレミスの Skype for Business から Skype for Business Online に移行した場合でも引き続き実行されます。電話会議の更新に関する現在の MMS の状態を確認するには、次のコマンドを実行して、 `AutomaticallyMigrateUserMeetings` パラメーターの値を確認します。このパラメーターが$true に設定されている場合は、MMS は電話会議の設定が変更された場合にユーザー会議を更新するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p126">You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="9fe07-230">電話会議に関して MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-230">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="9fe07-231">電話会議に関して MMS を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-231">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="9fe07-232">ユーザーのために手動で会議移行を実行する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-232">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="9fe07-233"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="9fe07-233"></span></span>

<span data-ttu-id="9fe07-p127">自動的な会議移行の他に、コマンドレット **Start-CsExMeetingMigration** を実行することによって、ユーザーのために手動で会議移行を実行することもできます。このコマンドレットはユーザーを会議移行キューに追加します。Meeting Migration Service (MMS) はユーザー リクエストを読み取り、会議を移行します。コマンドレット **Get-CsMeetingMigrationStatus** で会議移行の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p127">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**. This cmdlet adds the user in meeting migration queue. Meeting Migration Service will read the user request and migrate their meetings. You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="9fe07-238">ユーザー ashaw@contoso.com のために会議移行を開始する場合の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-238">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="9fe07-239">PowerShell を使用した Skype for Business の組織の管理</span><span class="sxs-lookup"><span data-stu-id="9fe07-239">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="9fe07-240"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="9fe07-240"></span></span>

 <span data-ttu-id="9fe07-241">**Windows PowerShell バージョン 3.0 以降を実行していることを確認する**</span><span class="sxs-lookup"><span data-stu-id="9fe07-241">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="9fe07-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9fe07-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9fe07-243">[ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-243">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="9fe07-p128">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="9fe07-p129">Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="9fe07-250">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-250">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="9fe07-251">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="9fe07-251">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="9fe07-252">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9fe07-252">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9fe07-253">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-253">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9fe07-254">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="9fe07-254">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="9fe07-255">Windows PowerShell の起動の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「[Windows PowerShell を使用した Lync Online への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-255">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="9fe07-p130">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9fe07-259">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="9fe07-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9fe07-260">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="9fe07-260">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="9fe07-p131">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="9fe07-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9fe07-263">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="9fe07-263">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="9fe07-264">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="9fe07-264">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9fe07-265">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="9fe07-265">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="9fe07-266">See also</span><span class="sxs-lookup"><span data-stu-id="9fe07-266">Related topics</span></span>

[<span data-ttu-id="9fe07-267">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="9fe07-267">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
