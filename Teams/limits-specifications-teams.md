---
title: Microsoft Teams の制限事項と仕様
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
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
ms.openlocfilehash: d14dcbcc7176a482458e23b10e4f017b28ad24ea
ms.sourcegitcommit: 109b3869afb5ff1ca4eaf771399d7cda70a43bea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51586496"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="8413c-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="8413c-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="8413c-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="8413c-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="8413c-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="8413c-105">Teams and channels</span></span>

|<span data-ttu-id="8413c-106">機能</span><span class="sxs-lookup"><span data-stu-id="8413c-106">Feature</span></span>    | <span data-ttu-id="8413c-107">上限</span><span class="sxs-lookup"><span data-stu-id="8413c-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="8413c-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="8413c-108">Number of teams a user can create</span></span> | <span data-ttu-id="8413c-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="8413c-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="8413c-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="8413c-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="8413c-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="8413c-111">1,000&sup2;</span></span>|
|<span data-ttu-id="8413c-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8413c-112">Number of members in a team</span></span> | <span data-ttu-id="8413c-113">25,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-113">25,000<sup>6</sup></span></span>     |
|<span data-ttu-id="8413c-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="8413c-114">Number of owners per team</span></span> | <span data-ttu-id="8413c-115">100</span><span class="sxs-lookup"><span data-stu-id="8413c-115">100</span></span>   |
|<span data-ttu-id="8413c-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="8413c-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="8413c-117">5&sup2;</span><span class="sxs-lookup"><span data-stu-id="8413c-117">5&sup2;</span></span>     |
|<span data-ttu-id="8413c-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8413c-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="8413c-119">10,000</span><span class="sxs-lookup"><span data-stu-id="8413c-119">10,000</span></span>       |
|<span data-ttu-id="8413c-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="8413c-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="8413c-121">500,000</span><span class="sxs-lookup"><span data-stu-id="8413c-121">500,000</span></span>   |
|<span data-ttu-id="8413c-122">Microsoft 365 または Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="8413c-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="8413c-123">500,000&sup3;</span><span class="sxs-lookup"><span data-stu-id="8413c-123">500,000&sup3;</span></span>     |
|<span data-ttu-id="8413c-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="8413c-124">Number of channels per team</span></span>    | <span data-ttu-id="8413c-125">200 (削除されたチャネルを含む)<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-125">200 (includes deleted channels)<sup>4</sup></span></span>        |
|<span data-ttu-id="8413c-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="8413c-126">Number of Private channels per team</span></span>    |<span data-ttu-id="8413c-127">30 (削除されたチャネルを含む)<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-127">30 (includes deleted channels)<sup>4</sup></span></span>        |
|<span data-ttu-id="8413c-128">プライベート チャネルのメンバー数</span><span class="sxs-lookup"><span data-stu-id="8413c-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="8413c-129">250</span><span class="sxs-lookup"><span data-stu-id="8413c-129">250</span></span>|
|<span data-ttu-id="8413c-130">チームにインポートできる配布リスト、セキュリティ グループ、または Office 365 グループの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="8413c-130">Maximum size of distribution list, security group or Office 365 group that can be imported in to a team</span></span>    |<span data-ttu-id="8413c-131">3,500</span><span class="sxs-lookup"><span data-stu-id="8413c-131">3,500</span></span>|
|<span data-ttu-id="8413c-132">チームに変換できる Office 365 グループのメンバーの最大数</span><span class="sxs-lookup"><span data-stu-id="8413c-132">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="8413c-133">10,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-133">10,000<sup>6</sup></span></span>     |
|<span data-ttu-id="8413c-134">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="8413c-134">Channel conversation post size</span></span> | <span data-ttu-id="8413c-135">投稿ごとに約 28 KB<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-135">Approximately 28 KB per post<sup>5</sup></span></span> |

