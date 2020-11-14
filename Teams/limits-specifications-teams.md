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
ms.openlocfilehash: a552fd88d469c7daaae324614c398c24ac2f9d41
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031363"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="07149-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="07149-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="07149-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="07149-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="07149-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="07149-105">Teams and channels</span></span>

|<span data-ttu-id="07149-106">機能</span><span class="sxs-lookup"><span data-stu-id="07149-106">Feature</span></span>    | <span data-ttu-id="07149-107">上限</span><span class="sxs-lookup"><span data-stu-id="07149-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="07149-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="07149-108">Number of teams a user can create</span></span> | <span data-ttu-id="07149-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="07149-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="07149-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="07149-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="07149-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="07149-111">1,000&sup2;</span></span>|
|<span data-ttu-id="07149-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="07149-112">Number of members in a team</span></span> | <span data-ttu-id="07149-113">10,000<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="07149-113">10,000<sup>5</sup></span></span>     |
|<span data-ttu-id="07149-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="07149-114">Number of owners per team</span></span> | <span data-ttu-id="07149-115">100</span><span class="sxs-lookup"><span data-stu-id="07149-115">100</span></span>   |
|<span data-ttu-id="07149-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="07149-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="07149-117">5</span><span class="sxs-lookup"><span data-stu-id="07149-117">5</span></span>     |
|<span data-ttu-id="07149-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="07149-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="07149-119">5,000</span><span class="sxs-lookup"><span data-stu-id="07149-119">5,000</span></span>       |
|<span data-ttu-id="07149-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="07149-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="07149-121">500,000</span><span class="sxs-lookup"><span data-stu-id="07149-121">500,000</span></span>   |
|<span data-ttu-id="07149-122">Microsoft 365 または Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="07149-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="07149-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="07149-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="07149-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="07149-124">Number of channels per team</span></span>    | <span data-ttu-id="07149-125">200 (削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="07149-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="07149-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="07149-126">Number of Private channels per team</span></span>    |<span data-ttu-id="07149-127">30</span><span class="sxs-lookup"><span data-stu-id="07149-127">30</span></span>| <span data-ttu-id="07149-128">(削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="07149-128">(includes deleted channels)&sup3;</span></span>
|<span data-ttu-id="07149-129">プライベート チャネルのメンバー数</span><span class="sxs-lookup"><span data-stu-id="07149-129">Number of members in a Private channel</span></span>    |<span data-ttu-id="07149-130">250 人</span><span class="sxs-lookup"><span data-stu-id="07149-130">250</span></span>|
|<span data-ttu-id="07149-131">チームに変換できる Office 365 グループのメンバーの最大数</span><span class="sxs-lookup"><span data-stu-id="07149-131">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="07149-132">10,000<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="07149-132">10,000<sup>5</sup></span></span>     |
|<span data-ttu-id="07149-133">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="07149-133">Channel conversation post size</span></span> | <span data-ttu-id="07149-134">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="07149-134">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="07149-135"><sup>1</sup> Azure Active Directory のすべてのディレクトリ オブジェクトはこの制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="07149-135"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="07149-136">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="07149-136">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="07149-137"><sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="07149-137"><sup>2</sup> This limit includes archived teams.</span></span>

<span data-ttu-id="07149-138"><sup>3</sup> 削除したチャネルは、30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="07149-138"><sup>3</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="07149-139">この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルまたは30のプライベートチャンネルとしてカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="07149-139">During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit.</span></span> <span data-ttu-id="07149-140">30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限内のチャンネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="07149-140">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="07149-141"><sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="07149-141"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="07149-142"><sup>5</sup> GCC の チーム は 5,000 人のメンバーしか収容できず、GCCH / DoD のチームは 2,500 人のメンバーしか収容できません。</span><span class="sxs-lookup"><span data-stu-id="07149-142"><sup>5</sup> Teams in GCC can only accommodate 5,000 members and teams in GCCH/DoD can only accommodate 2,500 members.</span></span>
## <a name="messaging"></a><span data-ttu-id="07149-143">Messaging</span><span class="sxs-lookup"><span data-stu-id="07149-143">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="07149-144">チャット</span><span class="sxs-lookup"><span data-stu-id="07149-144">Chat</span></span>

<span data-ttu-id="07149-145">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="07149-145">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="07149-146">これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。</span><span class="sxs-lookup"><span data-stu-id="07149-146">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="07149-147">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="07149-147">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="07149-148">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="07149-148">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="07149-149">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="07149-149">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="07149-150">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="07149-150">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="07149-151">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="07149-151">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="07149-152">機能</span><span class="sxs-lookup"><span data-stu-id="07149-152">Feature</span></span>  | <span data-ttu-id="07149-153">上限</span><span class="sxs-lookup"><span data-stu-id="07149-153">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="07149-154">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="07149-154">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="07149-155">250 人</span><span class="sxs-lookup"><span data-stu-id="07149-155">250</span></span> |
|<span data-ttu-id="07149-156">チャットから開始されるビデオまたは音声通話に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="07149-156">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="07149-157">20</span><span class="sxs-lookup"><span data-stu-id="07149-157">20</span></span> |
|<span data-ttu-id="07149-158">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="07149-158">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="07149-159">10</span><span class="sxs-lookup"><span data-stu-id="07149-159">10</span></span>     |
|<span data-ttu-id="07149-160">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="07149-160">Chat size</span></span> | <span data-ttu-id="07149-161">投稿ごとに約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="07149-161">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="07149-162"><sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。</span><span class="sxs-lookup"><span data-stu-id="07149-162"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span> <span data-ttu-id="07149-163">プライベート グループのチャットに 20 を超えるメンバーが含まれている場合は、「配信オプションの設定」 (!) ボタンも削除されます。</span><span class="sxs-lookup"><span data-stu-id="07149-163">The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="07149-164"><sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07149-164"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="07149-165"><sup>3</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="07149-165"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="07149-166">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="07149-166">Emailing a channel</span></span>

 <span data-ttu-id="07149-167">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="07149-167">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="07149-168">メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="07149-168">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="07149-169">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="07149-169">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="07149-170">機能</span><span class="sxs-lookup"><span data-stu-id="07149-170">Feature</span></span>  | <span data-ttu-id="07149-171">上限</span><span class="sxs-lookup"><span data-stu-id="07149-171">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="07149-172">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="07149-172">Message size<sup>1<sup></span></span> | <span data-ttu-id="07149-173">24 KB</span><span class="sxs-lookup"><span data-stu-id="07149-173">24 KB</span></span> |
|<span data-ttu-id="07149-174">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="07149-174">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="07149-175">20</span><span class="sxs-lookup"><span data-stu-id="07149-175">20</span></span>     |
|<span data-ttu-id="07149-176">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="07149-176">Size of each file attachment</span></span> | <span data-ttu-id="07149-177">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="07149-177">Less than 10 MB</span></span> |
|<span data-ttu-id="07149-178">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="07149-178">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="07149-179">50</span><span class="sxs-lookup"><span data-stu-id="07149-179">50</span></span>   |

<span data-ttu-id="07149-180"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="07149-180"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="07149-181"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07149-181"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="07149-182">詳細については、「[ Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="07149-182">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="07149-183">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="07149-183">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span> <span data-ttu-id="07149-184">Office の GCC/GCCH/DOD 組織用Teams では、チャネルにメールを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="07149-184">Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>



## <a name="channel-names"></a><span data-ttu-id="07149-185">チャネル名</span><span class="sxs-lookup"><span data-stu-id="07149-185">Channel names</span></span>

<span data-ttu-id="07149-186">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="07149-186">Channel names can't contain the following characters or words.</span></span>

|<span data-ttu-id="07149-187">種類</span><span class="sxs-lookup"><span data-stu-id="07149-187">Type</span></span>|<span data-ttu-id="07149-188">例</span><span class="sxs-lookup"><span data-stu-id="07149-188">Example</span></span>|
|---------|---------|
|<span data-ttu-id="07149-189">文字</span><span class="sxs-lookup"><span data-stu-id="07149-189">Characters</span></span>     | <span data-ttu-id="07149-190">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="07149-190">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="07149-191">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="07149-191">&#124; ' " , .</span></span>        |
|<span data-ttu-id="07149-192">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="07149-192">Characters in these ranges</span></span>    | <span data-ttu-id="07149-193">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="07149-193">0 to 1F</span></span><br><span data-ttu-id="07149-194">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="07149-194">80 to 9F</span></span>        |
|<span data-ttu-id="07149-195">単語</span><span class="sxs-lookup"><span data-stu-id="07149-195">Words</span></span>     | <span data-ttu-id="07149-196">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="07149-196">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="07149-197">チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="07149-197">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="07149-198">会議と通話</span><span class="sxs-lookup"><span data-stu-id="07149-198">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07149-199">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="07149-199">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="07149-200">**お客様をサポートするために、2021 年 1 月 1 日まで、Teams、Stream、Yammer でホストされるライブイベントの一時的な制限の引き上げを延長します。**</span><span class="sxs-lookup"><span data-stu-id="07149-200">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for Live Events hosted in Teams, Stream, and Yammer, including** :</span></span>
>
>- <span data-ttu-id="07149-201">イベントごとに最大 2 万人の参加者</span><span class="sxs-lookup"><span data-stu-id="07149-201">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="07149-202">Teams テナントごとに最大 50 の同時イベント</span><span class="sxs-lookup"><span data-stu-id="07149-202">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="07149-203">ブロードキャストあたり最大 16 時間</span><span class="sxs-lookup"><span data-stu-id="07149-203">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="07149-204">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブイベントを計画できます。</span><span class="sxs-lookup"><span data-stu-id="07149-204">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program.</span></span> <span data-ttu-id="07149-205">チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。</span><span class="sxs-lookup"><span data-stu-id="07149-205">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="07149-206">[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="07149-206">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="07149-207">**2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、 [Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="07149-207">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>


|<span data-ttu-id="07149-208">機能</span><span class="sxs-lookup"><span data-stu-id="07149-208">Feature</span></span>     | <span data-ttu-id="07149-209">上限</span><span class="sxs-lookup"><span data-stu-id="07149-209">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="07149-210">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="07149-210">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="07149-211">300</span><span class="sxs-lookup"><span data-stu-id="07149-211">300</span></span> |
|<span data-ttu-id="07149-212">チャットから開始されるビデオまたは音声通話に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="07149-212">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="07149-213">20</span><span class="sxs-lookup"><span data-stu-id="07149-213">20</span></span> |
|<span data-ttu-id="07149-214">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="07149-214">Max PowerPoint File Size</span></span> | <span data-ttu-id="07149-215">2GB</span><span class="sxs-lookup"><span data-stu-id="07149-215">2GB</span></span>|
|<span data-ttu-id="07149-216">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="07149-216">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="07149-217">20 日間</span><span class="sxs-lookup"><span data-stu-id="07149-217">20 days</span></span> |

>[!Note]
> <span data-ttu-id="07149-218">Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint ](tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。</span><span class="sxs-lookup"><span data-stu-id="07149-218">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="07149-219">リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。</span><span class="sxs-lookup"><span data-stu-id="07149-219">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="07149-220">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="07149-220">Meeting expiration</span></span>

|<span data-ttu-id="07149-221">会議の種類</span><span class="sxs-lookup"><span data-stu-id="07149-221">Meeting type</span></span>  |<span data-ttu-id="07149-222">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="07149-222">Meeting expires after this much time</span></span>  |<span data-ttu-id="07149-223">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="07149-223">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="07149-224">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="07149-224">Meet now</span></span>     |<span data-ttu-id="07149-225">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="07149-225">Start time + 8 hours</span></span>         |<span data-ttu-id="07149-226">該当なし</span><span class="sxs-lookup"><span data-stu-id="07149-226">N/A</span></span>         |
|<span data-ttu-id="07149-227">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="07149-227">Regular with no end time</span></span>     |<span data-ttu-id="07149-228">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="07149-228">Start time + 60 days</span></span>         | <span data-ttu-id="07149-229">60 日</span><span class="sxs-lookup"><span data-stu-id="07149-229">60 days</span></span>        |
|<span data-ttu-id="07149-230">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="07149-230">Regular with end time</span></span>     |<span data-ttu-id="07149-231">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="07149-231">End time + 60 days</span></span>         |<span data-ttu-id="07149-232">60 日</span><span class="sxs-lookup"><span data-stu-id="07149-232">60 days</span></span>         |
|<span data-ttu-id="07149-233">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="07149-233">Recurring with no end time</span></span>     |<span data-ttu-id="07149-234">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="07149-234">Start time + 60 days</span></span>         |<span data-ttu-id="07149-235">60 日</span><span class="sxs-lookup"><span data-stu-id="07149-235">60 days</span></span>         |
|<span data-ttu-id="07149-236">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="07149-236">Recurring with end time</span></span>     |<span data-ttu-id="07149-237">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="07149-237">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="07149-238">60 日</span><span class="sxs-lookup"><span data-stu-id="07149-238">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="07149-239">Microsoft Teams 会議には、24 時間の時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="07149-239">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="07149-240">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="07149-240">Teams Live Events</span></span>

|<span data-ttu-id="07149-241">機能</span><span class="sxs-lookup"><span data-stu-id="07149-241">Feature</span></span>     | <span data-ttu-id="07149-242">上限</span><span class="sxs-lookup"><span data-stu-id="07149-242">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="07149-243">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="07149-243">Audience size</span></span> | <span data-ttu-id="07149-244">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="07149-244">10,000 attendees</span></span> |
|<span data-ttu-id="07149-245">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="07149-245">Duration of event</span></span> | <span data-ttu-id="07149-246">4 時間</span><span class="sxs-lookup"><span data-stu-id="07149-246">4 hours</span></span> |
|<span data-ttu-id="07149-247">Microsoft 365 または Office 365 組織で実行されている同時ライブ イベント <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="07149-247">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="07149-248">15</span><span class="sxs-lookup"><span data-stu-id="07149-248">15</span></span> |

<span data-ttu-id="07149-249"><sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。</span><span class="sxs-lookup"><span data-stu-id="07149-249"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="07149-250">プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。</span><span class="sxs-lookup"><span data-stu-id="07149-250">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="07149-251">16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="07149-251">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="07149-252">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="07149-252">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span> <span data-ttu-id="07149-253">詳細については、「[Teams ライブ イベントのスケジュールを設定する](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="07149-253">See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07149-254">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="07149-254">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="07149-255">**お客様をサポートするために、2021 年 1 月 1 日まで、Teams、Stream、Yammer でホストされるライブイベントの一時的な制限の引き上げを延長します。**</span><span class="sxs-lookup"><span data-stu-id="07149-255">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for Live Events hosted in Teams, Stream, and Yammer, including** :</span></span>
>
> - <span data-ttu-id="07149-256">イベントごとに最大 2 万人の参加者</span><span class="sxs-lookup"><span data-stu-id="07149-256">Up to 20,000 attendees per event</span></span>
> - <span data-ttu-id="07149-257">Teams テナントごとに最大 50 の同時イベント</span><span class="sxs-lookup"><span data-stu-id="07149-257">Up to 50 simultaneous events per Teams tenant</span></span>
> - <span data-ttu-id="07149-258">ブロードキャストあたり最大 16 時間</span><span class="sxs-lookup"><span data-stu-id="07149-258">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="07149-259">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブイベントを計画できます。</span><span class="sxs-lookup"><span data-stu-id="07149-259">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program.</span></span> <span data-ttu-id="07149-260">チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。</span><span class="sxs-lookup"><span data-stu-id="07149-260">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="07149-261">[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="07149-261">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="07149-262">**2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、 [Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="07149-262">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="07149-263">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="07149-263">Presence in Outlook</span></span>

<span data-ttu-id="07149-264">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="07149-264">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="07149-265">Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07149-265">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="07149-266">ストレージ</span><span class="sxs-lookup"><span data-stu-id="07149-266">Storage</span></span>

<span data-ttu-id="07149-p114">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="07149-p114">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="07149-269">各 [プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels) には、独自の SharePoint サイト コレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="07149-269">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="07149-270">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="07149-270">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="07149-271">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="07149-271">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="07149-272">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="07149-272">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="07149-273">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="07149-273">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="07149-274">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="07149-274">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="07149-275">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="07149-275">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="07149-276">機能</span><span class="sxs-lookup"><span data-stu-id="07149-276">Feature</span></span>                 |<span data-ttu-id="07149-277">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="07149-277">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="07149-278">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="07149-278">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="07149-279">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="07149-279">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="07149-280">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="07149-280">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="07149-281">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="07149-281">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="07149-282">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="07149-282">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="07149-283">ストレージ</span><span class="sxs-lookup"><span data-stu-id="07149-283">Storage</span></span>                 |<span data-ttu-id="07149-284">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="07149-284">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="07149-285">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="07149-285">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="07149-286">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="07149-286">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="07149-287">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="07149-287">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="07149-288">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="07149-288">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="07149-289">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="07149-289">1 TB per organization</span></span>           |
|<span data-ttu-id="07149-290">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="07149-290">Storage for Teams Files</span></span> |<span data-ttu-id="07149-291">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="07149-291">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="07149-292">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="07149-292">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="07149-293">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="07149-293">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="07149-294">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="07149-294">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="07149-295">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="07149-295">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="07149-296">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="07149-296">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="07149-297">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="07149-297">File upload limit  (per file)</span></span>    |<span data-ttu-id="07149-298">100 GB</span><span class="sxs-lookup"><span data-stu-id="07149-298">100 GB</span></span>    |<span data-ttu-id="07149-299">100 GB</span><span class="sxs-lookup"><span data-stu-id="07149-299">100 GB</span></span>    |<span data-ttu-id="07149-300">100 GB</span><span class="sxs-lookup"><span data-stu-id="07149-300">100 GB</span></span>    |<span data-ttu-id="07149-301">100 GB</span><span class="sxs-lookup"><span data-stu-id="07149-301">100 GB</span></span>    |<span data-ttu-id="07149-302">100 GB</span><span class="sxs-lookup"><span data-stu-id="07149-302">100 GB</span></span>    |<span data-ttu-id="07149-303">100 GB</span><span class="sxs-lookup"><span data-stu-id="07149-303">100 GB</span></span>    |

<span data-ttu-id="07149-304">チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="07149-304">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="07149-305">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07149-305">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="07149-306">クラス チーム</span><span class="sxs-lookup"><span data-stu-id="07149-306">Class teams</span></span>

<span data-ttu-id="07149-307">Microsoft Teams for Education には、教育機関向けの特別なシナリオ (授業教材など) 向けのテンプレートが用意されています。//Microsoft Teams for Education には、教室での授業など、独自の教育シナリオ用に設計されたテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="07149-307">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching.</span></span> <span data-ttu-id="07149-308">クラスチームなど、チームの種類の詳細については、「[Microsoft Teams で共同作業を行うチームの種類を選択する](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07149-308">More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="07149-309">クラスチームは、追加のアプリが含まれるテンプレートの種類で、チームメンバーの数に応じた制限があります。</span><span class="sxs-lookup"><span data-stu-id="07149-309">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="07149-310">クラスチームを使用するには、[Office 365 Education ライセンス](https://www.microsoft.com/education/products/office)が必要です。</span><span class="sxs-lookup"><span data-stu-id="07149-310">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="07149-311">クラスチームの制限を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="07149-311">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="07149-312">機能</span><span class="sxs-lookup"><span data-stu-id="07149-312">Feature</span></span>  |<span data-ttu-id="07149-313">上限</span><span class="sxs-lookup"><span data-stu-id="07149-313">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="07149-314">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="07149-314">Number of members in a team</span></span>    | <span data-ttu-id="07149-315">この記事の「[チームとチャネル](#teams-and-channels)」のセクションを参照してください</span><span class="sxs-lookup"><span data-stu-id="07149-315">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="07149-316">クラスチームで課題を使用するメンバーの数</span><span class="sxs-lookup"><span data-stu-id="07149-316">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="07149-317">200</span><span class="sxs-lookup"><span data-stu-id="07149-317">200</span></span>        |
|<span data-ttu-id="07149-318">クラスチームで OneNote Class Notebook を使用するためのメンバー数</span><span class="sxs-lookup"><span data-stu-id="07149-318">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="07149-319">200</span><span class="sxs-lookup"><span data-stu-id="07149-319">200</span></span>         |

<span data-ttu-id="07149-320">クラスチームは、200を超えるメンバーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="07149-320">A class team can support more than 200 members.</span></span> <span data-ttu-id="07149-321">ただし、チーム内でアサインメントアプリまたはクラスノートブックアプリのいずれかを使用する場合は、メンバー数を上記の上限未満に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="07149-321">However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>


## <a name="tags"></a><span data-ttu-id="07149-322">タグ</span><span class="sxs-lookup"><span data-stu-id="07149-322">Tags</span></span>

|<span data-ttu-id="07149-323">機能</span><span class="sxs-lookup"><span data-stu-id="07149-323">Feature</span></span>  |<span data-ttu-id="07149-324">上限</span><span class="sxs-lookup"><span data-stu-id="07149-324">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="07149-325">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="07149-325">Number of tags per team</span></span>    | <span data-ttu-id="07149-326">100</span><span class="sxs-lookup"><span data-stu-id="07149-326">100</span></span>        |
|<span data-ttu-id="07149-327">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="07149-327">Number of suggested default tags per team</span></span>    | <span data-ttu-id="07149-328">25</span><span class="sxs-lookup"><span data-stu-id="07149-328">25</span></span>        |
|<span data-ttu-id="07149-329">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="07149-329">Number of team members assign to a tag</span></span>    |<span data-ttu-id="07149-330">100</span><span class="sxs-lookup"><span data-stu-id="07149-330">100</span></span>         |
|<span data-ttu-id="07149-331">ユーザーに割り当てられたるタグ数</span><span class="sxs-lookup"><span data-stu-id="07149-331">Number of tags assigned to a user</span></span>    |<span data-ttu-id="07149-332">25</span><span class="sxs-lookup"><span data-stu-id="07149-332">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="07149-333">連絡先</span><span class="sxs-lookup"><span data-stu-id="07149-333">Contacts</span></span>

<span data-ttu-id="07149-334">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="07149-334">Teams uses these contacts:</span></span>

- <span data-ttu-id="07149-335">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="07149-335">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="07149-336">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="07149-336">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="07149-337">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[ **チャット** ]  >  [ **連絡先** ] または [ **通話** ]  >  [ **連絡先** ] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="07149-337">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="07149-338">Teams ユーザーは、[ **通話** ]  >  [ **連絡先** ] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="07149-338">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="07149-339">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="07149-339">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="07149-340">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="07149-340">Operating systems</span></span>

<span data-ttu-id="07149-341">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="07149-341">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
