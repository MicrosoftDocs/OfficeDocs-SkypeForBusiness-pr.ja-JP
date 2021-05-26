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
ms.openlocfilehash: b714da86c51072eb7efae846dbeb29b205674751
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628886"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="ae49d-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="ae49d-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="ae49d-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae49d-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="ae49d-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="ae49d-105">Teams and channels</span></span>

|<span data-ttu-id="ae49d-106">機能</span><span class="sxs-lookup"><span data-stu-id="ae49d-106">Feature</span></span>    | <span data-ttu-id="ae49d-107">上限</span><span class="sxs-lookup"><span data-stu-id="ae49d-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="ae49d-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-108">Number of teams a user can create</span></span> | <span data-ttu-id="ae49d-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="ae49d-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="ae49d-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="ae49d-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="ae49d-111">1,000&sup2;</span></span>|
|<span data-ttu-id="ae49d-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-112">Number of members in a team</span></span> | <span data-ttu-id="ae49d-113">25,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-113">25,000<sup>6</sup></span></span>     |
|<span data-ttu-id="ae49d-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="ae49d-114">Number of owners per team</span></span> | <span data-ttu-id="ae49d-115">100</span><span class="sxs-lookup"><span data-stu-id="ae49d-115">100</span></span>   |
|<span data-ttu-id="ae49d-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="ae49d-117">5&sup2;</span><span class="sxs-lookup"><span data-stu-id="ae49d-117">5&sup2;</span></span>     |
|<span data-ttu-id="ae49d-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="ae49d-119">10,000</span><span class="sxs-lookup"><span data-stu-id="ae49d-119">10,000</span></span>       |
|<span data-ttu-id="ae49d-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="ae49d-121">500,000</span><span class="sxs-lookup"><span data-stu-id="ae49d-121">500,000</span></span>   |
|<span data-ttu-id="ae49d-122">Microsoft 365 または Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="ae49d-123">500,000&sup3;</span><span class="sxs-lookup"><span data-stu-id="ae49d-123">500,000&sup3;</span></span>     |
|<span data-ttu-id="ae49d-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="ae49d-124">Number of channels per team</span></span>    | <span data-ttu-id="ae49d-125">200 (削除されたチャネルを含む)<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-125">200 (includes deleted channels)<sup>4</sup></span></span>        |
|<span data-ttu-id="ae49d-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="ae49d-126">Number of Private channels per team</span></span>    |<span data-ttu-id="ae49d-127">30 (削除されたチャネルを含む)<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-127">30 (includes deleted channels)<sup>4</sup></span></span>        |
|<span data-ttu-id="ae49d-128">プライベート チャネルのメンバー数</span><span class="sxs-lookup"><span data-stu-id="ae49d-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="ae49d-129">250</span><span class="sxs-lookup"><span data-stu-id="ae49d-129">250</span></span>|
|<span data-ttu-id="ae49d-130">チームにインポートできる配布リスト、セキュリティ グループ、または Office 365 グループの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="ae49d-130">Maximum size of distribution list, security group or Office 365 group that can be imported in to a team</span></span>    |<span data-ttu-id="ae49d-131">3,500</span><span class="sxs-lookup"><span data-stu-id="ae49d-131">3,500</span></span>|
|<span data-ttu-id="ae49d-132">チームに変換できる Office 365 グループのメンバーの最大数</span><span class="sxs-lookup"><span data-stu-id="ae49d-132">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="ae49d-133">10,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-133">10,000<sup>6</sup></span></span>     |
|<span data-ttu-id="ae49d-134">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="ae49d-134">Channel conversation post size</span></span> | <span data-ttu-id="ae49d-135">投稿ごとに約 28 KB<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-135">Approximately 28 KB per post<sup>5</sup></span></span> |

<span data-ttu-id="ae49d-p101"><sup>1</sup> Azure Active Directory のすべてのディレクトリ オブジェクトはこの制限にカウントされます。グローバル管理者は、[アプリケーションのアクセス許可](/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).</span></span>

<span data-ttu-id="ae49d-138"><sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-138"><sup>2</sup> This limit includes archived teams.</span></span> 

