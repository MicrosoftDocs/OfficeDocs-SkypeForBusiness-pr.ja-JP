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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 236b11242c4f7f609fb5eab0bd772884f9452336
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583656"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="4f53c-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="4f53c-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="4f53c-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="4f53c-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="4f53c-105">Teams and channels</span></span>

|<span data-ttu-id="4f53c-106">機能</span><span class="sxs-lookup"><span data-stu-id="4f53c-106">Feature</span></span>    | <span data-ttu-id="4f53c-107">上限</span><span class="sxs-lookup"><span data-stu-id="4f53c-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="4f53c-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-108">Number of teams a user can create</span></span> | <span data-ttu-id="4f53c-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="4f53c-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="4f53c-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="4f53c-111">1,000</span><span class="sxs-lookup"><span data-stu-id="4f53c-111">1,000</span></span>|
|<span data-ttu-id="4f53c-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-112">Number of members in a team</span></span> | <span data-ttu-id="4f53c-113">10,000</span><span class="sxs-lookup"><span data-stu-id="4f53c-113">10,000</span></span>       |
|<span data-ttu-id="4f53c-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="4f53c-114">Number of owners per team</span></span> | <span data-ttu-id="4f53c-115">100</span><span class="sxs-lookup"><span data-stu-id="4f53c-115">100</span></span>   |
|<span data-ttu-id="4f53c-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="4f53c-117">5</span><span class="sxs-lookup"><span data-stu-id="4f53c-117">5</span></span>     |
|<span data-ttu-id="4f53c-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="4f53c-119">5,000</span><span class="sxs-lookup"><span data-stu-id="4f53c-119">5,000</span></span>       |
|<span data-ttu-id="4f53c-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="4f53c-121">500,000</span><span class="sxs-lookup"><span data-stu-id="4f53c-121">500,000</span></span>   |
|<span data-ttu-id="4f53c-122">Microsoft 365 または Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="4f53c-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="4f53c-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="4f53c-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="4f53c-124">Number of channels per team</span></span>    | <span data-ttu-id="4f53c-125">200 (削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="4f53c-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="4f53c-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="4f53c-126">Number of Private channels per team</span></span>    |<span data-ttu-id="4f53c-127">30</span><span class="sxs-lookup"><span data-stu-id="4f53c-127">30</span></span>|
|<span data-ttu-id="4f53c-128">プライベート チャネルのメンバー数</span><span class="sxs-lookup"><span data-stu-id="4f53c-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="4f53c-129">250 人</span><span class="sxs-lookup"><span data-stu-id="4f53c-129">250</span></span>|
|<span data-ttu-id="4f53c-130">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="4f53c-130">Channel conversation post size</span></span> | <span data-ttu-id="4f53c-131">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4f53c-131">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="4f53c-132"><sup>1</sup> Azure Active Directory のすべてのディレクトリ オブジェクトはこの制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-132"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="4f53c-133">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-133">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="4f53c-134"><sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-134"><sup>2</sup> This limit includes archived teams.</span></span>

<span data-ttu-id="4f53c-135"><sup>3</sup> 削除したチャネルは、30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-135"><sup>3</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="4f53c-136">この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルとしてカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-136">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="4f53c-137">30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限である 200 チャンネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f53c-137">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="4f53c-138"><sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="4f53c-138"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="4f53c-139">Messaging</span><span class="sxs-lookup"><span data-stu-id="4f53c-139">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="4f53c-140">チャット</span><span class="sxs-lookup"><span data-stu-id="4f53c-140">Chat</span></span>

