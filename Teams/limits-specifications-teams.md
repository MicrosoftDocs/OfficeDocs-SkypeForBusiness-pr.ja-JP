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
ms.openlocfilehash: fadc9fbeb82b4cb808b9beb698c0726c22f78c44
ms.sourcegitcommit: 762e303509940f830c304e00a98b05796bf5537f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333267"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="42f5e-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="42f5e-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="42f5e-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="42f5e-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="42f5e-105">Teams and channels</span></span>

|<span data-ttu-id="42f5e-106">機能</span><span class="sxs-lookup"><span data-stu-id="42f5e-106">Feature</span></span>    | <span data-ttu-id="42f5e-107">上限</span><span class="sxs-lookup"><span data-stu-id="42f5e-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="42f5e-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-108">Number of teams a user can create</span></span> | <span data-ttu-id="42f5e-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="42f5e-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="42f5e-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="42f5e-111">1,000</span><span class="sxs-lookup"><span data-stu-id="42f5e-111">1,000</span></span>|
|<span data-ttu-id="42f5e-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-112">Number of members in a team</span></span> | <span data-ttu-id="42f5e-113">10,000</span><span class="sxs-lookup"><span data-stu-id="42f5e-113">10,000</span></span>       |
|<span data-ttu-id="42f5e-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="42f5e-114">Number of owners per team</span></span> | <span data-ttu-id="42f5e-115">100</span><span class="sxs-lookup"><span data-stu-id="42f5e-115">100</span></span>   |
|<span data-ttu-id="42f5e-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="42f5e-117">5</span><span class="sxs-lookup"><span data-stu-id="42f5e-117">5</span></span>     |
|<span data-ttu-id="42f5e-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="42f5e-119">5,000</span><span class="sxs-lookup"><span data-stu-id="42f5e-119">5,000</span></span>       |
|<span data-ttu-id="42f5e-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="42f5e-121">500,000</span><span class="sxs-lookup"><span data-stu-id="42f5e-121">500,000</span></span>   |
|<span data-ttu-id="42f5e-122">Microsoft 365 または Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="42f5e-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="42f5e-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="42f5e-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="42f5e-124">Number of channels per team</span></span>    | <span data-ttu-id="42f5e-125">200 (削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="42f5e-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="42f5e-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="42f5e-126">Number of Private channels per team</span></span>    |<span data-ttu-id="42f5e-127">30</span><span class="sxs-lookup"><span data-stu-id="42f5e-127">30</span></span>|
|<span data-ttu-id="42f5e-128">プライベート チャネルのメンバー数</span><span class="sxs-lookup"><span data-stu-id="42f5e-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="42f5e-129">250 人</span><span class="sxs-lookup"><span data-stu-id="42f5e-129">250</span></span>|
|<span data-ttu-id="42f5e-130">チームに変換できる Office 365 グループのメンバーの最大数</span><span class="sxs-lookup"><span data-stu-id="42f5e-130">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="42f5e-131">10,000</span><span class="sxs-lookup"><span data-stu-id="42f5e-131">10,000</span></span>|
|<span data-ttu-id="42f5e-132">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="42f5e-132">Channel conversation post size</span></span> | <span data-ttu-id="42f5e-133">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="42f5e-133">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="42f5e-134"><sup>1</sup> Azure Active Directory のすべてのディレクトリ オブジェクトはこの制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-134"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="42f5e-135">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-135">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="42f5e-136"><sup>2</sup> この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-136"><sup>2</sup> This limit includes archived teams.</span></span>

<span data-ttu-id="42f5e-137"><sup>3</sup> 削除したチャネルは、30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-137"><sup>3</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="42f5e-138">この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルとしてカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-138">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="42f5e-139">30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限である 200 チャンネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="42f5e-139">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="42f5e-140"><sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="42f5e-140"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="42f5e-141">Messaging</span><span class="sxs-lookup"><span data-stu-id="42f5e-141">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="42f5e-142">チャット</span><span class="sxs-lookup"><span data-stu-id="42f5e-142">Chat</span></span>