<span data-ttu-id="ae49d-p102"><sup>3</sup> チームの数をさらに増やすには、Microsoft サポートに連絡して、テナント内の Azure Active Directory オブジェクト数を増やすように依頼する必要があります。増加は、実際の生産シナリオに対してのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p102"><sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.</span></span>

<span data-ttu-id="ae49d-p103"><sup>4</sup> 削除したチャネルは、30 日以内であれば復元できます。この 30 日間、削除されたチャネルはチームごとの制限である 200 チャネルまたは 30 のプライベート チャネルとしてカウントされ続けます。30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャネルはチームごとの制限内のチャネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p103"><sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="ae49d-144"><sup>5</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="ae49d-144"><sup>5</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="ae49d-145"><sup>6</sup> GCC の チーム は 25,000 人のメンバーを収容できますが、GCCH / DoD のチームは 2,500 人のメンバーしか収容できません。</span><span class="sxs-lookup"><span data-stu-id="ae49d-145"><sup>6</sup> Teams in GCC can accommodate 25,000 members but teams in GCCH/DoD can only accommodate 2,500 members.</span></span> <span data-ttu-id="ae49d-146">さらに、メンバー数が 10,000 人以上のチームでは、チーム/チャネルのメンションはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-146">Further note that teams/channel mentions are blocked in teams with over 10,000 members.</span></span>

## <a name="messaging"></a><span data-ttu-id="ae49d-147">Messaging</span><span class="sxs-lookup"><span data-stu-id="ae49d-147">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="ae49d-148">チャット</span><span class="sxs-lookup"><span data-stu-id="ae49d-148">Chat</span></span>