<span data-ttu-id="4f53c-141">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f53c-141">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="4f53c-142">これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。</span><span class="sxs-lookup"><span data-stu-id="4f53c-142">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="4f53c-143">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f53c-143">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="4f53c-144">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f53c-144">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="4f53c-145">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="4f53c-145">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="4f53c-146">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="4f53c-146">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="4f53c-147">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-147">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="4f53c-148">機能</span><span class="sxs-lookup"><span data-stu-id="4f53c-148">Feature</span></span>  | <span data-ttu-id="4f53c-149">上限</span><span class="sxs-lookup"><span data-stu-id="4f53c-149">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="4f53c-150">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4f53c-150">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="4f53c-151">250 人</span><span class="sxs-lookup"><span data-stu-id="4f53c-151">250</span></span><br><br><span data-ttu-id="4f53c-152">**注:** 政府機関用の Teams (GCC、GCC High、DoD) の場合、制限は 100 のままです。</span><span class="sxs-lookup"><span data-stu-id="4f53c-152">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 100.</span></span> <span data-ttu-id="4f53c-153">政府機関のクラウド制限が 100 から 250 に増加したときに、この記事を更新します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-153">We'll update this article when the government cloud limit increases from 100 to 250.</span></span>    |
|<span data-ttu-id="4f53c-154">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-154">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="4f53c-155">20</span><span class="sxs-lookup"><span data-stu-id="4f53c-155">20</span></span> |
|<span data-ttu-id="4f53c-156">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4f53c-156">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="4f53c-157">10</span><span class="sxs-lookup"><span data-stu-id="4f53c-157">10</span></span>     |
|<span data-ttu-id="4f53c-158">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="4f53c-158">Chat size</span></span> | <span data-ttu-id="4f53c-159">投稿ごとに約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4f53c-159">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="4f53c-160"><sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。</span><span class="sxs-lookup"><span data-stu-id="4f53c-160"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span> <span data-ttu-id="4f53c-161">プライベート グループのチャットに 20 を超えるメンバーが含まれている場合は、「配信オプションの設定」 (!) ボタンも削除されます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-161">The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="4f53c-162"><sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-162"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="4f53c-163"><sup>3</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="4f53c-163"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="4f53c-164">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="4f53c-164">Emailing a channel</span></span>

 <span data-ttu-id="4f53c-165">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-165">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="4f53c-166">メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-166">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="4f53c-167">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-167">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="4f53c-168">機能</span><span class="sxs-lookup"><span data-stu-id="4f53c-168">Feature</span></span>  | <span data-ttu-id="4f53c-169">上限</span><span class="sxs-lookup"><span data-stu-id="4f53c-169">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="4f53c-170">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="4f53c-170">Message size<sup>1<sup></span></span> | <span data-ttu-id="4f53c-171">24 KB</span><span class="sxs-lookup"><span data-stu-id="4f53c-171">24 KB</span></span> |
|<span data-ttu-id="4f53c-172">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4f53c-172">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="4f53c-173">20</span><span class="sxs-lookup"><span data-stu-id="4f53c-173">20</span></span>     |
|<span data-ttu-id="4f53c-174">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="4f53c-174">Size of each file attachment</span></span> | <span data-ttu-id="4f53c-175">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="4f53c-175">Less than 10 MB</span></span> |
|<span data-ttu-id="4f53c-176">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4f53c-176">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="4f53c-177">50</span><span class="sxs-lookup"><span data-stu-id="4f53c-177">50</span></span>   |