<span data-ttu-id="42f5e-143">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f5e-143">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="42f5e-144">これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。</span><span class="sxs-lookup"><span data-stu-id="42f5e-144">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="42f5e-145">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="42f5e-145">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="42f5e-146">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="42f5e-146">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="42f5e-147">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="42f5e-147">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="42f5e-148">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="42f5e-148">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="42f5e-149">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-149">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="42f5e-150">機能</span><span class="sxs-lookup"><span data-stu-id="42f5e-150">Feature</span></span>  | <span data-ttu-id="42f5e-151">上限</span><span class="sxs-lookup"><span data-stu-id="42f5e-151">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="42f5e-152">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="42f5e-152">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="42f5e-153">250 人</span><span class="sxs-lookup"><span data-stu-id="42f5e-153">250</span></span> |
|<span data-ttu-id="42f5e-154">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-154">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="42f5e-155">20</span><span class="sxs-lookup"><span data-stu-id="42f5e-155">20</span></span> |
|<span data-ttu-id="42f5e-156">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="42f5e-156">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="42f5e-157">10</span><span class="sxs-lookup"><span data-stu-id="42f5e-157">10</span></span>     |
|<span data-ttu-id="42f5e-158">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="42f5e-158">Chat size</span></span> | <span data-ttu-id="42f5e-159">投稿ごとに約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="42f5e-159">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="42f5e-160"><sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。</span><span class="sxs-lookup"><span data-stu-id="42f5e-160"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span> <span data-ttu-id="42f5e-161">プライベート グループのチャットに 20 を超えるメンバーが含まれている場合は、「配信オプションの設定」 (!) ボタンも削除されます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-161">The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="42f5e-162"><sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-162"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="42f5e-163"><sup>3</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="42f5e-163"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="42f5e-164">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="42f5e-164">Emailing a channel</span></span>

 <span data-ttu-id="42f5e-165">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-165">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="42f5e-166">メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-166">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="42f5e-167">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-167">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="42f5e-168">機能</span><span class="sxs-lookup"><span data-stu-id="42f5e-168">Feature</span></span>  | <span data-ttu-id="42f5e-169">上限</span><span class="sxs-lookup"><span data-stu-id="42f5e-169">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="42f5e-170">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="42f5e-170">Message size<sup>1<sup></span></span> | <span data-ttu-id="42f5e-171">24 KB</span><span class="sxs-lookup"><span data-stu-id="42f5e-171">24 KB</span></span> |
|<span data-ttu-id="42f5e-172">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="42f5e-172">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="42f5e-173">20</span><span class="sxs-lookup"><span data-stu-id="42f5e-173">20</span></span>     |
|<span data-ttu-id="42f5e-174">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="42f5e-174">Size of each file attachment</span></span> | <span data-ttu-id="42f5e-175">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="42f5e-175">Less than 10 MB</span></span> |
|<span data-ttu-id="42f5e-176">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="42f5e-176">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="42f5e-177">50</span><span class="sxs-lookup"><span data-stu-id="42f5e-177">50</span></span>   |