<span data-ttu-id="ae49d-p105">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。(詳細については、「[Exchange と Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="ae49d-p105">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="ae49d-155">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-155">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="ae49d-156">機能</span><span class="sxs-lookup"><span data-stu-id="ae49d-156">Feature</span></span>  | <span data-ttu-id="ae49d-157">上限</span><span class="sxs-lookup"><span data-stu-id="ae49d-157">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="ae49d-158">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-158">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="ae49d-159">250<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-159">250<sup>2</sup></span></span> |
|<span data-ttu-id="ae49d-160">チャットから開始されるビデオまたは音声通話に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="ae49d-160">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="ae49d-161">20</span><span class="sxs-lookup"><span data-stu-id="ae49d-161">20</span></span> |
|<span data-ttu-id="ae49d-162">添付ファイルの数 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-162">Number of file attachments<sup>3</sup></span></span>  |<span data-ttu-id="ae49d-163">10</span><span class="sxs-lookup"><span data-stu-id="ae49d-163">10</span></span>     |
|<span data-ttu-id="ae49d-164">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="ae49d-164">Chat size</span></span> | <span data-ttu-id="ae49d-165">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-165">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="ae49d-p106"><sup>1</sup> チャットに 20 人以上いる場合、Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認などのチャット機能は無効になります。プライベート グループのチャットに 20 を超えるメンバーが含まれている場合は、「配信オプションの設定」 (!) ボタンも削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p106"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="ae49d-p107"><sup>2</sup> グループチャットには一度に 200 人のメンバーまで追加できます。 [詳細については、この記事を参照します](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat)。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p107"><sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).</span></span>

<span data-ttu-id="ae49d-170"><sup>3</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-170"><sup>3</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="ae49d-171"><sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="ae49d-171"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="ae49d-172">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="ae49d-172">Emailing a channel</span></span>

 <span data-ttu-id="ae49d-p108">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p108">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="ae49d-176">機能</span><span class="sxs-lookup"><span data-stu-id="ae49d-176">Feature</span></span>  | <span data-ttu-id="ae49d-177">上限</span><span class="sxs-lookup"><span data-stu-id="ae49d-177">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="ae49d-178">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-178">Message size<sup>1<sup></span></span> | <span data-ttu-id="ae49d-179">24 KB</span><span class="sxs-lookup"><span data-stu-id="ae49d-179">24 KB</span></span> |
|<span data-ttu-id="ae49d-180">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-180">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="ae49d-181">20</span><span class="sxs-lookup"><span data-stu-id="ae49d-181">20</span></span>     |
|<span data-ttu-id="ae49d-182">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="ae49d-182">Size of each file attachment</span></span> | <span data-ttu-id="ae49d-183">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="ae49d-183">Less than 10 MB</span></span> |
|<span data-ttu-id="ae49d-184">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-184">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="ae49d-185">50</span><span class="sxs-lookup"><span data-stu-id="ae49d-185">50</span></span>   |

<span data-ttu-id="ae49d-186"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-186"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="ae49d-187"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-187"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="ae49d-188">詳細については、「[Exchange Online の制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ae49d-188">For more information, see [Exchange Online limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="ae49d-p109">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p109">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>

## <a name="channel-names"></a><span data-ttu-id="ae49d-191">チャネル名</span><span class="sxs-lookup"><span data-stu-id="ae49d-191">Channel names</span></span>

<span data-ttu-id="ae49d-192">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="ae49d-192">Channel names can't contain the following characters or words:</span></span>

|<span data-ttu-id="ae49d-193">種類</span><span class="sxs-lookup"><span data-stu-id="ae49d-193">Type</span></span>|<span data-ttu-id="ae49d-194">例</span><span class="sxs-lookup"><span data-stu-id="ae49d-194">Example</span></span>|
|---------|---------|
|<span data-ttu-id="ae49d-195">文字</span><span class="sxs-lookup"><span data-stu-id="ae49d-195">Characters</span></span>     | <span data-ttu-id="ae49d-p110">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span><span class="sxs-lookup"><span data-stu-id="ae49d-p110">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span></span>        |
|<span data-ttu-id="ae49d-198">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="ae49d-198">Characters in these ranges</span></span>    | <span data-ttu-id="ae49d-199">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="ae49d-199">0 to 1F</span></span><br><span data-ttu-id="ae49d-200">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="ae49d-200">80 to 9F</span></span>        |
|<span data-ttu-id="ae49d-201">単語</span><span class="sxs-lookup"><span data-stu-id="ae49d-201">Words</span></span>     | <span data-ttu-id="ae49d-202">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="ae49d-202">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="ae49d-203">チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="ae49d-203">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="ae49d-204">会議と通話</span><span class="sxs-lookup"><span data-stu-id="ae49d-204">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae49d-205">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="ae49d-205">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="ae49d-206">**お客様のニーズを引き続きサポートするため、2021年6月30日まで、** などのライブ イベントへの一時的な制約を増やします。</span><span class="sxs-lookup"><span data-stu-id="ae49d-206">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="ae49d-207">イベントでは、最大2万の出席者をサポートします</span><span class="sxs-lookup"><span data-stu-id="ae49d-207">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="ae49d-208">テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="ae49d-208">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="ae49d-209">ブロードキャストあたり16時間のイベント期間</span><span class="sxs-lookup"><span data-stu-id="ae49d-209">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="ae49d-p111">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブ イベントを計画できます。チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p111">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span>

|<span data-ttu-id="ae49d-213">機能</span><span class="sxs-lookup"><span data-stu-id="ae49d-213">Feature</span></span>     | <span data-ttu-id="ae49d-214">上限</span><span class="sxs-lookup"><span data-stu-id="ae49d-214">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="ae49d-215">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="ae49d-215">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="ae49d-216">1000。GCC は含まれますが、GCCH、DoD、または A1 (300) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="ae49d-216">1000, includes GCC but not yet for GCCH, DoD, or A1 (300).</span></span> <span data-ttu-id="ae49d-217">**表示専用** では、開催者が E3/E5/A3/A5 SKU および Government (GCC、GCC High、DoD) のライセンスを持っている会議に、最大 2 万人の聴取のみの参加者が参加できます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-217">**View-only** allows for up to 20,000 listen-only participants to join a meeting in which the organizer has a license for E3/E5/A3/A5 SKU, as well as, Government (GCC, GCC High, DoD).</span></span> <span data-ttu-id="ae49d-218">[表示専用エクスペリエンス](view-only-meeting-experience.md)に関する詳細。</span><span class="sxs-lookup"><span data-stu-id="ae49d-218">Learn more about the [View-only experience](view-only-meeting-experience.md).</span></span>|
|<span data-ttu-id="ae49d-219">チャットから開始されるビデオまたは音声通話に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="ae49d-219">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="ae49d-220">20</span><span class="sxs-lookup"><span data-stu-id="ae49d-220">20</span></span> |
|<span data-ttu-id="ae49d-221">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="ae49d-221">Max PowerPoint File Size</span></span> | <span data-ttu-id="ae49d-222">2GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-222">2GB</span></span>|
|<span data-ttu-id="ae49d-223">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="ae49d-223">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="ae49d-224">20 日間</span><span class="sxs-lookup"><span data-stu-id="ae49d-224">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="ae49d-225">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="ae49d-225">Meeting expiration</span></span>

> [!NOTE]
> <span data-ttu-id="ae49d-p113">会議の URL は機能を停止しません。有効期限は、任意の PSTN のダイヤルイン番号または基となる会議ポリシーと設定 (あるいはその両方) にのみ関係します。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p113">A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers and/or underlying meeting policies and settings.</span></span>

|<span data-ttu-id="ae49d-228">会議の種類</span><span class="sxs-lookup"><span data-stu-id="ae49d-228">Meeting type</span></span>  |<span data-ttu-id="ae49d-229">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="ae49d-229">Meeting expires after this much time</span></span>  |<span data-ttu-id="ae49d-230">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="ae49d-230">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ae49d-231">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="ae49d-231">Meet now</span></span>     |<span data-ttu-id="ae49d-232">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="ae49d-232">Start time + 8 hours</span></span>         |<span data-ttu-id="ae49d-233">該当なし</span><span class="sxs-lookup"><span data-stu-id="ae49d-233">N/A</span></span>         |
|<span data-ttu-id="ae49d-234">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="ae49d-234">Regular with no end time</span></span>     |<span data-ttu-id="ae49d-235">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="ae49d-235">Start time + 60 days</span></span>         | <span data-ttu-id="ae49d-236">60 日</span><span class="sxs-lookup"><span data-stu-id="ae49d-236">60 days</span></span>        |
|<span data-ttu-id="ae49d-237">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="ae49d-237">Regular with end time</span></span>     |<span data-ttu-id="ae49d-238">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="ae49d-238">End time + 60 days</span></span>         |<span data-ttu-id="ae49d-239">60 日</span><span class="sxs-lookup"><span data-stu-id="ae49d-239">60 days</span></span>         |
|<span data-ttu-id="ae49d-240">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="ae49d-240">Recurring with no end time</span></span>     |<span data-ttu-id="ae49d-241">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="ae49d-241">Start time + 60 days</span></span>         |<span data-ttu-id="ae49d-242">60 日</span><span class="sxs-lookup"><span data-stu-id="ae49d-242">60 days</span></span>         |
|<span data-ttu-id="ae49d-243">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="ae49d-243">Recurring with end time</span></span>     |<span data-ttu-id="ae49d-244">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="ae49d-244">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="ae49d-245">60 日</span><span class="sxs-lookup"><span data-stu-id="ae49d-245">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="ae49d-246">Microsoft Teams 会議には、24 時間の時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="ae49d-246">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="ae49d-247">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="ae49d-247">Teams Live Events</span></span>

|<span data-ttu-id="ae49d-248">機能</span><span class="sxs-lookup"><span data-stu-id="ae49d-248">Feature</span></span>     | <span data-ttu-id="ae49d-249">上限</span><span class="sxs-lookup"><span data-stu-id="ae49d-249">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="ae49d-250">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="ae49d-250">Audience size</span></span> | <span data-ttu-id="ae49d-251">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="ae49d-251">10,000 attendees</span></span> |
|<span data-ttu-id="ae49d-252">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="ae49d-252">Duration of event</span></span> | <span data-ttu-id="ae49d-253">4 時間</span><span class="sxs-lookup"><span data-stu-id="ae49d-253">4 hours</span></span> |
|<span data-ttu-id="ae49d-254">Microsoft 365 または Office 365 組織で実行されている同時ライブ イベント <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ae49d-254">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="ae49d-255">15</span><span class="sxs-lookup"><span data-stu-id="ae49d-255">15</span></span> |

<span data-ttu-id="ae49d-p114"><sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p114"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="ae49d-p115">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。「[Teams のライブ イベントのスケジュール](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p115">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae49d-261">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="ae49d-261">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="ae49d-262">**お客様のニーズを引き続きサポートするため、2021年6月30日まで、** などのライブ イベントへの一時的な制約を増やします。</span><span class="sxs-lookup"><span data-stu-id="ae49d-262">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="ae49d-263">イベントでは、最大2万の出席者をサポートします</span><span class="sxs-lookup"><span data-stu-id="ae49d-263">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="ae49d-264">テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="ae49d-264">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="ae49d-265">ブロードキャストあたり16時間のイベント期間</span><span class="sxs-lookup"><span data-stu-id="ae49d-265">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="ae49d-p116">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブ イベントを計画できます。チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p116">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> 

## <a name="presence-in-outlook"></a><span data-ttu-id="ae49d-269">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="ae49d-269">Presence in Outlook</span></span>

<span data-ttu-id="ae49d-p117">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p117">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="ae49d-272">ストレージ</span><span class="sxs-lookup"><span data-stu-id="ae49d-272">Storage</span></span>

<span data-ttu-id="ae49d-p118">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p118">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="ae49d-275">各[プライベート チャネル](./private-channels.md)には、独自の SharePoint サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="ae49d-275">Each [private channel](./private-channels.md) has its own SharePoint site (previously called "site collection").</span></span>

<span data-ttu-id="ae49d-p119">テナントで有効な SharePoint Online をお持ちでない場合は、Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p119">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="ae49d-p120">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレ ベルで構成されるすべてのコンプライアンス ルールが順守されます。(詳しくは、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="ae49d-p120">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="ae49d-p121">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p121">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="ae49d-282">機能</span><span class="sxs-lookup"><span data-stu-id="ae49d-282">Feature</span></span>                 |<span data-ttu-id="ae49d-283">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="ae49d-283">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="ae49d-284">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="ae49d-284">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="ae49d-285">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="ae49d-285">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="ae49d-286">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="ae49d-286">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="ae49d-287">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="ae49d-287">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="ae49d-288">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="ae49d-288">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="ae49d-289">ストレージ</span><span class="sxs-lookup"><span data-stu-id="ae49d-289">Storage</span></span>                 |<span data-ttu-id="ae49d-290">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-290">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="ae49d-291">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-291">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="ae49d-292">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-292">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="ae49d-293">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-293">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="ae49d-294">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-294">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="ae49d-295">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="ae49d-295">1 TB per organization</span></span>           |
|<span data-ttu-id="ae49d-296">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="ae49d-296">Storage for Teams Files</span></span> |<span data-ttu-id="ae49d-297">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ae49d-297">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ae49d-298">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ae49d-298">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ae49d-299">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ae49d-299">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ae49d-300">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ae49d-300">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ae49d-301">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ae49d-301">Up to 25 TB per site or group</span></span> |<span data-ttu-id="ae49d-302">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="ae49d-302">Up to 25 TB per site or group</span></span> |
|<span data-ttu-id="ae49d-303">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="ae49d-303">File upload limit  (per file)</span></span>    |<span data-ttu-id="ae49d-304">100 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-304">100 GB</span></span>    |<span data-ttu-id="ae49d-305">100 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-305">100 GB</span></span>    |<span data-ttu-id="ae49d-306">100 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-306">100 GB</span></span>    |<span data-ttu-id="ae49d-307">100 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-307">100 GB</span></span>    |<span data-ttu-id="ae49d-308">100 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-308">100 GB</span></span>    |<span data-ttu-id="ae49d-309">100 GB</span><span class="sxs-lookup"><span data-stu-id="ae49d-309">100 GB</span></span>    |

<span data-ttu-id="ae49d-310">チャネルは、チーム用に作成された SharePoint Online サイト内のフォルダーによってバックアップされるため、チャネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="ae49d-310">Channels are backed by folders within the SharePoint Online site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="ae49d-311">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae49d-311">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="ae49d-312">クラス チーム</span><span class="sxs-lookup"><span data-stu-id="ae49d-312">Class teams</span></span>

<span data-ttu-id="ae49d-p122">Microsoft Teams for Education には、教室での授業など、独自の教育シナリオ用に設計されたテンプレートが用意されています。クラス チームなど、チームの種類の詳細については、「[Microsoft Teams で共同作業を行うチームの種類を選択する](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p122">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="ae49d-315">クラス チームは、追加のアプリが含まれるテンプレートの種類で、チーム メンバーの数に応じた制限があります。</span><span class="sxs-lookup"><span data-stu-id="ae49d-315">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="ae49d-316">クラスチームを使用するには、[Office 365 Education ライセンス](https://www.microsoft.com/education/products/office)が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae49d-316">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="ae49d-317">クラスチームの制限を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="ae49d-317">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="ae49d-318">機能</span><span class="sxs-lookup"><span data-stu-id="ae49d-318">Feature</span></span>  |<span data-ttu-id="ae49d-319">上限</span><span class="sxs-lookup"><span data-stu-id="ae49d-319">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="ae49d-320">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-320">Number of members in a team</span></span>    | <span data-ttu-id="ae49d-321">この記事の「[チームとチャネル](#teams-and-channels)」のセクションを参照してください</span><span class="sxs-lookup"><span data-stu-id="ae49d-321">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="ae49d-322">クラスチームで課題を使用するメンバーの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-322">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="ae49d-323">200</span><span class="sxs-lookup"><span data-stu-id="ae49d-323">200</span></span>        |
|<span data-ttu-id="ae49d-324">クラスチームで OneNote Class Notebook を使用するためのメンバー数</span><span class="sxs-lookup"><span data-stu-id="ae49d-324">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="ae49d-325">200</span><span class="sxs-lookup"><span data-stu-id="ae49d-325">200</span></span>         |

<span data-ttu-id="ae49d-p123">クラス チームは、200 を超えるメンバーをサポートできます。ただし、チーム内で課題アプリまたは Class Notebook アプリのいずれかを使用する場合は、メンバー数を上記の上限未満に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae49d-p123">A class team can support more than 200 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>

## <a name="tags"></a><span data-ttu-id="ae49d-328">タグ</span><span class="sxs-lookup"><span data-stu-id="ae49d-328">Tags</span></span>

|<span data-ttu-id="ae49d-329">機能</span><span class="sxs-lookup"><span data-stu-id="ae49d-329">Feature</span></span>  |<span data-ttu-id="ae49d-330">上限</span><span class="sxs-lookup"><span data-stu-id="ae49d-330">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="ae49d-331">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="ae49d-331">Number of tags per team</span></span>    | <span data-ttu-id="ae49d-332">100</span><span class="sxs-lookup"><span data-stu-id="ae49d-332">100</span></span>        |
|<span data-ttu-id="ae49d-333">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="ae49d-333">Number of suggested default tags per team</span></span>    | <span data-ttu-id="ae49d-334">25</span><span class="sxs-lookup"><span data-stu-id="ae49d-334">25</span></span>        |
|<span data-ttu-id="ae49d-335">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="ae49d-335">Number of team members assign to a tag</span></span>    |<span data-ttu-id="ae49d-336">100</span><span class="sxs-lookup"><span data-stu-id="ae49d-336">100</span></span>         |
|<span data-ttu-id="ae49d-337">チームごとにユーザーに割り当てられたタグ数</span><span class="sxs-lookup"><span data-stu-id="ae49d-337">Number of tags assigned to a user per team</span></span>    |<span data-ttu-id="ae49d-338">25</span><span class="sxs-lookup"><span data-stu-id="ae49d-338">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="ae49d-339">連絡先</span><span class="sxs-lookup"><span data-stu-id="ae49d-339">Contacts</span></span>

<span data-ttu-id="ae49d-340">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae49d-340">Teams uses these contacts:</span></span>

- <span data-ttu-id="ae49d-341">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="ae49d-341">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="ae49d-342">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="ae49d-342">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="ae49d-343">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-343">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="ae49d-344">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae49d-344">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="ae49d-345">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="ae49d-345">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="ae49d-346">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="ae49d-346">Operating systems</span></span>

<span data-ttu-id="ae49d-347">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ae49d-347">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