<span data-ttu-id="4f53c-178"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-178"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="4f53c-179"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-179"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="4f53c-180">詳細については、「[ Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f53c-180">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="4f53c-181">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="4f53c-181">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="4f53c-182">チャネル名</span><span class="sxs-lookup"><span data-stu-id="4f53c-182">Channel names</span></span>

<span data-ttu-id="4f53c-183">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="4f53c-183">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="4f53c-184">文字</span><span class="sxs-lookup"><span data-stu-id="4f53c-184">Characters</span></span>     | <span data-ttu-id="4f53c-185">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="4f53c-185">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="4f53c-186">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="4f53c-186">&#124; ' " , .</span></span>        |
|<span data-ttu-id="4f53c-187">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="4f53c-187">Characters in these ranges</span></span>    | <span data-ttu-id="4f53c-188">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="4f53c-188">0 to 1F</span></span><br><span data-ttu-id="4f53c-189">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="4f53c-189">80 to 9F</span></span>        |
|<span data-ttu-id="4f53c-190">単語</span><span class="sxs-lookup"><span data-stu-id="4f53c-190">Words</span></span>     | <span data-ttu-id="4f53c-191">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="4f53c-191">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="4f53c-192">チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="4f53c-192">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="4f53c-193">会議と通話</span><span class="sxs-lookup"><span data-stu-id="4f53c-193">Meetings and calls</span></span>

|<span data-ttu-id="4f53c-194">機能</span><span class="sxs-lookup"><span data-stu-id="4f53c-194">Feature</span></span>     | <span data-ttu-id="4f53c-195">上限</span><span class="sxs-lookup"><span data-stu-id="4f53c-195">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="4f53c-196">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="4f53c-196">Number of people in a meeting (can chat and call in)</span></span>  |<span data-ttu-id="4f53c-197">300. **表示のみ** では、最大 2 万人の聴取のみの参加者が会議に参加できます。開催者は、高度な通信アドオン SKU のライセンスを持っています。<sup>1</sup> [!INCLUDE [template](includes/preview-feature.md)]</span><span class="sxs-lookup"><span data-stu-id="4f53c-197">300. **View-only** allows for up to 20,000 listen-only participants to join a meeting in which the organizer has a license for the Advanced Communications add-on SKU.<sup>1</sup> [!INCLUDE [template](includes/preview-feature.md)]</span></span> <br><br><span data-ttu-id="4f53c-198">**注:** 政府機関用の Teams (GCC、GCC High、DoD) の場合、制限は 250 のままです。</span><span class="sxs-lookup"><span data-stu-id="4f53c-198">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 250.</span></span> <span data-ttu-id="4f53c-199">政府機関のクラウド制限が 250 から 300 に増加し、会議のオーバーフローがサポートされたら、この記事を更新します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-199">We'll update this article when the government cloud limit increases from 250 to 300 and supports meeting overflow.</span></span>   |
|<span data-ttu-id="4f53c-200">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="4f53c-200">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="4f53c-201">300</span><span class="sxs-lookup"><span data-stu-id="4f53c-201">300</span></span> |
|<span data-ttu-id="4f53c-202">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-202">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="4f53c-203">20</span><span class="sxs-lookup"><span data-stu-id="4f53c-203">20</span></span> |
|<span data-ttu-id="4f53c-204">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="4f53c-204">Max PowerPoint File Size</span></span> | <span data-ttu-id="4f53c-205">2GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-205">2GB</span></span>|
|<span data-ttu-id="4f53c-206">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="4f53c-206">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="4f53c-207">20 日間</span><span class="sxs-lookup"><span data-stu-id="4f53c-207">20 days</span></span> |

<span data-ttu-id="4f53c-208"><sup>1</sup> 表示のみは既定でオンです。</span><span class="sxs-lookup"><span data-stu-id="4f53c-208"><sup>1</sup> View-only is on by default.</span></span> <span data-ttu-id="4f53c-209">PowerShell を使用して、会議のオーバーフローを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-209">You can use PowerShell to disable meeting overflow.</span></span> 
```powershell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```
<span data-ttu-id="4f53c-210">表示のみの参加者は、会議に表示専用の容量がない場合、または設定されたロビー ポリシーまたはオプションに基づいてロビーをバイパスする権限がない場合、会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="4f53c-210">View-only attendees will be unable to join a meeting if there is no longer view-only capacity in the meeting or the attendee doesn't have permission to bypass the Lobby based on set Lobby Policies or Options.</span></span> <span data-ttu-id="4f53c-211">表示のみの参加者は、ネイティブ PPT 共有ファイルを表示できません。</span><span class="sxs-lookup"><span data-stu-id="4f53c-211">View-only participants won't be able to see native PPT share files.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="4f53c-212">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="4f53c-212">Meeting expiration</span></span>

|<span data-ttu-id="4f53c-213">会議の種類</span><span class="sxs-lookup"><span data-stu-id="4f53c-213">Meeting type</span></span>  |<span data-ttu-id="4f53c-214">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="4f53c-214">Meeting expires after this much time</span></span>  |<span data-ttu-id="4f53c-215">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="4f53c-215">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="4f53c-216">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="4f53c-216">Meet now</span></span>     |<span data-ttu-id="4f53c-217">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="4f53c-217">Start time + 8 hours</span></span>         |<span data-ttu-id="4f53c-218">該当なし</span><span class="sxs-lookup"><span data-stu-id="4f53c-218">N/A</span></span>         |
|<span data-ttu-id="4f53c-219">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="4f53c-219">Regular with no end time</span></span>     |<span data-ttu-id="4f53c-220">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="4f53c-220">Start time + 60 days</span></span>         | <span data-ttu-id="4f53c-221">60 日</span><span class="sxs-lookup"><span data-stu-id="4f53c-221">60 days</span></span>        |
|<span data-ttu-id="4f53c-222">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="4f53c-222">Regular with end time</span></span>     |<span data-ttu-id="4f53c-223">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="4f53c-223">End time + 60 days</span></span>         |<span data-ttu-id="4f53c-224">60 日</span><span class="sxs-lookup"><span data-stu-id="4f53c-224">60 days</span></span>         |
|<span data-ttu-id="4f53c-225">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="4f53c-225">Recurring with no end time</span></span>     |<span data-ttu-id="4f53c-226">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="4f53c-226">Start time + 60 days</span></span>         |<span data-ttu-id="4f53c-227">60 日</span><span class="sxs-lookup"><span data-stu-id="4f53c-227">60 days</span></span>         |
|<span data-ttu-id="4f53c-228">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="4f53c-228">Recurring with end time</span></span>     |<span data-ttu-id="4f53c-229">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="4f53c-229">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="4f53c-230">60 日</span><span class="sxs-lookup"><span data-stu-id="4f53c-230">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="4f53c-231">Microsoft Teams 会議には、24 時間の時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="4f53c-231">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="4f53c-232">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="4f53c-232">Teams live events</span></span>

|<span data-ttu-id="4f53c-233">機能</span><span class="sxs-lookup"><span data-stu-id="4f53c-233">Feature</span></span>     | <span data-ttu-id="4f53c-234">上限</span><span class="sxs-lookup"><span data-stu-id="4f53c-234">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="4f53c-235">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="4f53c-235">Audience size</span></span> | <span data-ttu-id="4f53c-236">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="4f53c-236">10,000 attendees</span></span> |
|<span data-ttu-id="4f53c-237">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="4f53c-237">Duration of event</span></span> | <span data-ttu-id="4f53c-238">4 時間</span><span class="sxs-lookup"><span data-stu-id="4f53c-238">4 hours</span></span> |
|<span data-ttu-id="4f53c-239">Microsoft 365 または Office 365 組織で実行されている同時ライブ イベント <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4f53c-239">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="4f53c-240">15</span><span class="sxs-lookup"><span data-stu-id="4f53c-240">15</span></span> |

<span data-ttu-id="4f53c-241"><sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。</span><span class="sxs-lookup"><span data-stu-id="4f53c-241"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="4f53c-242">プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-242">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="4f53c-243">16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-243">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="4f53c-244">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="4f53c-244">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f53c-245">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="4f53c-245">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="4f53c-246">お客様が急速に変化するコミュニケーションのニーズに対応できるように、Microsoft 365 ライブ イベントは、2020 年 10 月 1 日まで、Teams でホストされるライブ イベントの既定の上限を一時的に引き上げます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-246">To help customers meet rapidly changing communication needs, Microsoft 365 live events will temporarily raise default limits until October 1, 2020, for live events hosted in Teams.</span></span> <span data-ttu-id="4f53c-247">次の上限が適用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="4f53c-247">The following increases are being rolled out:</span></span>
>
> - <span data-ttu-id="4f53c-248">参加者の制限: イベントは最大 20,000 人の参加者をサポートできます</span><span class="sxs-lookup"><span data-stu-id="4f53c-248">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="4f53c-249">同時イベント: テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="4f53c-249">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="4f53c-250">イベントの時間: イベントの長さが 1 回のブロードキャストにつき 16 時間に延長されました</span><span class="sxs-lookup"><span data-stu-id="4f53c-250">Event duration: event length has been increased to 16 hours per broadcast</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="4f53c-251">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="4f53c-251">Presence in Outlook</span></span>

<span data-ttu-id="4f53c-252">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4f53c-252">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="4f53c-253">Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f53c-253">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="4f53c-254">ストレージ</span><span class="sxs-lookup"><span data-stu-id="4f53c-254">Storage</span></span>

<span data-ttu-id="4f53c-p114">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-p114">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="4f53c-257">各 [プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels) には、独自の SharePoint サイト コレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="4f53c-257">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="4f53c-258">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f53c-258">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="4f53c-259">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="4f53c-259">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="4f53c-260">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-260">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="4f53c-261">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="4f53c-261">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="4f53c-262">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-262">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="4f53c-263">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-263">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="4f53c-264">機能</span><span class="sxs-lookup"><span data-stu-id="4f53c-264">Feature</span></span>                 |<span data-ttu-id="4f53c-265">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="4f53c-265">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="4f53c-266">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="4f53c-266">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="4f53c-267">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="4f53c-267">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="4f53c-268">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="4f53c-268">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="4f53c-269">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="4f53c-269">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="4f53c-270">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="4f53c-270">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="4f53c-271">ストレージ</span><span class="sxs-lookup"><span data-stu-id="4f53c-271">Storage</span></span>                 |<span data-ttu-id="4f53c-272">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-272">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="4f53c-273">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-273">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="4f53c-274">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-274">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="4f53c-275">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-275">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="4f53c-276">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-276">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="4f53c-277">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="4f53c-277">1 TB per organization</span></span>           |
|<span data-ttu-id="4f53c-278">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="4f53c-278">Storage for Teams Files</span></span> |<span data-ttu-id="4f53c-279">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="4f53c-279">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="4f53c-280">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="4f53c-280">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="4f53c-281">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="4f53c-281">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="4f53c-282">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="4f53c-282">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="4f53c-283">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="4f53c-283">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="4f53c-284">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="4f53c-284">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="4f53c-285">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="4f53c-285">File upload limit  (per file)</span></span>    |<span data-ttu-id="4f53c-286">15 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-286">15 GB</span></span>    |<span data-ttu-id="4f53c-287">15 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-287">15 GB</span></span>    |<span data-ttu-id="4f53c-288">15 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-288">15 GB</span></span>    |<span data-ttu-id="4f53c-289">15 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-289">15 GB</span></span>    |<span data-ttu-id="4f53c-290">15 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-290">15 GB</span></span>    |<span data-ttu-id="4f53c-291">15 GB</span><span class="sxs-lookup"><span data-stu-id="4f53c-291">15 GB</span></span>    |

<span data-ttu-id="4f53c-292">チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-292">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="4f53c-293">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f53c-293">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="tags"></a><span data-ttu-id="4f53c-294">タグ</span><span class="sxs-lookup"><span data-stu-id="4f53c-294">Tags</span></span>

|<span data-ttu-id="4f53c-295">機能</span><span class="sxs-lookup"><span data-stu-id="4f53c-295">Feature</span></span>  |<span data-ttu-id="4f53c-296">上限</span><span class="sxs-lookup"><span data-stu-id="4f53c-296">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="4f53c-297">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="4f53c-297">Number of tags per team</span></span>    | <span data-ttu-id="4f53c-298">100</span><span class="sxs-lookup"><span data-stu-id="4f53c-298">100</span></span>        |
|<span data-ttu-id="4f53c-299">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="4f53c-299">Number of suggested default tags per team</span></span>    | <span data-ttu-id="4f53c-300">25</span><span class="sxs-lookup"><span data-stu-id="4f53c-300">25</span></span>        |
|<span data-ttu-id="4f53c-301">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="4f53c-301">Number of team members assign to a tag</span></span>    |<span data-ttu-id="4f53c-302">100</span><span class="sxs-lookup"><span data-stu-id="4f53c-302">100</span></span>         |
|<span data-ttu-id="4f53c-303">ユーザーに割り当てられたるタグ数</span><span class="sxs-lookup"><span data-stu-id="4f53c-303">Number of tags assigned to a user</span></span>    |<span data-ttu-id="4f53c-304">25</span><span class="sxs-lookup"><span data-stu-id="4f53c-304">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="4f53c-305">連絡先</span><span class="sxs-lookup"><span data-stu-id="4f53c-305">Contacts</span></span>

<span data-ttu-id="4f53c-306">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f53c-306">Teams uses these contacts:</span></span>

- <span data-ttu-id="4f53c-307">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="4f53c-307">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="4f53c-308">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="4f53c-308">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="4f53c-309">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-309">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="4f53c-310">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f53c-310">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="4f53c-311">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="4f53c-311">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="4f53c-312">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="4f53c-312">Operating systems</span></span>

<span data-ttu-id="4f53c-313">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f53c-313">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