<span data-ttu-id="8413c-p101"><sup>1</sup> Azure Active Directory のすべてのディレクトリ オブジェクトはこの制限にカウントされます。グローバル管理者は、[アプリケーションのアクセス許可](/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="8413c-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).</span></span>

<span data-ttu-id="8413c-138"><sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8413c-138"><sup>2</sup> This limit includes archived teams.</span></span> 

<span data-ttu-id="8413c-139"><sup>3</sup> チームの数をさらに増やすには、Microsoft サポートに連絡して、テナント内の Azure Active Directory オブジェクト数を増やすように依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8413c-139"><sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant.</span></span> <span data-ttu-id="8413c-140">増加は、実際の生産シナリオに対してのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="8413c-140">Increase is only made for real-life production scenarios.</span></span>

<span data-ttu-id="8413c-141"><sup>4</sup> 削除したチャネルは、30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="8413c-141"><sup>4</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="8413c-142">この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルまたは30のプライベートチャンネルとしてカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="8413c-142">During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit.</span></span> <span data-ttu-id="8413c-143">30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限内のチャンネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="8413c-143">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="8413c-144"><sup>5</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="8413c-144"><sup>5</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="8413c-145"><sup>6</sup> GCC の チーム は 25,000 人のメンバーを収容できますが、GCCH / DoD のチームは 2,500 人のメンバーしか収容できません。</span><span class="sxs-lookup"><span data-stu-id="8413c-145"><sup>6</sup> Teams in GCC can accommodate 25,000 members but teams in GCCH/DoD can only accommodate 2,500 members.</span></span> <span data-ttu-id="8413c-146">さらに、メンバー数が 10,000 人以上のチームでは、チーム/チャネルのメンションはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8413c-146">Further note that teams/channel mentions are blocked in teams with over 10,000 members.</span></span>

## <a name="messaging"></a><span data-ttu-id="8413c-147">Messaging</span><span class="sxs-lookup"><span data-stu-id="8413c-147">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="8413c-148">チャット</span><span class="sxs-lookup"><span data-stu-id="8413c-148">Chat</span></span>

<span data-ttu-id="8413c-p105">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。(詳細については、「[Exchange と Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="8413c-p105">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="8413c-155">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8413c-155">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="8413c-156">機能</span><span class="sxs-lookup"><span data-stu-id="8413c-156">Feature</span></span>  | <span data-ttu-id="8413c-157">上限</span><span class="sxs-lookup"><span data-stu-id="8413c-157">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8413c-158">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-158">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="8413c-159">250<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-159">250<sup>2</sup></span></span> |
|<span data-ttu-id="8413c-160">チャットから開始されるビデオまたは音声通話に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="8413c-160">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="8413c-161">20</span><span class="sxs-lookup"><span data-stu-id="8413c-161">20</span></span> |
|<span data-ttu-id="8413c-162">添付ファイルの数 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-162">Number of file attachments<sup>3</sup></span></span>  |<span data-ttu-id="8413c-163">10</span><span class="sxs-lookup"><span data-stu-id="8413c-163">10</span></span>     |
|<span data-ttu-id="8413c-164">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="8413c-164">Chat size</span></span> | <span data-ttu-id="8413c-165">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-165">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="8413c-p106"><sup>1</sup> チャットに 20 人以上いる場合、Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認などのチャット機能は無効になります。プライベート グループのチャットに 20 を超えるメンバーが含まれている場合は、「配信オプションの設定」 (!) ボタンも削除されます。</span><span class="sxs-lookup"><span data-stu-id="8413c-p106"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="8413c-168"><sup>2</sup> グループチャットには一度に 200 人のメンバーのみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8413c-168"><sup>2</sup> Only 200 members at a time can be added to a group chat.</span></span> <span data-ttu-id="8413c-169">[詳細については、こちらの記事を参照してください](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat)。</span><span class="sxs-lookup"><span data-stu-id="8413c-169">[See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).</span></span>

<span data-ttu-id="8413c-170"><sup>3</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8413c-170"><sup>3</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="8413c-171"><sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="8413c-171"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="8413c-172">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="8413c-172">Emailing a channel</span></span>

 <span data-ttu-id="8413c-p108">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8413c-p108">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="8413c-176">機能</span><span class="sxs-lookup"><span data-stu-id="8413c-176">Feature</span></span>  | <span data-ttu-id="8413c-177">上限</span><span class="sxs-lookup"><span data-stu-id="8413c-177">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8413c-178">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="8413c-178">Message size<sup>1<sup></span></span> | <span data-ttu-id="8413c-179">24 KB</span><span class="sxs-lookup"><span data-stu-id="8413c-179">24 KB</span></span> |
|<span data-ttu-id="8413c-180">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-180">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="8413c-181">20</span><span class="sxs-lookup"><span data-stu-id="8413c-181">20</span></span>     |
|<span data-ttu-id="8413c-182">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="8413c-182">Size of each file attachment</span></span> | <span data-ttu-id="8413c-183">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="8413c-183">Less than 10 MB</span></span> |
|<span data-ttu-id="8413c-184">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-184">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="8413c-185">50</span><span class="sxs-lookup"><span data-stu-id="8413c-185">50</span></span>   |

<span data-ttu-id="8413c-186"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8413c-186"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="8413c-187"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8413c-187"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="8413c-188">詳細については、「[Exchange Online の制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8413c-188">For more information, see [Exchange Online limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="8413c-p109">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="8413c-p109">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>

## <a name="channel-names"></a><span data-ttu-id="8413c-191">チャネル名</span><span class="sxs-lookup"><span data-stu-id="8413c-191">Channel names</span></span>

<span data-ttu-id="8413c-192">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="8413c-192">Channel names can't contain the following characters or words:</span></span>

|<span data-ttu-id="8413c-193">種類</span><span class="sxs-lookup"><span data-stu-id="8413c-193">Type</span></span>|<span data-ttu-id="8413c-194">例</span><span class="sxs-lookup"><span data-stu-id="8413c-194">Example</span></span>|
|---------|---------|
|<span data-ttu-id="8413c-195">文字</span><span class="sxs-lookup"><span data-stu-id="8413c-195">Characters</span></span>     | <span data-ttu-id="8413c-p110">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span><span class="sxs-lookup"><span data-stu-id="8413c-p110">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span></span>        |
|<span data-ttu-id="8413c-198">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="8413c-198">Characters in these ranges</span></span>    | <span data-ttu-id="8413c-199">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="8413c-199">0 to 1F</span></span><br><span data-ttu-id="8413c-200">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="8413c-200">80 to 9F</span></span>        |
|<span data-ttu-id="8413c-201">単語</span><span class="sxs-lookup"><span data-stu-id="8413c-201">Words</span></span>     | <span data-ttu-id="8413c-202">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="8413c-202">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="8413c-203">チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="8413c-203">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="8413c-204">会議と通話</span><span class="sxs-lookup"><span data-stu-id="8413c-204">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8413c-205">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="8413c-205">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="8413c-206">**お客様のニーズを引き続きサポートするため、2021年6月30日まで、** などのライブ イベントへの一時的な制約を増やします。</span><span class="sxs-lookup"><span data-stu-id="8413c-206">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="8413c-207">イベントでは、最大2万の出席者をサポートします</span><span class="sxs-lookup"><span data-stu-id="8413c-207">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="8413c-208">テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="8413c-208">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="8413c-209">ブロードキャストあたり16時間のイベント期間</span><span class="sxs-lookup"><span data-stu-id="8413c-209">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="8413c-210">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブイベントを計画できます。</span><span class="sxs-lookup"><span data-stu-id="8413c-210">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program.</span></span> <span data-ttu-id="8413c-211">チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。</span><span class="sxs-lookup"><span data-stu-id="8413c-211">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="8413c-212">[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="8413c-212">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span>

|<span data-ttu-id="8413c-213">機能</span><span class="sxs-lookup"><span data-stu-id="8413c-213">Feature</span></span>     | <span data-ttu-id="8413c-214">上限</span><span class="sxs-lookup"><span data-stu-id="8413c-214">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="8413c-215">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="8413c-215">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="8413c-216">300。**表示専用** では、開催者が E3/E5/A3/A5 SKU のライセンスを持っている会議に、最大 1 万人の聴取のみの参加者が参加できます。</span><span class="sxs-lookup"><span data-stu-id="8413c-216">300. **View-only** allows for up to 10,000 listen-only participants to join a meeting in which the organizer has a license for E3/E5/A3/A5 SKU.</span></span><br><span data-ttu-id="8413c-217">**注:** 政府機関用の Teams (GCC、GCC High、DoD) の場合、制限は 250 のままです。</span><span class="sxs-lookup"><span data-stu-id="8413c-217">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 250.</span></span> <span data-ttu-id="8413c-218">政府機関のクラウド制限が 250 から 300 に増加し、会議のオーバーフローがサポートされたら、この記事を更新します。</span><span class="sxs-lookup"><span data-stu-id="8413c-218">We'll update this article when the government cloud limit increases from 250 to 300 and supports meeting overflow.</span></span> <span data-ttu-id="8413c-219">[表示専用エクスペリエンス](view-only-meeting-experience.md)に関する詳細。</span><span class="sxs-lookup"><span data-stu-id="8413c-219">Learn more about the [View-only experience](view-only-meeting-experience.md).</span></span>|
|<span data-ttu-id="8413c-220">チャットから開始されるビデオまたは音声通話に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="8413c-220">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="8413c-221">20</span><span class="sxs-lookup"><span data-stu-id="8413c-221">20</span></span> |
|<span data-ttu-id="8413c-222">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="8413c-222">Max PowerPoint File Size</span></span> | <span data-ttu-id="8413c-223">2GB</span><span class="sxs-lookup"><span data-stu-id="8413c-223">2GB</span></span>|
|<span data-ttu-id="8413c-224">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="8413c-224">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="8413c-225">20 日間</span><span class="sxs-lookup"><span data-stu-id="8413c-225">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="8413c-226">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="8413c-226">Meeting expiration</span></span>

> [!NOTE]
> <span data-ttu-id="8413c-227">会議の URL は機能を停止しません。</span><span class="sxs-lookup"><span data-stu-id="8413c-227">A meeting URL will never stop working.</span></span> <span data-ttu-id="8413c-228">有効期限は、任意の PSTN のダイヤルイン番号および/または基となる会議ポリシーおよび設定にのみ関係します。</span><span class="sxs-lookup"><span data-stu-id="8413c-228">The expiry only relates to any PSTN dial-in numbers and/or underlying meeting policies and settings.</span></span>

|<span data-ttu-id="8413c-229">会議の種類</span><span class="sxs-lookup"><span data-stu-id="8413c-229">Meeting type</span></span>  |<span data-ttu-id="8413c-230">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="8413c-230">Meeting expires after this much time</span></span>  |<span data-ttu-id="8413c-231">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="8413c-231">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8413c-232">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="8413c-232">Meet now</span></span>     |<span data-ttu-id="8413c-233">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="8413c-233">Start time + 8 hours</span></span>         |<span data-ttu-id="8413c-234">該当なし</span><span class="sxs-lookup"><span data-stu-id="8413c-234">N/A</span></span>         |
|<span data-ttu-id="8413c-235">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="8413c-235">Regular with no end time</span></span>     |<span data-ttu-id="8413c-236">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8413c-236">Start time + 60 days</span></span>         | <span data-ttu-id="8413c-237">60 日</span><span class="sxs-lookup"><span data-stu-id="8413c-237">60 days</span></span>        |
|<span data-ttu-id="8413c-238">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="8413c-238">Regular with end time</span></span>     |<span data-ttu-id="8413c-239">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8413c-239">End time + 60 days</span></span>         |<span data-ttu-id="8413c-240">60 日</span><span class="sxs-lookup"><span data-stu-id="8413c-240">60 days</span></span>         |
|<span data-ttu-id="8413c-241">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="8413c-241">Recurring with no end time</span></span>     |<span data-ttu-id="8413c-242">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8413c-242">Start time + 60 days</span></span>         |<span data-ttu-id="8413c-243">60 日</span><span class="sxs-lookup"><span data-stu-id="8413c-243">60 days</span></span>         |
|<span data-ttu-id="8413c-244">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="8413c-244">Recurring with end time</span></span>     |<span data-ttu-id="8413c-245">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8413c-245">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="8413c-246">60 日</span><span class="sxs-lookup"><span data-stu-id="8413c-246">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="8413c-247">Microsoft Teams 会議には、24 時間の時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="8413c-247">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="8413c-248">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="8413c-248">Teams Live Events</span></span>

|<span data-ttu-id="8413c-249">機能</span><span class="sxs-lookup"><span data-stu-id="8413c-249">Feature</span></span>     | <span data-ttu-id="8413c-250">上限</span><span class="sxs-lookup"><span data-stu-id="8413c-250">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="8413c-251">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="8413c-251">Audience size</span></span> | <span data-ttu-id="8413c-252">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="8413c-252">10,000 attendees</span></span> |
|<span data-ttu-id="8413c-253">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="8413c-253">Duration of event</span></span> | <span data-ttu-id="8413c-254">4 時間</span><span class="sxs-lookup"><span data-stu-id="8413c-254">4 hours</span></span> |
|<span data-ttu-id="8413c-255">Microsoft 365 または Office 365 組織で実行されている同時ライブ イベント <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8413c-255">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="8413c-256">15</span><span class="sxs-lookup"><span data-stu-id="8413c-256">15</span></span> |

<span data-ttu-id="8413c-p114"><sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8413c-p114"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="8413c-p115">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。「[Teams のライブ イベントのスケジュール](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="8413c-p115">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8413c-262">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="8413c-262">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="8413c-263">**お客様のニーズを引き続きサポートするため、2021年6月30日まで、** などのライブ イベントへの一時的な制約を増やします。</span><span class="sxs-lookup"><span data-stu-id="8413c-263">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="8413c-264">イベントでは、最大2万の出席者をサポートします</span><span class="sxs-lookup"><span data-stu-id="8413c-264">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="8413c-265">テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="8413c-265">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="8413c-266">ブロードキャストあたり16時間のイベント期間</span><span class="sxs-lookup"><span data-stu-id="8413c-266">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="8413c-267">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブイベントを計画できます。</span><span class="sxs-lookup"><span data-stu-id="8413c-267">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program.</span></span> <span data-ttu-id="8413c-268">チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。</span><span class="sxs-lookup"><span data-stu-id="8413c-268">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="8413c-269">[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="8413c-269">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> 

## <a name="presence-in-outlook"></a><span data-ttu-id="8413c-270">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="8413c-270">Presence in Outlook</span></span>

<span data-ttu-id="8413c-p117">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8413c-p117">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="8413c-273">ストレージ</span><span class="sxs-lookup"><span data-stu-id="8413c-273">Storage</span></span>

<span data-ttu-id="8413c-p118">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="8413c-p118">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="8413c-276">各[プライベート チャネル](./private-channels.md)には、独自の SharePoint サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="8413c-276">Each [private channel](./private-channels.md) has its own SharePoint site (previously called "site collection").</span></span>

<span data-ttu-id="8413c-p119">テナントで有効な SharePoint Online をお持ちでない場合は、Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="8413c-p119">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="8413c-p120">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレ ベルで構成されるすべてのコンプライアンス ルールが順守されます。(詳しくは、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="8413c-p120">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="8413c-p121">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="8413c-p121">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="8413c-283">機能</span><span class="sxs-lookup"><span data-stu-id="8413c-283">Feature</span></span>                 |<span data-ttu-id="8413c-284">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="8413c-284">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="8413c-285">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="8413c-285">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="8413c-286">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="8413c-286">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="8413c-287">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="8413c-287">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="8413c-288">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="8413c-288">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="8413c-289">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="8413c-289">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="8413c-290">ストレージ</span><span class="sxs-lookup"><span data-stu-id="8413c-290">Storage</span></span>                 |<span data-ttu-id="8413c-291">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-291">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8413c-292">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-292">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8413c-293">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-293">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="8413c-294">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-294">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="8413c-295">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-295">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8413c-296">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="8413c-296">1 TB per organization</span></span>           |
|<span data-ttu-id="8413c-297">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="8413c-297">Storage for Teams Files</span></span> |<span data-ttu-id="8413c-298">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8413c-298">Up to 25 TB per site or group</span></span> |<span data-ttu-id="8413c-299">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8413c-299">Up to 25 TB per site or group</span></span> |<span data-ttu-id="8413c-300">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8413c-300">Up to 25 TB per site or group</span></span> |<span data-ttu-id="8413c-301">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8413c-301">Up to 25 TB per site or group</span></span> |<span data-ttu-id="8413c-302">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8413c-302">Up to 25 TB per site or group</span></span> |<span data-ttu-id="8413c-303">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8413c-303">Up to 25 TB per site or group</span></span> |
|<span data-ttu-id="8413c-304">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="8413c-304">File upload limit  (per file)</span></span>    |<span data-ttu-id="8413c-305">100 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-305">100 GB</span></span>    |<span data-ttu-id="8413c-306">100 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-306">100 GB</span></span>    |<span data-ttu-id="8413c-307">100 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-307">100 GB</span></span>    |<span data-ttu-id="8413c-308">100 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-308">100 GB</span></span>    |<span data-ttu-id="8413c-309">100 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-309">100 GB</span></span>    |<span data-ttu-id="8413c-310">100 GB</span><span class="sxs-lookup"><span data-stu-id="8413c-310">100 GB</span></span>    |

<span data-ttu-id="8413c-311">チャネルは、チーム用に作成された SharePoint Online サイト内のフォルダーによってバックアップされるため、チャネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="8413c-311">Channels are backed by folders within the SharePoint Online site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="8413c-312">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8413c-312">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="8413c-313">クラス チーム</span><span class="sxs-lookup"><span data-stu-id="8413c-313">Class teams</span></span>

<span data-ttu-id="8413c-p122">Microsoft Teams for Education には、教室での授業など、独自の教育シナリオ用に設計されたテンプレートが用意されています。クラス チームなど、チームの種類の詳細については、「[Microsoft Teams で共同作業を行うチームの種類を選択する](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8413c-p122">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="8413c-316">クラス チームは、追加のアプリが含まれるテンプレートの種類で、チーム メンバーの数に応じた制限があります。</span><span class="sxs-lookup"><span data-stu-id="8413c-316">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="8413c-317">クラスチームを使用するには、[Office 365 Education ライセンス](https://www.microsoft.com/education/products/office)が必要です。</span><span class="sxs-lookup"><span data-stu-id="8413c-317">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="8413c-318">クラスチームの制限を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="8413c-318">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="8413c-319">機能</span><span class="sxs-lookup"><span data-stu-id="8413c-319">Feature</span></span>  |<span data-ttu-id="8413c-320">上限</span><span class="sxs-lookup"><span data-stu-id="8413c-320">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8413c-321">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8413c-321">Number of members in a team</span></span>    | <span data-ttu-id="8413c-322">この記事の「[チームとチャネル](#teams-and-channels)」のセクションを参照してください</span><span class="sxs-lookup"><span data-stu-id="8413c-322">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="8413c-323">クラスチームで課題を使用するメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8413c-323">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="8413c-324">200</span><span class="sxs-lookup"><span data-stu-id="8413c-324">200</span></span>        |
|<span data-ttu-id="8413c-325">クラスチームで OneNote Class Notebook を使用するためのメンバー数</span><span class="sxs-lookup"><span data-stu-id="8413c-325">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="8413c-326">200</span><span class="sxs-lookup"><span data-stu-id="8413c-326">200</span></span>         |

<span data-ttu-id="8413c-p123">クラス チームは、200 を超えるメンバーをサポートできます。ただし、チーム内で課題アプリまたは Class Notebook アプリのいずれかを使用する場合は、メンバー数を上記の上限未満に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="8413c-p123">A class team can support more than 200 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>

## <a name="tags"></a><span data-ttu-id="8413c-329">タグ</span><span class="sxs-lookup"><span data-stu-id="8413c-329">Tags</span></span>

|<span data-ttu-id="8413c-330">機能</span><span class="sxs-lookup"><span data-stu-id="8413c-330">Feature</span></span>  |<span data-ttu-id="8413c-331">上限</span><span class="sxs-lookup"><span data-stu-id="8413c-331">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8413c-332">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="8413c-332">Number of tags per team</span></span>    | <span data-ttu-id="8413c-333">100</span><span class="sxs-lookup"><span data-stu-id="8413c-333">100</span></span>        |
|<span data-ttu-id="8413c-334">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="8413c-334">Number of suggested default tags per team</span></span>    | <span data-ttu-id="8413c-335">25</span><span class="sxs-lookup"><span data-stu-id="8413c-335">25</span></span>        |
|<span data-ttu-id="8413c-336">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8413c-336">Number of team members assign to a tag</span></span>    |<span data-ttu-id="8413c-337">100</span><span class="sxs-lookup"><span data-stu-id="8413c-337">100</span></span>         |
|<span data-ttu-id="8413c-338">チームごとにユーザーに割り当てられたタグ数</span><span class="sxs-lookup"><span data-stu-id="8413c-338">Number of tags assigned to a user per team</span></span>    |<span data-ttu-id="8413c-339">25</span><span class="sxs-lookup"><span data-stu-id="8413c-339">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="8413c-340">連絡先</span><span class="sxs-lookup"><span data-stu-id="8413c-340">Contacts</span></span>

<span data-ttu-id="8413c-341">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="8413c-341">Teams uses these contacts:</span></span>

- <span data-ttu-id="8413c-342">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="8413c-342">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="8413c-343">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="8413c-343">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="8413c-344">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8413c-344">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="8413c-345">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="8413c-345">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="8413c-346">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="8413c-346">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="8413c-347">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="8413c-347">Operating systems</span></span>

<span data-ttu-id="8413c-348">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8413c-348">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>