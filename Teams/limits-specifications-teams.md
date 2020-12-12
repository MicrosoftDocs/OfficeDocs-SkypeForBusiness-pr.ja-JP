---
title: Microsoft Teams の制限事項と仕様
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: この記事では、Microsoft Teams に適用される制限、仕様、およびその他の要件について説明します。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7b66ce5095d194f937f3bceeef23d2666c51d518
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611471"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="69080-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="69080-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="69080-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="69080-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="69080-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="69080-105">Teams and channels</span></span>

|<span data-ttu-id="69080-106">機能</span><span class="sxs-lookup"><span data-stu-id="69080-106">Feature</span></span>    | <span data-ttu-id="69080-107">上限</span><span class="sxs-lookup"><span data-stu-id="69080-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="69080-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="69080-108">Number of teams a user can create</span></span> | <span data-ttu-id="69080-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="69080-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="69080-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="69080-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="69080-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="69080-111">1,000&sup2;</span></span>|
|<span data-ttu-id="69080-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="69080-112">Number of members in a team</span></span> | <span data-ttu-id="69080-113">10,000<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="69080-113">10,000<sup>5</sup></span></span>     |
|<span data-ttu-id="69080-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="69080-114">Number of owners per team</span></span> | <span data-ttu-id="69080-115">100</span><span class="sxs-lookup"><span data-stu-id="69080-115">100</span></span>   |
|<span data-ttu-id="69080-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="69080-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="69080-117">5</span><span class="sxs-lookup"><span data-stu-id="69080-117">5</span></span>     |
|<span data-ttu-id="69080-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="69080-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="69080-119">5,000</span><span class="sxs-lookup"><span data-stu-id="69080-119">5,000</span></span>       |
|<span data-ttu-id="69080-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="69080-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="69080-121">500,000</span><span class="sxs-lookup"><span data-stu-id="69080-121">500,000</span></span>   |
|<span data-ttu-id="69080-122">Microsoft 365 または Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="69080-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="69080-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="69080-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="69080-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="69080-124">Number of channels per team</span></span>    | <span data-ttu-id="69080-125">200 (削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="69080-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="69080-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="69080-126">Number of Private channels per team</span></span>    |<span data-ttu-id="69080-127">30</span><span class="sxs-lookup"><span data-stu-id="69080-127">30</span></span>| <span data-ttu-id="69080-128">(削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="69080-128">(includes deleted channels)&sup3;</span></span>
|<span data-ttu-id="69080-129">プライベート チャネルのメンバー数</span><span class="sxs-lookup"><span data-stu-id="69080-129">Number of members in a Private channel</span></span>    |<span data-ttu-id="69080-130">250</span><span class="sxs-lookup"><span data-stu-id="69080-130">250</span></span>|
|<span data-ttu-id="69080-131">チームにインポートできる配布リスト、セキュリティ グループ、または Office 365 グループの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="69080-131">Maximum size of distribution list, security group or Office 365 group that can be imported in to a team</span></span>    |<span data-ttu-id="69080-132">3,500</span><span class="sxs-lookup"><span data-stu-id="69080-132">3,500</span></span>|
|<span data-ttu-id="69080-133">チームに変換できる Office 365 グループのメンバーの最大数</span><span class="sxs-lookup"><span data-stu-id="69080-133">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="69080-134">10,000<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="69080-134">10,000<sup>5</sup></span></span>     |
|<span data-ttu-id="69080-135">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="69080-135">Channel conversation post size</span></span> | <span data-ttu-id="69080-136">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="69080-136">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="69080-p101"><sup>1</sup> Azure Active Directory のすべてのディレクトリ オブジェクトはこの制限にカウントされます。グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="69080-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="69080-139"><sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="69080-139"><sup>2</sup> This limit includes archived teams.</span></span> <span data-ttu-id="69080-140">Microsoft 365 または Office 365 組織が保持できるチームの最大数を超えるには、Microsoft サポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69080-140">To go beyond the maximum number of teams a Microsoft 365 or Office 365 organization can have, you must contact Microsoft support.</span></span>

<span data-ttu-id="69080-p103"><sup>3</sup> 削除したチャネルは、30 日以内であれば復元できます。この 30 日間、削除されたチャネルはチームごとの制限である 200 チャネルまたは 30 のプライベート チャネルとしてカウントされ続けます。30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャネルはチームごとの制限内のチャネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="69080-p103"><sup>3</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="69080-144"><sup>4</sup> 28 KBは、メッセージ自体 (テキスト、画像リンクなど)、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="69080-144"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="69080-145"><sup>5</sup> GCC の チーム は 5,000 人のメンバーしか収容できず、GCCH / DoD のチームは 2,500 人のメンバーしか収容できません。</span><span class="sxs-lookup"><span data-stu-id="69080-145"><sup>5</sup> Teams in GCC can only accommodate 5,000 members and teams in GCCH/DoD can only accommodate 2,500 members.</span></span>

## <a name="messaging"></a><span data-ttu-id="69080-146">Messaging</span><span class="sxs-lookup"><span data-stu-id="69080-146">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="69080-147">チャット</span><span class="sxs-lookup"><span data-stu-id="69080-147">Chat</span></span>

<span data-ttu-id="69080-p104">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。(詳細については、「[Exchange と Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="69080-p104">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="69080-154">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="69080-154">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="69080-155">機能</span><span class="sxs-lookup"><span data-stu-id="69080-155">Feature</span></span>  | <span data-ttu-id="69080-156">上限</span><span class="sxs-lookup"><span data-stu-id="69080-156">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="69080-157">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="69080-157">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="69080-158">250 人</span><span class="sxs-lookup"><span data-stu-id="69080-158">250</span></span> |
|<span data-ttu-id="69080-159">チャットから開始されるビデオまたは音声通話に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="69080-159">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="69080-160">20</span><span class="sxs-lookup"><span data-stu-id="69080-160">20</span></span> |
|<span data-ttu-id="69080-161">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="69080-161">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="69080-162">10</span><span class="sxs-lookup"><span data-stu-id="69080-162">10</span></span>     |
|<span data-ttu-id="69080-163">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="69080-163">Chat size</span></span> | <span data-ttu-id="69080-164">投稿ごとに約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="69080-164">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="69080-p105"><sup>1</sup> チャットに 20 人以上いる場合、Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認などのチャット機能は無効になります。プライベート グループのチャットに 20 を超えるメンバーが含まれている場合は、「配信オプションの設定」 (!) ボタンも削除されます。</span><span class="sxs-lookup"><span data-stu-id="69080-p105"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="69080-167"><sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69080-167"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="69080-168"><sup>3</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="69080-168"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="69080-169">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="69080-169">Emailing a channel</span></span>

 <span data-ttu-id="69080-p106">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="69080-p106">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="69080-173">機能</span><span class="sxs-lookup"><span data-stu-id="69080-173">Feature</span></span>  | <span data-ttu-id="69080-174">上限</span><span class="sxs-lookup"><span data-stu-id="69080-174">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="69080-175">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="69080-175">Message size<sup>1<sup></span></span> | <span data-ttu-id="69080-176">24 KB</span><span class="sxs-lookup"><span data-stu-id="69080-176">24 KB</span></span> |
|<span data-ttu-id="69080-177">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="69080-177">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="69080-178">20</span><span class="sxs-lookup"><span data-stu-id="69080-178">20</span></span>     |
|<span data-ttu-id="69080-179">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="69080-179">Size of each file attachment</span></span> | <span data-ttu-id="69080-180">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="69080-180">Less than 10 MB</span></span> |
|<span data-ttu-id="69080-181">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="69080-181">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="69080-182">50</span><span class="sxs-lookup"><span data-stu-id="69080-182">50</span></span>   |

<span data-ttu-id="69080-183"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="69080-183"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="69080-184"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69080-184"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="69080-185">詳細については、「[Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="69080-185">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="69080-p107">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="69080-p107">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>

## <a name="channel-names"></a><span data-ttu-id="69080-188">チャネル名</span><span class="sxs-lookup"><span data-stu-id="69080-188">Channel names</span></span>

<span data-ttu-id="69080-189">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="69080-189">Channel names can't contain the following characters or words:</span></span>

|<span data-ttu-id="69080-190">種類</span><span class="sxs-lookup"><span data-stu-id="69080-190">Type</span></span>|<span data-ttu-id="69080-191">例</span><span class="sxs-lookup"><span data-stu-id="69080-191">Example</span></span>|
|---------|---------|
|<span data-ttu-id="69080-192">文字</span><span class="sxs-lookup"><span data-stu-id="69080-192">Characters</span></span>     | <span data-ttu-id="69080-p108">~ # % & \* { } + / \ : < > ? &#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="69080-p108">~ # % & \* { } + / \ : < > ? &#124; ' " , .</span></span>        |
|<span data-ttu-id="69080-195">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="69080-195">Characters in these ranges</span></span>    | <span data-ttu-id="69080-196">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="69080-196">0 to 1F</span></span><br><span data-ttu-id="69080-197">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="69080-197">80 to 9F</span></span>        |
|<span data-ttu-id="69080-198">単語</span><span class="sxs-lookup"><span data-stu-id="69080-198">Words</span></span>     | <span data-ttu-id="69080-199">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="69080-199">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="69080-200">チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="69080-200">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="69080-201">会議と通話</span><span class="sxs-lookup"><span data-stu-id="69080-201">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69080-202">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="69080-202">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="69080-203">**お客様をサポートするために、2021 年 1 月 1 日まで、Teams、Stream、Yammer でホストされるライブイベントの一時的な制限の引き上げを延長します。**</span><span class="sxs-lookup"><span data-stu-id="69080-203">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for Live Events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="69080-204">イベントごとに最大 2 万人の参加者</span><span class="sxs-lookup"><span data-stu-id="69080-204">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="69080-205">Teams テナントごとに最大 50 の同時イベント</span><span class="sxs-lookup"><span data-stu-id="69080-205">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="69080-206">ブロードキャストあたり最大 16 時間</span><span class="sxs-lookup"><span data-stu-id="69080-206">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="69080-p109">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブ イベントを計画できます。チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。**2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、[Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="69080-p109">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). **After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

|<span data-ttu-id="69080-211">機能</span><span class="sxs-lookup"><span data-stu-id="69080-211">Feature</span></span>     | <span data-ttu-id="69080-212">上限</span><span class="sxs-lookup"><span data-stu-id="69080-212">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="69080-213">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="69080-213">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="69080-214">350</span><span class="sxs-lookup"><span data-stu-id="69080-214">350</span></span> |
|<span data-ttu-id="69080-215">チャットタブから開始されるビデオ通話または音声通話の人数</span><span class="sxs-lookup"><span data-stu-id="69080-215">Number of people in a video or audio call started from the chat tab</span></span> | <span data-ttu-id="69080-216">20</span><span class="sxs-lookup"><span data-stu-id="69080-216">20</span></span> |
|<span data-ttu-id="69080-217">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="69080-217">Max PowerPoint File Size</span></span> | <span data-ttu-id="69080-218">2 GB</span><span class="sxs-lookup"><span data-stu-id="69080-218">2 GB</span></span>|
|<span data-ttu-id="69080-219">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="69080-219">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="69080-220">20 日間</span><span class="sxs-lookup"><span data-stu-id="69080-220">20 days</span></span> |

>[!Note]
> <span data-ttu-id="69080-p110">Microsoft Stream の使用から[会議の記録用の OneDrive for Business および SharePoint ](tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。</span><span class="sxs-lookup"><span data-stu-id="69080-p110">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="69080-223">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="69080-223">Meeting expiration</span></span>

|<span data-ttu-id="69080-224">会議の種類</span><span class="sxs-lookup"><span data-stu-id="69080-224">Meeting type</span></span>  |<span data-ttu-id="69080-225">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="69080-225">Meeting expires after this much time</span></span>  |<span data-ttu-id="69080-226">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="69080-226">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="69080-227">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="69080-227">Meet now</span></span>     |<span data-ttu-id="69080-228">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="69080-228">Start time + 8 hours</span></span>         |<span data-ttu-id="69080-229">該当なし</span><span class="sxs-lookup"><span data-stu-id="69080-229">N/A</span></span>         |
|<span data-ttu-id="69080-230">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="69080-230">Regular with no end time</span></span>     |<span data-ttu-id="69080-231">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="69080-231">Start time + 60 days</span></span>         | <span data-ttu-id="69080-232">60 日</span><span class="sxs-lookup"><span data-stu-id="69080-232">60 days</span></span>        |
|<span data-ttu-id="69080-233">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="69080-233">Regular with end time</span></span>     |<span data-ttu-id="69080-234">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="69080-234">End time + 60 days</span></span>         |<span data-ttu-id="69080-235">60 日</span><span class="sxs-lookup"><span data-stu-id="69080-235">60 days</span></span>         |
|<span data-ttu-id="69080-236">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="69080-236">Recurring with no end time</span></span>     |<span data-ttu-id="69080-237">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="69080-237">Start time + 60 days</span></span>         |<span data-ttu-id="69080-238">60 日</span><span class="sxs-lookup"><span data-stu-id="69080-238">60 days</span></span>         |
|<span data-ttu-id="69080-239">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="69080-239">Recurring with end time</span></span>     |<span data-ttu-id="69080-240">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="69080-240">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="69080-241">60 日</span><span class="sxs-lookup"><span data-stu-id="69080-241">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="69080-242">Microsoft Teams 会議には、24 時間の時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="69080-242">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="69080-243">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="69080-243">Teams Live Events</span></span>

|<span data-ttu-id="69080-244">機能</span><span class="sxs-lookup"><span data-stu-id="69080-244">Feature</span></span>     | <span data-ttu-id="69080-245">上限</span><span class="sxs-lookup"><span data-stu-id="69080-245">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="69080-246">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="69080-246">Audience size</span></span> | <span data-ttu-id="69080-247">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="69080-247">10,000 attendees</span></span> |
|<span data-ttu-id="69080-248">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="69080-248">Duration of event</span></span> | <span data-ttu-id="69080-249">4 時間</span><span class="sxs-lookup"><span data-stu-id="69080-249">4 hours</span></span> |
|<span data-ttu-id="69080-250">Microsoft 365 または Office 365 組織で実行されている同時ライブ イベント <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="69080-250">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="69080-251">15</span><span class="sxs-lookup"><span data-stu-id="69080-251">15</span></span> |

<span data-ttu-id="69080-p111"><sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="69080-p111"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="69080-p112">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。「[Teams のライブ イベントのスケジュール](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="69080-p112">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69080-257">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="69080-257">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="69080-258">**お客様をサポートするために、2021 年 1 月 1 日まで、Teams、Stream、Yammer でホストされるライブイベントの一時的な制限の引き上げを延長します。**</span><span class="sxs-lookup"><span data-stu-id="69080-258">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for Live Events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
> - <span data-ttu-id="69080-259">イベントごとに最大 2 万人の参加者</span><span class="sxs-lookup"><span data-stu-id="69080-259">Up to 20,000 attendees per event</span></span>
> - <span data-ttu-id="69080-260">Teams テナントごとに最大 50 の同時イベント</span><span class="sxs-lookup"><span data-stu-id="69080-260">Up to 50 simultaneous events per Teams tenant</span></span>
> - <span data-ttu-id="69080-261">ブロードキャストあたり最大 16 時間</span><span class="sxs-lookup"><span data-stu-id="69080-261">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="69080-p113">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブ イベントを計画できます。チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。**2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、[Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="69080-p113">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). **After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="69080-266">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="69080-266">Presence in Outlook</span></span>

<span data-ttu-id="69080-p114">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69080-p114">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="69080-269">ストレージ</span><span class="sxs-lookup"><span data-stu-id="69080-269">Storage</span></span>

<span data-ttu-id="69080-p115">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="69080-p115">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="69080-272">各[プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels)には、独自の SharePoint サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="69080-272">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site (previously called "site collection").</span></span>

<span data-ttu-id="69080-p116">テナントで有効な SharePoint Online をお持ちでない場合は、Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="69080-p116">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="69080-p117">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレ ベルで構成されるすべてのコンプライアンス ルールが順守されます。(詳しくは、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="69080-p117">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="69080-p118">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="69080-p118">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="69080-279">機能</span><span class="sxs-lookup"><span data-stu-id="69080-279">Feature</span></span>                 |<span data-ttu-id="69080-280">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="69080-280">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="69080-281">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="69080-281">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="69080-282">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="69080-282">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="69080-283">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="69080-283">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="69080-284">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="69080-284">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="69080-285">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="69080-285">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="69080-286">ストレージ</span><span class="sxs-lookup"><span data-stu-id="69080-286">Storage</span></span>                 |<span data-ttu-id="69080-287">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="69080-287">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="69080-288">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="69080-288">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="69080-289">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="69080-289">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="69080-290">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="69080-290">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="69080-291">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="69080-291">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="69080-292">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="69080-292">1 TB per organization</span></span>           |
|<span data-ttu-id="69080-293">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="69080-293">Storage for Teams Files</span></span> |<span data-ttu-id="69080-294">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="69080-294">Up to 25 TB per site or group</span></span> |<span data-ttu-id="69080-295">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="69080-295">Up to 25 TB per site or group</span></span> |<span data-ttu-id="69080-296">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="69080-296">Up to 25 TB per site or group</span></span> |<span data-ttu-id="69080-297">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="69080-297">Up to 25 TB per site or group</span></span> |<span data-ttu-id="69080-298">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="69080-298">Up to 25 TB per site or group</span></span> |<span data-ttu-id="69080-299">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="69080-299">Up to 25 TB per site or group</span></span> |
|<span data-ttu-id="69080-300">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="69080-300">File upload limit  (per file)</span></span>    |<span data-ttu-id="69080-301">2 GB</span><span class="sxs-lookup"><span data-stu-id="69080-301">2 GB</span></span>    |<span data-ttu-id="69080-302">2 GB</span><span class="sxs-lookup"><span data-stu-id="69080-302">2 GB</span></span>    |<span data-ttu-id="69080-303">2 GB</span><span class="sxs-lookup"><span data-stu-id="69080-303">2 GB</span></span>    |<span data-ttu-id="69080-304">2 GB</span><span class="sxs-lookup"><span data-stu-id="69080-304">2 GB</span></span>    |<span data-ttu-id="69080-305">2 GB</span><span class="sxs-lookup"><span data-stu-id="69080-305">2 GB</span></span>    |<span data-ttu-id="69080-306">2 GB</span><span class="sxs-lookup"><span data-stu-id="69080-306">2 GB</span></span>    |

<span data-ttu-id="69080-307">チャネルは、チーム用に作成された SharePoint Online サイト内のフォルダーによってバックアップされるため、チャネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="69080-307">Channels are backed by folders within the SharePoint Online site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="69080-308">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69080-308">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="69080-309">クラス チーム</span><span class="sxs-lookup"><span data-stu-id="69080-309">Class teams</span></span>

<span data-ttu-id="69080-p119">Microsoft Teams for Education には、教室での授業など、独自の教育シナリオ用に設計されたテンプレートが用意されています。クラス チームなど、チームの種類の詳細については、「[Microsoft Teams で共同作業を行うチームの種類を選択する](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69080-p119">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="69080-312">クラス チームは、追加のアプリが含まれるテンプレートの種類で、チーム メンバーの数に応じた制限があります。</span><span class="sxs-lookup"><span data-stu-id="69080-312">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="69080-313">クラスチームを使用するには、[Office 365 Education ライセンス](https://www.microsoft.com/education/products/office)が必要です。</span><span class="sxs-lookup"><span data-stu-id="69080-313">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="69080-314">クラスチームの制限を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="69080-314">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="69080-315">機能</span><span class="sxs-lookup"><span data-stu-id="69080-315">Feature</span></span>  |<span data-ttu-id="69080-316">上限</span><span class="sxs-lookup"><span data-stu-id="69080-316">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="69080-317">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="69080-317">Number of members in a team</span></span>    | <span data-ttu-id="69080-318">この記事の「[チームとチャネル](#teams-and-channels)」のセクションを参照してください</span><span class="sxs-lookup"><span data-stu-id="69080-318">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="69080-319">クラスチームで課題を使用するメンバーの数</span><span class="sxs-lookup"><span data-stu-id="69080-319">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="69080-320">200</span><span class="sxs-lookup"><span data-stu-id="69080-320">200</span></span>        |
|<span data-ttu-id="69080-321">クラスチームで OneNote Class Notebook を使用するためのメンバー数</span><span class="sxs-lookup"><span data-stu-id="69080-321">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="69080-322">200</span><span class="sxs-lookup"><span data-stu-id="69080-322">200</span></span>         |

<span data-ttu-id="69080-p120">クラス チームは、200 を超えるメンバーをサポートできます。ただし、チーム内で課題アプリまたは Class Notebook アプリのいずれかを使用する場合は、メンバー数を上記の上限未満に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="69080-p120">A class team can support more than 200 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>

## <a name="tags"></a><span data-ttu-id="69080-325">タグ</span><span class="sxs-lookup"><span data-stu-id="69080-325">Tags</span></span>

|<span data-ttu-id="69080-326">機能</span><span class="sxs-lookup"><span data-stu-id="69080-326">Feature</span></span>  |<span data-ttu-id="69080-327">上限</span><span class="sxs-lookup"><span data-stu-id="69080-327">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="69080-328">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="69080-328">Number of tags per team</span></span>    | <span data-ttu-id="69080-329">100</span><span class="sxs-lookup"><span data-stu-id="69080-329">100</span></span>        |
|<span data-ttu-id="69080-330">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="69080-330">Number of suggested default tags per team</span></span>    | <span data-ttu-id="69080-331">25</span><span class="sxs-lookup"><span data-stu-id="69080-331">25</span></span>        |
|<span data-ttu-id="69080-332">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="69080-332">Number of team members assign to a tag</span></span>    |<span data-ttu-id="69080-333">100</span><span class="sxs-lookup"><span data-stu-id="69080-333">100</span></span>         |
|<span data-ttu-id="69080-334">ユーザーに割り当てられたるタグ数</span><span class="sxs-lookup"><span data-stu-id="69080-334">Number of tags assigned to a user</span></span>    |<span data-ttu-id="69080-335">25</span><span class="sxs-lookup"><span data-stu-id="69080-335">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="69080-336">連絡先</span><span class="sxs-lookup"><span data-stu-id="69080-336">Contacts</span></span>

<span data-ttu-id="69080-337">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="69080-337">Teams uses these contacts:</span></span>

- <span data-ttu-id="69080-338">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="69080-338">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="69080-339">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="69080-339">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="69080-340">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="69080-340">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="69080-341">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="69080-341">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="69080-342">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="69080-342">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="69080-343">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="69080-343">Operating systems</span></span>

<span data-ttu-id="69080-344">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="69080-344">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
