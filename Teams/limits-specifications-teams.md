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
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a95606786b59718e99adedb9a33ad31c1903f75
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308200"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="8b799-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="8b799-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="8b799-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b799-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="8b799-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="8b799-105">Teams and channels</span></span>

|<span data-ttu-id="8b799-106">機能</span><span class="sxs-lookup"><span data-stu-id="8b799-106">Feature</span></span>    | <span data-ttu-id="8b799-107">上限</span><span class="sxs-lookup"><span data-stu-id="8b799-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="8b799-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="8b799-108">Number of teams a user can create</span></span> | <span data-ttu-id="8b799-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="8b799-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="8b799-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="8b799-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="8b799-111">1,000</span><span class="sxs-lookup"><span data-stu-id="8b799-111">1,000</span></span>|
|<span data-ttu-id="8b799-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8b799-112">Number of members in a team</span></span> | <span data-ttu-id="8b799-113">10,000</span><span class="sxs-lookup"><span data-stu-id="8b799-113">10,000</span></span>       |
|<span data-ttu-id="8b799-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="8b799-114">Number of owners per team</span></span> | <span data-ttu-id="8b799-115">100</span><span class="sxs-lookup"><span data-stu-id="8b799-115">100</span></span>   |
|<span data-ttu-id="8b799-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="8b799-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="8b799-117">5</span><span class="sxs-lookup"><span data-stu-id="8b799-117">5</span></span>     |
|<span data-ttu-id="8b799-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8b799-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="8b799-119">5,000</span><span class="sxs-lookup"><span data-stu-id="8b799-119">5,000</span></span>       |
|<span data-ttu-id="8b799-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="8b799-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="8b799-121">500,000</span><span class="sxs-lookup"><span data-stu-id="8b799-121">500,000</span></span>   |
|<span data-ttu-id="8b799-122">Microsoft 365 または Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="8b799-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="8b799-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="8b799-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="8b799-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="8b799-124">Number of channels per team</span></span>    | <span data-ttu-id="8b799-125">200 (削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="8b799-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="8b799-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="8b799-126">Number of Private channels per team</span></span>    |<span data-ttu-id="8b799-127">30</span><span class="sxs-lookup"><span data-stu-id="8b799-127">30</span></span>|
|<span data-ttu-id="8b799-128">プライベート チャネルのメンバー数</span><span class="sxs-lookup"><span data-stu-id="8b799-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="8b799-129">250 人</span><span class="sxs-lookup"><span data-stu-id="8b799-129">250</span></span>|
|<span data-ttu-id="8b799-130">チームに変換できる Office 365 グループのメンバーの最大数</span><span class="sxs-lookup"><span data-stu-id="8b799-130">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="8b799-131">10,000</span><span class="sxs-lookup"><span data-stu-id="8b799-131">10,000</span></span>|
|<span data-ttu-id="8b799-132">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="8b799-132">Channel conversation post size</span></span> | <span data-ttu-id="8b799-133">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8b799-133">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="8b799-134"><sup>1</sup> Azure Active Directory のすべてのディレクトリ オブジェクトはこの制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="8b799-134"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="8b799-135">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="8b799-135">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="8b799-136"><sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b799-136"><sup>2</sup> This limit includes archived teams.</span></span>

<span data-ttu-id="8b799-137"><sup>3</sup> 削除したチャネルは、30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="8b799-137"><sup>3</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="8b799-138">この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルとしてカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="8b799-138">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="8b799-139">30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限である 200 チャンネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="8b799-139">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="8b799-140"><sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="8b799-140"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="8b799-141">Messaging</span><span class="sxs-lookup"><span data-stu-id="8b799-141">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="8b799-142">チャット</span><span class="sxs-lookup"><span data-stu-id="8b799-142">Chat</span></span>

<span data-ttu-id="8b799-143">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b799-143">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="8b799-144">これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。</span><span class="sxs-lookup"><span data-stu-id="8b799-144">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="8b799-145">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="8b799-145">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="8b799-146">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8b799-146">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="8b799-147">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="8b799-147">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="8b799-148">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="8b799-148">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="8b799-149">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8b799-149">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="8b799-150">機能</span><span class="sxs-lookup"><span data-stu-id="8b799-150">Feature</span></span>  | <span data-ttu-id="8b799-151">上限</span><span class="sxs-lookup"><span data-stu-id="8b799-151">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8b799-152">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b799-152">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="8b799-153">250 人</span><span class="sxs-lookup"><span data-stu-id="8b799-153">250</span></span> |
|<span data-ttu-id="8b799-154">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="8b799-154">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="8b799-155">20</span><span class="sxs-lookup"><span data-stu-id="8b799-155">20</span></span> |
|<span data-ttu-id="8b799-156">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b799-156">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="8b799-157">10</span><span class="sxs-lookup"><span data-stu-id="8b799-157">10</span></span>     |
|<span data-ttu-id="8b799-158">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="8b799-158">Chat size</span></span> | <span data-ttu-id="8b799-159">投稿ごとに約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8b799-159">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="8b799-160"><sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。</span><span class="sxs-lookup"><span data-stu-id="8b799-160"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span> <span data-ttu-id="8b799-161">プライベート グループのチャットに 20 を超えるメンバーが含まれている場合は、「配信オプションの設定」 (!) ボタンも削除されます。</span><span class="sxs-lookup"><span data-stu-id="8b799-161">The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="8b799-162"><sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b799-162"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="8b799-163"><sup>3</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="8b799-163"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="8b799-164">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="8b799-164">Emailing a channel</span></span>

 <span data-ttu-id="8b799-165">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b799-165">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="8b799-166">メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8b799-166">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="8b799-167">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8b799-167">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="8b799-168">機能</span><span class="sxs-lookup"><span data-stu-id="8b799-168">Feature</span></span>  | <span data-ttu-id="8b799-169">上限</span><span class="sxs-lookup"><span data-stu-id="8b799-169">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8b799-170">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="8b799-170">Message size<sup>1<sup></span></span> | <span data-ttu-id="8b799-171">24 KB</span><span class="sxs-lookup"><span data-stu-id="8b799-171">24 KB</span></span> |
|<span data-ttu-id="8b799-172">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b799-172">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="8b799-173">20</span><span class="sxs-lookup"><span data-stu-id="8b799-173">20</span></span>     |
|<span data-ttu-id="8b799-174">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="8b799-174">Size of each file attachment</span></span> | <span data-ttu-id="8b799-175">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="8b799-175">Less than 10 MB</span></span> |
|<span data-ttu-id="8b799-176">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b799-176">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="8b799-177">50</span><span class="sxs-lookup"><span data-stu-id="8b799-177">50</span></span>   |

<span data-ttu-id="8b799-178"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8b799-178"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="8b799-179"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b799-179"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="8b799-180">詳細については、「[ Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8b799-180">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="8b799-181">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="8b799-181">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="8b799-182">チャネル名</span><span class="sxs-lookup"><span data-stu-id="8b799-182">Channel names</span></span>

<span data-ttu-id="8b799-183">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="8b799-183">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="8b799-184">文字</span><span class="sxs-lookup"><span data-stu-id="8b799-184">Characters</span></span>     | <span data-ttu-id="8b799-185">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="8b799-185">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="8b799-186">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="8b799-186">&#124; ' " , .</span></span>        |
|<span data-ttu-id="8b799-187">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="8b799-187">Characters in these ranges</span></span>    | <span data-ttu-id="8b799-188">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="8b799-188">0 to 1F</span></span><br><span data-ttu-id="8b799-189">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="8b799-189">80 to 9F</span></span>        |
|<span data-ttu-id="8b799-190">単語</span><span class="sxs-lookup"><span data-stu-id="8b799-190">Words</span></span>     | <span data-ttu-id="8b799-191">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="8b799-191">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="8b799-192">チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="8b799-192">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="8b799-193">会議と通話</span><span class="sxs-lookup"><span data-stu-id="8b799-193">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b799-194">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="8b799-194">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="8b799-195">**お客様をサポートするために、2021 年 1 月 1 日まで、Teams、Stream、Yammer でホストされるライブイベントの一時的な制限の引き上げを延長します。**</span><span class="sxs-lookup"><span data-stu-id="8b799-195">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for live events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="8b799-196">イベントごとに最大 2 万人の参加者</span><span class="sxs-lookup"><span data-stu-id="8b799-196">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="8b799-197">Teams テナントごとに最大 50 の同時イベント</span><span class="sxs-lookup"><span data-stu-id="8b799-197">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="8b799-198">ブロードキャストあたり最大 16 時間</span><span class="sxs-lookup"><span data-stu-id="8b799-198">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="8b799-199">さらに、最大 10 万人の参加者がいるライブイベントを、MIcrosoft のライブイベント支援プログラムを通じて計画できます。</span><span class="sxs-lookup"><span data-stu-id="8b799-199">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft live events assistance program.</span></span> <span data-ttu-id="8b799-200">[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="8b799-200">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="8b799-201">**2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、[Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="8b799-201">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>


|<span data-ttu-id="8b799-202">機能</span><span class="sxs-lookup"><span data-stu-id="8b799-202">Feature</span></span>     | <span data-ttu-id="8b799-203">上限</span><span class="sxs-lookup"><span data-stu-id="8b799-203">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="8b799-204">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="8b799-204">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="8b799-205">300</span><span class="sxs-lookup"><span data-stu-id="8b799-205">300</span></span> |
|<span data-ttu-id="8b799-206">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="8b799-206">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="8b799-207">20</span><span class="sxs-lookup"><span data-stu-id="8b799-207">20</span></span> |
|<span data-ttu-id="8b799-208">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="8b799-208">Max PowerPoint File Size</span></span> | <span data-ttu-id="8b799-209">2GB</span><span class="sxs-lookup"><span data-stu-id="8b799-209">2GB</span></span>|
|<span data-ttu-id="8b799-210">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="8b799-210">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="8b799-211">20 日間</span><span class="sxs-lookup"><span data-stu-id="8b799-211">20 days</span></span> |

>[!Note]
> <span data-ttu-id="8b799-212">Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint ](tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。</span><span class="sxs-lookup"><span data-stu-id="8b799-212">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="8b799-213">リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。</span><span class="sxs-lookup"><span data-stu-id="8b799-213">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="8b799-214">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="8b799-214">Meeting expiration</span></span>

|<span data-ttu-id="8b799-215">会議の種類</span><span class="sxs-lookup"><span data-stu-id="8b799-215">Meeting type</span></span>  |<span data-ttu-id="8b799-216">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="8b799-216">Meeting expires after this much time</span></span>  |<span data-ttu-id="8b799-217">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="8b799-217">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8b799-218">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="8b799-218">Meet now</span></span>     |<span data-ttu-id="8b799-219">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="8b799-219">Start time + 8 hours</span></span>         |<span data-ttu-id="8b799-220">該当なし</span><span class="sxs-lookup"><span data-stu-id="8b799-220">N/A</span></span>         |
|<span data-ttu-id="8b799-221">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="8b799-221">Regular with no end time</span></span>     |<span data-ttu-id="8b799-222">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8b799-222">Start time + 60 days</span></span>         | <span data-ttu-id="8b799-223">60 日</span><span class="sxs-lookup"><span data-stu-id="8b799-223">60 days</span></span>        |
|<span data-ttu-id="8b799-224">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="8b799-224">Regular with end time</span></span>     |<span data-ttu-id="8b799-225">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8b799-225">End time + 60 days</span></span>         |<span data-ttu-id="8b799-226">60 日</span><span class="sxs-lookup"><span data-stu-id="8b799-226">60 days</span></span>         |
|<span data-ttu-id="8b799-227">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="8b799-227">Recurring with no end time</span></span>     |<span data-ttu-id="8b799-228">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8b799-228">Start time + 60 days</span></span>         |<span data-ttu-id="8b799-229">60 日</span><span class="sxs-lookup"><span data-stu-id="8b799-229">60 days</span></span>         |
|<span data-ttu-id="8b799-230">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="8b799-230">Recurring with end time</span></span>     |<span data-ttu-id="8b799-231">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8b799-231">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="8b799-232">60 日</span><span class="sxs-lookup"><span data-stu-id="8b799-232">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="8b799-233">Microsoft Teams 会議には、24 時間の時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="8b799-233">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="8b799-234">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="8b799-234">Teams live events</span></span>

|<span data-ttu-id="8b799-235">機能</span><span class="sxs-lookup"><span data-stu-id="8b799-235">Feature</span></span>     | <span data-ttu-id="8b799-236">上限</span><span class="sxs-lookup"><span data-stu-id="8b799-236">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="8b799-237">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="8b799-237">Audience size</span></span> | <span data-ttu-id="8b799-238">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="8b799-238">10,000 attendees</span></span> |
|<span data-ttu-id="8b799-239">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="8b799-239">Duration of event</span></span> | <span data-ttu-id="8b799-240">4 時間</span><span class="sxs-lookup"><span data-stu-id="8b799-240">4 hours</span></span> |
|<span data-ttu-id="8b799-241">Microsoft 365 または Office 365 組織で実行されている同時ライブ イベント <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b799-241">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="8b799-242">15</span><span class="sxs-lookup"><span data-stu-id="8b799-242">15</span></span> |

<span data-ttu-id="8b799-243"><sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。</span><span class="sxs-lookup"><span data-stu-id="8b799-243"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="8b799-244">プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。</span><span class="sxs-lookup"><span data-stu-id="8b799-244">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="8b799-245">16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8b799-245">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="8b799-246">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="8b799-246">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b799-247">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="8b799-247">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="8b799-248">お客様が急速に変化するコミュニケーションのニーズに対応できるように、Teams、Stream、Yammer でホストされるライブイベントの既定の上限を 2021 年 1 月 1 日まで一時的に引き上げます。</span><span class="sxs-lookup"><span data-stu-id="8b799-248">To help customers meet rapidly changing communication needs, we will temporarily raise default limits until January 1, 2021, for live events hosted in Teams, Stream, and Yammer.</span></span>
>
> - <span data-ttu-id="8b799-249">参加者の制限: イベントは最大 20,000 人の参加者をサポートできます</span><span class="sxs-lookup"><span data-stu-id="8b799-249">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="8b799-250">同時イベント: テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="8b799-250">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="8b799-251">イベントの時間: イベントの長さが 1 回のブロードキャストにつき 16 時間に延長されました</span><span class="sxs-lookup"><span data-stu-id="8b799-251">Event duration: event length has been increased to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="8b799-252">さらに、最大 10 万人の参加者がいるライブイベントを、MIcrosoft のライブイベント支援プログラムを通じて計画できます。</span><span class="sxs-lookup"><span data-stu-id="8b799-252">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft live events assistance program.</span></span> <span data-ttu-id="8b799-253">[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="8b799-253">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="8b799-254">**2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、[Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="8b799-254">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="8b799-255">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="8b799-255">Presence in Outlook</span></span>

<span data-ttu-id="8b799-256">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b799-256">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="8b799-257">Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b799-257">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="8b799-258">ストレージ</span><span class="sxs-lookup"><span data-stu-id="8b799-258">Storage</span></span>

<span data-ttu-id="8b799-p112">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="8b799-p112">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="8b799-261">各 [プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels) には、独自の SharePoint サイト コレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="8b799-261">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="8b799-262">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="8b799-262">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="8b799-263">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="8b799-263">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="8b799-264">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="8b799-264">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="8b799-265">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="8b799-265">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="8b799-266">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8b799-266">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="8b799-267">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="8b799-267">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="8b799-268">機能</span><span class="sxs-lookup"><span data-stu-id="8b799-268">Feature</span></span>                 |<span data-ttu-id="8b799-269">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="8b799-269">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="8b799-270">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="8b799-270">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="8b799-271">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="8b799-271">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="8b799-272">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="8b799-272">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="8b799-273">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="8b799-273">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="8b799-274">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="8b799-274">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="8b799-275">ストレージ</span><span class="sxs-lookup"><span data-stu-id="8b799-275">Storage</span></span>                 |<span data-ttu-id="8b799-276">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-276">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8b799-277">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-277">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8b799-278">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-278">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="8b799-279">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-279">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="8b799-280">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-280">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8b799-281">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="8b799-281">1 TB per organization</span></span>           |
|<span data-ttu-id="8b799-282">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="8b799-282">Storage for Teams Files</span></span> |<span data-ttu-id="8b799-283">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8b799-283">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8b799-284">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8b799-284">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8b799-285">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8b799-285">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8b799-286">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8b799-286">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8b799-287">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8b799-287">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8b799-288">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8b799-288">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="8b799-289">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="8b799-289">File upload limit  (per file)</span></span>    |<span data-ttu-id="8b799-290">100 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-290">100 GB</span></span>    |<span data-ttu-id="8b799-291">100 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-291">100 GB</span></span>    |<span data-ttu-id="8b799-292">100 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-292">100 GB</span></span>    |<span data-ttu-id="8b799-293">100 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-293">100 GB</span></span>    |<span data-ttu-id="8b799-294">100 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-294">100 GB</span></span>    |<span data-ttu-id="8b799-295">100 GB</span><span class="sxs-lookup"><span data-stu-id="8b799-295">100 GB</span></span>    |

<span data-ttu-id="8b799-296">チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="8b799-296">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="8b799-297">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b799-297">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="8b799-298">クラス チーム</span><span class="sxs-lookup"><span data-stu-id="8b799-298">Class teams</span></span>

<span data-ttu-id="8b799-299">Microsoft Teams for Education には、教育機関向けの特別なシナリオ (授業教材など) 向けのテンプレートが用意されています。//Microsoft Teams for Education には、教室での授業など、独自の教育シナリオ用に設計されたテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8b799-299">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching.</span></span> <span data-ttu-id="8b799-300">クラスチームなど、チームの種類の詳細については、「[Microsoft Teams で共同作業を行うチームの種類を選択する](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b799-300">More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="8b799-301">クラスチームは、追加のアプリが含まれるテンプレートの種類で、チームメンバーの数に応じた制限があります。</span><span class="sxs-lookup"><span data-stu-id="8b799-301">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="8b799-302">クラスチームを使用するには、[Office 365 Education ライセンス](https://www.microsoft.com/education/products/office)が必要です。</span><span class="sxs-lookup"><span data-stu-id="8b799-302">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="8b799-303">クラスチームの制限を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="8b799-303">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="8b799-304">機能</span><span class="sxs-lookup"><span data-stu-id="8b799-304">Feature</span></span>  |<span data-ttu-id="8b799-305">上限</span><span class="sxs-lookup"><span data-stu-id="8b799-305">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8b799-306">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8b799-306">Number of members in a team</span></span>    | <span data-ttu-id="8b799-307">この記事の「[チームとチャネル](#teams-and-channels)」のセクションを参照してください</span><span class="sxs-lookup"><span data-stu-id="8b799-307">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="8b799-308">クラスチームで課題を使用するメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8b799-308">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="8b799-309">200</span><span class="sxs-lookup"><span data-stu-id="8b799-309">200</span></span>        |
|<span data-ttu-id="8b799-310">クラスチームで OneNote Class Notebook を使用するためのメンバー数</span><span class="sxs-lookup"><span data-stu-id="8b799-310">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="8b799-311">200</span><span class="sxs-lookup"><span data-stu-id="8b799-311">200</span></span>         |

<span data-ttu-id="8b799-312">クラスチームは、200を超えるメンバーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="8b799-312">A class team can support more than 200 members.</span></span> <span data-ttu-id="8b799-313">ただし、チーム内でアサインメントアプリまたはクラスノートブックアプリのいずれかを使用する場合は、メンバー数を上記の上限未満に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b799-313">However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>


## <a name="tags"></a><span data-ttu-id="8b799-314">タグ</span><span class="sxs-lookup"><span data-stu-id="8b799-314">Tags</span></span>

|<span data-ttu-id="8b799-315">機能</span><span class="sxs-lookup"><span data-stu-id="8b799-315">Feature</span></span>  |<span data-ttu-id="8b799-316">上限</span><span class="sxs-lookup"><span data-stu-id="8b799-316">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8b799-317">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="8b799-317">Number of tags per team</span></span>    | <span data-ttu-id="8b799-318">100</span><span class="sxs-lookup"><span data-stu-id="8b799-318">100</span></span>        |
|<span data-ttu-id="8b799-319">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="8b799-319">Number of suggested default tags per team</span></span>    | <span data-ttu-id="8b799-320">25</span><span class="sxs-lookup"><span data-stu-id="8b799-320">25</span></span>        |
|<span data-ttu-id="8b799-321">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8b799-321">Number of team members assign to a tag</span></span>    |<span data-ttu-id="8b799-322">100</span><span class="sxs-lookup"><span data-stu-id="8b799-322">100</span></span>         |
|<span data-ttu-id="8b799-323">ユーザーに割り当てられたるタグ数</span><span class="sxs-lookup"><span data-stu-id="8b799-323">Number of tags assigned to a user</span></span>    |<span data-ttu-id="8b799-324">25</span><span class="sxs-lookup"><span data-stu-id="8b799-324">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="8b799-325">連絡先</span><span class="sxs-lookup"><span data-stu-id="8b799-325">Contacts</span></span>

<span data-ttu-id="8b799-326">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b799-326">Teams uses these contacts:</span></span>

- <span data-ttu-id="8b799-327">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="8b799-327">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="8b799-328">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="8b799-328">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="8b799-329">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8b799-329">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="8b799-330">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b799-330">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="8b799-331">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="8b799-331">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="8b799-332">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="8b799-332">Operating systems</span></span>

<span data-ttu-id="8b799-333">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8b799-333">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