<span data-ttu-id="42f5e-178"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-178"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="42f5e-179"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-179"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="42f5e-180">詳細については、「[ Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="42f5e-180">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="42f5e-181">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Microsoft 365 および Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="42f5e-181">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="42f5e-182">チャネル名</span><span class="sxs-lookup"><span data-stu-id="42f5e-182">Channel names</span></span>

<span data-ttu-id="42f5e-183">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="42f5e-183">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="42f5e-184">文字</span><span class="sxs-lookup"><span data-stu-id="42f5e-184">Characters</span></span>     | <span data-ttu-id="42f5e-185">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="42f5e-185">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="42f5e-186">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="42f5e-186">&#124; ' " , .</span></span>        |
|<span data-ttu-id="42f5e-187">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="42f5e-187">Characters in these ranges</span></span>    | <span data-ttu-id="42f5e-188">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="42f5e-188">0 to 1F</span></span><br><span data-ttu-id="42f5e-189">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="42f5e-189">80 to 9F</span></span>        |
|<span data-ttu-id="42f5e-190">単語</span><span class="sxs-lookup"><span data-stu-id="42f5e-190">Words</span></span>     | <span data-ttu-id="42f5e-191">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="42f5e-191">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="42f5e-192">チャンネル名は、アンダースコア (_) またはピリオド (.) で開始したり、ピリオド (.) で終了したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="42f5e-192">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="42f5e-193">会議と通話</span><span class="sxs-lookup"><span data-stu-id="42f5e-193">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42f5e-194">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="42f5e-194">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="42f5e-195">**お客様をサポートするために、2021 年 1 月 1 日まで、Teams、Stream、Yammer でホストされるライブイベントの一時的な制限の引き上げを延長します。**</span><span class="sxs-lookup"><span data-stu-id="42f5e-195">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for live events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="42f5e-196">イベントごとに最大 2 万人の参加者</span><span class="sxs-lookup"><span data-stu-id="42f5e-196">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="42f5e-197">Teams テナントごとに最大 50 の同時イベント</span><span class="sxs-lookup"><span data-stu-id="42f5e-197">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="42f5e-198">ブロードキャストあたり最大 16 時間</span><span class="sxs-lookup"><span data-stu-id="42f5e-198">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="42f5e-199">さらに、Microsoft 365 支援プログラムを通じて、最大 10 万人が参加するライブイベントを計画できます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-199">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program.</span></span> <span data-ttu-id="42f5e-200">チームは各要求を評価し、お客様と協力して利用可能なオプションを決定します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-200">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="42f5e-201">[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="42f5e-201">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="42f5e-202">**2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、[Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="42f5e-202">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>


|<span data-ttu-id="42f5e-203">機能</span><span class="sxs-lookup"><span data-stu-id="42f5e-203">Feature</span></span>     | <span data-ttu-id="42f5e-204">上限</span><span class="sxs-lookup"><span data-stu-id="42f5e-204">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="42f5e-205">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="42f5e-205">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="42f5e-206">300</span><span class="sxs-lookup"><span data-stu-id="42f5e-206">300</span></span> |
|<span data-ttu-id="42f5e-207">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-207">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="42f5e-208">20</span><span class="sxs-lookup"><span data-stu-id="42f5e-208">20</span></span> |
|<span data-ttu-id="42f5e-209">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="42f5e-209">Max PowerPoint File Size</span></span> | <span data-ttu-id="42f5e-210">2GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-210">2GB</span></span>|
|<span data-ttu-id="42f5e-211">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="42f5e-211">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="42f5e-212">20 日間</span><span class="sxs-lookup"><span data-stu-id="42f5e-212">20 days</span></span> |

>[!Note]
> <span data-ttu-id="42f5e-213">Microsoft Stream の使用から [会議の記録用の OneDrive for Business および SharePoint ](tmr-meeting-recording-change.md)への変更は段階的なアプローチになります。</span><span class="sxs-lookup"><span data-stu-id="42f5e-213">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="42f5e-214">リリース時には、この機能にオプトインできるようになります。Stream を使い続けるには、11 月にオプトアウトする必要があります。また、2021 年初頭には、すべてのお客様に、新しい会議の記録に OneDrive と SharePoint を使用するように要請する予定です。</span><span class="sxs-lookup"><span data-stu-id="42f5e-214">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="42f5e-215">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="42f5e-215">Meeting expiration</span></span>

|<span data-ttu-id="42f5e-216">会議の種類</span><span class="sxs-lookup"><span data-stu-id="42f5e-216">Meeting type</span></span>  |<span data-ttu-id="42f5e-217">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="42f5e-217">Meeting expires after this much time</span></span>  |<span data-ttu-id="42f5e-218">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="42f5e-218">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="42f5e-219">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="42f5e-219">Meet now</span></span>     |<span data-ttu-id="42f5e-220">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="42f5e-220">Start time + 8 hours</span></span>         |<span data-ttu-id="42f5e-221">該当なし</span><span class="sxs-lookup"><span data-stu-id="42f5e-221">N/A</span></span>         |
|<span data-ttu-id="42f5e-222">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="42f5e-222">Regular with no end time</span></span>     |<span data-ttu-id="42f5e-223">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="42f5e-223">Start time + 60 days</span></span>         | <span data-ttu-id="42f5e-224">60 日</span><span class="sxs-lookup"><span data-stu-id="42f5e-224">60 days</span></span>        |
|<span data-ttu-id="42f5e-225">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="42f5e-225">Regular with end time</span></span>     |<span data-ttu-id="42f5e-226">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="42f5e-226">End time + 60 days</span></span>         |<span data-ttu-id="42f5e-227">60 日</span><span class="sxs-lookup"><span data-stu-id="42f5e-227">60 days</span></span>         |
|<span data-ttu-id="42f5e-228">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="42f5e-228">Recurring with no end time</span></span>     |<span data-ttu-id="42f5e-229">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="42f5e-229">Start time + 60 days</span></span>         |<span data-ttu-id="42f5e-230">60 日</span><span class="sxs-lookup"><span data-stu-id="42f5e-230">60 days</span></span>         |
|<span data-ttu-id="42f5e-231">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="42f5e-231">Recurring with end time</span></span>     |<span data-ttu-id="42f5e-232">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="42f5e-232">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="42f5e-233">60 日</span><span class="sxs-lookup"><span data-stu-id="42f5e-233">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="42f5e-234">Microsoft Teams 会議には、24 時間の時間制限があります。</span><span class="sxs-lookup"><span data-stu-id="42f5e-234">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="42f5e-235">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="42f5e-235">Teams live events</span></span>

|<span data-ttu-id="42f5e-236">機能</span><span class="sxs-lookup"><span data-stu-id="42f5e-236">Feature</span></span>     | <span data-ttu-id="42f5e-237">上限</span><span class="sxs-lookup"><span data-stu-id="42f5e-237">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="42f5e-238">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="42f5e-238">Audience size</span></span> | <span data-ttu-id="42f5e-239">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="42f5e-239">10,000 attendees</span></span> |
|<span data-ttu-id="42f5e-240">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="42f5e-240">Duration of event</span></span> | <span data-ttu-id="42f5e-241">4 時間</span><span class="sxs-lookup"><span data-stu-id="42f5e-241">4 hours</span></span> |
|<span data-ttu-id="42f5e-242">Microsoft 365 または Office 365 組織で実行されている同時ライブ イベント <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="42f5e-242">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="42f5e-243">15</span><span class="sxs-lookup"><span data-stu-id="42f5e-243">15</span></span> |

<span data-ttu-id="42f5e-244"><sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。</span><span class="sxs-lookup"><span data-stu-id="42f5e-244"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="42f5e-245">プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-245">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="42f5e-246">16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-246">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="42f5e-247">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="42f5e-247">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42f5e-248">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="42f5e-248">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="42f5e-249">お客様が急速に変化するコミュニケーションのニーズに対応できるように、Teams、Stream、Yammer でホストされるライブイベントの既定の上限を 2021 年 1 月 1 日まで一時的に引き上げます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-249">To help customers meet rapidly changing communication needs, we will temporarily raise default limits until January 1, 2021, for live events hosted in Teams, Stream, and Yammer.</span></span>
>
> - <span data-ttu-id="42f5e-250">参加者の制限: イベントは最大 20,000 人の参加者をサポートできます</span><span class="sxs-lookup"><span data-stu-id="42f5e-250">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="42f5e-251">同時イベント: テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="42f5e-251">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="42f5e-252">イベントの時間: イベントの長さが 1 回のブロードキャストにつき 16 時間に延長されました</span><span class="sxs-lookup"><span data-stu-id="42f5e-252">Event duration: event length has been increased to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="42f5e-253">さらに、最大 10 万人の参加者がいるライブイベントを、MIcrosoft のライブイベント支援プログラムを通じて計画できます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-253">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft live events assistance program.</span></span> <span data-ttu-id="42f5e-254">[詳細情報を参照してください](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="42f5e-254">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="42f5e-255">**2021 年 1 月 1 日以降、これらの制限の引き上げが必要なお客様は、[Advanced Communications](teams-add-on-licensing/advanced-communications.md) アドオンを購入する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="42f5e-255">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="42f5e-256">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="42f5e-256">Presence in Outlook</span></span>

<span data-ttu-id="42f5e-257">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="42f5e-257">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="42f5e-258">Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f5e-258">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="42f5e-259">ストレージ</span><span class="sxs-lookup"><span data-stu-id="42f5e-259">Storage</span></span>

<span data-ttu-id="42f5e-p112">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-p112">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="42f5e-262">各 [プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels) には、独自の SharePoint サイト コレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="42f5e-262">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="42f5e-263">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="42f5e-263">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="42f5e-264">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="42f5e-264">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="42f5e-265">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-265">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="42f5e-266">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="42f5e-266">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="42f5e-267">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-267">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="42f5e-268">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-268">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="42f5e-269">機能</span><span class="sxs-lookup"><span data-stu-id="42f5e-269">Feature</span></span>                 |<span data-ttu-id="42f5e-270">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="42f5e-270">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="42f5e-271">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="42f5e-271">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="42f5e-272">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="42f5e-272">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="42f5e-273">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="42f5e-273">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="42f5e-274">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="42f5e-274">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="42f5e-275">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="42f5e-275">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="42f5e-276">ストレージ</span><span class="sxs-lookup"><span data-stu-id="42f5e-276">Storage</span></span>                 |<span data-ttu-id="42f5e-277">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-277">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="42f5e-278">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-278">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="42f5e-279">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-279">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="42f5e-280">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-280">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="42f5e-281">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-281">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="42f5e-282">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="42f5e-282">1 TB per organization</span></span>           |
|<span data-ttu-id="42f5e-283">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="42f5e-283">Storage for Teams Files</span></span> |<span data-ttu-id="42f5e-284">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="42f5e-284">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="42f5e-285">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="42f5e-285">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="42f5e-286">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="42f5e-286">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="42f5e-287">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="42f5e-287">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="42f5e-288">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="42f5e-288">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="42f5e-289">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="42f5e-289">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="42f5e-290">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="42f5e-290">File upload limit  (per file)</span></span>    |<span data-ttu-id="42f5e-291">100 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-291">100 GB</span></span>    |<span data-ttu-id="42f5e-292">100 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-292">100 GB</span></span>    |<span data-ttu-id="42f5e-293">100 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-293">100 GB</span></span>    |<span data-ttu-id="42f5e-294">100 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-294">100 GB</span></span>    |<span data-ttu-id="42f5e-295">100 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-295">100 GB</span></span>    |<span data-ttu-id="42f5e-296">100 GB</span><span class="sxs-lookup"><span data-stu-id="42f5e-296">100 GB</span></span>    |

<span data-ttu-id="42f5e-297">チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-297">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="42f5e-298">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f5e-298">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="42f5e-299">クラス チーム</span><span class="sxs-lookup"><span data-stu-id="42f5e-299">Class teams</span></span>

<span data-ttu-id="42f5e-300">Microsoft Teams for Education には、教育機関向けの特別なシナリオ (授業教材など) 向けのテンプレートが用意されています。//Microsoft Teams for Education には、教室での授業など、独自の教育シナリオ用に設計されたテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="42f5e-300">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching.</span></span> <span data-ttu-id="42f5e-301">クラスチームなど、チームの種類の詳細については、「[Microsoft Teams で共同作業を行うチームの種類を選択する](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f5e-301">More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="42f5e-302">クラスチームは、追加のアプリが含まれるテンプレートの種類で、チームメンバーの数に応じた制限があります。</span><span class="sxs-lookup"><span data-stu-id="42f5e-302">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="42f5e-303">クラスチームを使用するには、[Office 365 Education ライセンス](https://www.microsoft.com/education/products/office)が必要です。</span><span class="sxs-lookup"><span data-stu-id="42f5e-303">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="42f5e-304">クラスチームの制限を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-304">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="42f5e-305">機能</span><span class="sxs-lookup"><span data-stu-id="42f5e-305">Feature</span></span>  |<span data-ttu-id="42f5e-306">上限</span><span class="sxs-lookup"><span data-stu-id="42f5e-306">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="42f5e-307">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-307">Number of members in a team</span></span>    | <span data-ttu-id="42f5e-308">この記事の「[チームとチャネル](#teams-and-channels)」のセクションを参照してください</span><span class="sxs-lookup"><span data-stu-id="42f5e-308">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="42f5e-309">クラスチームで課題を使用するメンバーの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-309">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="42f5e-310">200</span><span class="sxs-lookup"><span data-stu-id="42f5e-310">200</span></span>        |
|<span data-ttu-id="42f5e-311">クラスチームで OneNote Class Notebook を使用するためのメンバー数</span><span class="sxs-lookup"><span data-stu-id="42f5e-311">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="42f5e-312">200</span><span class="sxs-lookup"><span data-stu-id="42f5e-312">200</span></span>         |

<span data-ttu-id="42f5e-313">クラスチームは、200を超えるメンバーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-313">A class team can support more than 200 members.</span></span> <span data-ttu-id="42f5e-314">ただし、チーム内でアサインメントアプリまたはクラスノートブックアプリのいずれかを使用する場合は、メンバー数を上記の上限未満に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f5e-314">However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>


## <a name="tags"></a><span data-ttu-id="42f5e-315">タグ</span><span class="sxs-lookup"><span data-stu-id="42f5e-315">Tags</span></span>

|<span data-ttu-id="42f5e-316">機能</span><span class="sxs-lookup"><span data-stu-id="42f5e-316">Feature</span></span>  |<span data-ttu-id="42f5e-317">上限</span><span class="sxs-lookup"><span data-stu-id="42f5e-317">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="42f5e-318">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="42f5e-318">Number of tags per team</span></span>    | <span data-ttu-id="42f5e-319">100</span><span class="sxs-lookup"><span data-stu-id="42f5e-319">100</span></span>        |
|<span data-ttu-id="42f5e-320">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="42f5e-320">Number of suggested default tags per team</span></span>    | <span data-ttu-id="42f5e-321">25</span><span class="sxs-lookup"><span data-stu-id="42f5e-321">25</span></span>        |
|<span data-ttu-id="42f5e-322">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="42f5e-322">Number of team members assign to a tag</span></span>    |<span data-ttu-id="42f5e-323">100</span><span class="sxs-lookup"><span data-stu-id="42f5e-323">100</span></span>         |
|<span data-ttu-id="42f5e-324">ユーザーに割り当てられたるタグ数</span><span class="sxs-lookup"><span data-stu-id="42f5e-324">Number of tags assigned to a user</span></span>    |<span data-ttu-id="42f5e-325">25</span><span class="sxs-lookup"><span data-stu-id="42f5e-325">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="42f5e-326">連絡先</span><span class="sxs-lookup"><span data-stu-id="42f5e-326">Contacts</span></span>

<span data-ttu-id="42f5e-327">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="42f5e-327">Teams uses these contacts:</span></span>

- <span data-ttu-id="42f5e-328">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="42f5e-328">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="42f5e-329">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="42f5e-329">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="42f5e-330">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-330">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="42f5e-331">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="42f5e-331">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="42f5e-332">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="42f5e-332">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="42f5e-333">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="42f5e-333">Operating systems</span></span>

<span data-ttu-id="42f5e-334">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="42f5e-334">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
