---
title: Microsoft Teams の制限事項と仕様
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 28a77271c66dc473dfb774db2c02ca80bc842587
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "43950972"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="fa19a-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="fa19a-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="fa19a-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa19a-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="fa19a-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="fa19a-105">Teams and channels</span></span>

|<span data-ttu-id="fa19a-106">機能</span><span class="sxs-lookup"><span data-stu-id="fa19a-106">Feature</span></span>    | <span data-ttu-id="fa19a-107">上限</span><span class="sxs-lookup"><span data-stu-id="fa19a-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="fa19a-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-108">Number of teams a user can create</span></span> | <span data-ttu-id="fa19a-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="fa19a-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="fa19a-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="fa19a-111">1,000</span><span class="sxs-lookup"><span data-stu-id="fa19a-111">1,000</span></span>|
|<span data-ttu-id="fa19a-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-112">Number of members in a team</span></span> | <span data-ttu-id="fa19a-113">5,000</span><span class="sxs-lookup"><span data-stu-id="fa19a-113">5,000</span></span>       |
|<span data-ttu-id="fa19a-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="fa19a-114">Number of owners per team</span></span> | <span data-ttu-id="fa19a-115">100</span><span class="sxs-lookup"><span data-stu-id="fa19a-115">100</span></span>   |
|<span data-ttu-id="fa19a-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="fa19a-117">5</span><span class="sxs-lookup"><span data-stu-id="fa19a-117">5</span></span>     |
|<span data-ttu-id="fa19a-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="fa19a-119">5,000</span><span class="sxs-lookup"><span data-stu-id="fa19a-119">5,000</span></span>       |
|<span data-ttu-id="fa19a-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="fa19a-121">500,000</span><span class="sxs-lookup"><span data-stu-id="fa19a-121">500,000</span></span>   |
|<span data-ttu-id="fa19a-122">Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-122">Number of teams an Office 365 organization can have</span></span>    | <span data-ttu-id="fa19a-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="fa19a-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="fa19a-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="fa19a-124">Number of channels per team</span></span>    | <span data-ttu-id="fa19a-125">200 (削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="fa19a-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="fa19a-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="fa19a-126">Number of Private channels per team</span></span>    |<span data-ttu-id="fa19a-127">30</span><span class="sxs-lookup"><span data-stu-id="fa19a-127">30</span></span>|
|<span data-ttu-id="fa19a-128">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="fa19a-128">Channel conversation post size</span></span> | <span data-ttu-id="fa19a-129">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="fa19a-129">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="fa19a-130">&sup1; Azure Active Directory の任意のディレクトリ オブジェクトは、この制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-130">&sup1; Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="fa19a-131">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-131">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="fa19a-132">&sup2; この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-132">&sup2; This limit includes archived teams.</span></span>

<span data-ttu-id="fa19a-133">&sup3; 削除したチャネルは、30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-133">&sup3; Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="fa19a-134">この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルとしてカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-134">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="fa19a-135">30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限である 200 チャンネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="fa19a-135">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="fa19a-136"><sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="fa19a-136"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="fa19a-137">Messaging</span><span class="sxs-lookup"><span data-stu-id="fa19a-137">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="fa19a-138">チャット</span><span class="sxs-lookup"><span data-stu-id="fa19a-138">Chat</span></span>

<span data-ttu-id="fa19a-139">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa19a-139">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="fa19a-140">これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。</span><span class="sxs-lookup"><span data-stu-id="fa19a-140">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="fa19a-141">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa19a-141">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="fa19a-142">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa19a-142">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="fa19a-143">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="fa19a-143">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="fa19a-144">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="fa19a-144">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="fa19a-145">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-145">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="fa19a-146">機能</span><span class="sxs-lookup"><span data-stu-id="fa19a-146">Feature</span></span>  | <span data-ttu-id="fa19a-147">上限</span><span class="sxs-lookup"><span data-stu-id="fa19a-147">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="fa19a-148">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fa19a-148">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="fa19a-149">100</span><span class="sxs-lookup"><span data-stu-id="fa19a-149">100</span></span>    |
|<span data-ttu-id="fa19a-150">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-150">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="fa19a-151">20</span><span class="sxs-lookup"><span data-stu-id="fa19a-151">20</span></span> |
|<span data-ttu-id="fa19a-152">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fa19a-152">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="fa19a-153">10</span><span class="sxs-lookup"><span data-stu-id="fa19a-153">10</span></span>     |
|<span data-ttu-id="fa19a-154">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="fa19a-154">Chat size</span></span> | <span data-ttu-id="fa19a-155">投稿ごとに約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="fa19a-155">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="fa19a-156"><sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。</span><span class="sxs-lookup"><span data-stu-id="fa19a-156"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="fa19a-157"><sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-157"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="fa19a-158"><sup>3</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="fa19a-158"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="fa19a-159">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="fa19a-159">Emailing a channel</span></span>

 <span data-ttu-id="fa19a-160">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa19a-160">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="fa19a-161">メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-161">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="fa19a-162">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fa19a-162">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="fa19a-163">機能</span><span class="sxs-lookup"><span data-stu-id="fa19a-163">Feature</span></span>  | <span data-ttu-id="fa19a-164">上限</span><span class="sxs-lookup"><span data-stu-id="fa19a-164">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="fa19a-165">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="fa19a-165">Message size<sup>1<sup></span></span> | <span data-ttu-id="fa19a-166">24 KB</span><span class="sxs-lookup"><span data-stu-id="fa19a-166">24 KB</span></span> |
|<span data-ttu-id="fa19a-167">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fa19a-167">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="fa19a-168">20</span><span class="sxs-lookup"><span data-stu-id="fa19a-168">20</span></span>     |
|<span data-ttu-id="fa19a-169">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="fa19a-169">Size of each file attachment</span></span> | <span data-ttu-id="fa19a-170">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="fa19a-170">Less than 10 MB</span></span> |
|<span data-ttu-id="fa19a-171">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fa19a-171">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="fa19a-172">50</span><span class="sxs-lookup"><span data-stu-id="fa19a-172">50</span></span>   |

<span data-ttu-id="fa19a-173"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-173"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="fa19a-174"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-174"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="fa19a-175">詳細については、「[ Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa19a-175">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="fa19a-176">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="fa19a-176">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="fa19a-177">チャネル名</span><span class="sxs-lookup"><span data-stu-id="fa19a-177">Channel names</span></span>

<span data-ttu-id="fa19a-178">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa19a-178">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="fa19a-179">文字</span><span class="sxs-lookup"><span data-stu-id="fa19a-179">Characters</span></span>     | <span data-ttu-id="fa19a-180">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="fa19a-180">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="fa19a-181">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="fa19a-181">&#124; ' " ..</span></span>        |
|<span data-ttu-id="fa19a-182">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="fa19a-182">Characters in these ranges</span></span>    | <span data-ttu-id="fa19a-183">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="fa19a-183">0 to 1F</span></span><br><span data-ttu-id="fa19a-184">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="fa19a-184">80 to 9F</span></span>        |
|<span data-ttu-id="fa19a-185">単語数</span><span class="sxs-lookup"><span data-stu-id="fa19a-185">Words</span></span>     | <span data-ttu-id="fa19a-186">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="fa19a-186">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="fa19a-187">チャネル名は、アンダースコア (_) またはピリオド (。) で始まったり終わったりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="fa19a-187">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="fa19a-188">会議と通話</span><span class="sxs-lookup"><span data-stu-id="fa19a-188">Meetings and calls</span></span>

|<span data-ttu-id="fa19a-189">機能</span><span class="sxs-lookup"><span data-stu-id="fa19a-189">Feature</span></span>     | <span data-ttu-id="fa19a-190">上限</span><span class="sxs-lookup"><span data-stu-id="fa19a-190">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="fa19a-191">会議に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="fa19a-191">Number of people in a meeting</span></span>  | <span data-ttu-id="fa19a-192">250 人</span><span class="sxs-lookup"><span data-stu-id="fa19a-192">250</span></span>    |
|<span data-ttu-id="fa19a-193">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-193">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="fa19a-194">20</span><span class="sxs-lookup"><span data-stu-id="fa19a-194">20</span></span> |
|<span data-ttu-id="fa19a-195">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="fa19a-195">Max PowerPoint File Size</span></span> | <span data-ttu-id="fa19a-196">2GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-196">2GB</span></span>|
|<span data-ttu-id="fa19a-197">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="fa19a-197">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="fa19a-198">20 日間</span><span class="sxs-lookup"><span data-stu-id="fa19a-198">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="fa19a-199">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="fa19a-199">Meeting expiration</span></span>

|<span data-ttu-id="fa19a-200">会議の種類</span><span class="sxs-lookup"><span data-stu-id="fa19a-200">Meeting type</span></span>  |<span data-ttu-id="fa19a-201">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="fa19a-201">Meeting expires after this much time</span></span>  |<span data-ttu-id="fa19a-202">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="fa19a-202">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="fa19a-203">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="fa19a-203">Meet now</span></span>     |<span data-ttu-id="fa19a-204">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="fa19a-204">Start time + 8 hours</span></span>         |<span data-ttu-id="fa19a-205">該当なし</span><span class="sxs-lookup"><span data-stu-id="fa19a-205">N/A</span></span>         |
|<span data-ttu-id="fa19a-206">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="fa19a-206">Regular with no end time</span></span>     |<span data-ttu-id="fa19a-207">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="fa19a-207">Start time + 60 days</span></span>         | <span data-ttu-id="fa19a-208">60 日</span><span class="sxs-lookup"><span data-stu-id="fa19a-208">60 days</span></span>        |
|<span data-ttu-id="fa19a-209">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="fa19a-209">Regular with end time</span></span>     |<span data-ttu-id="fa19a-210">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="fa19a-210">End time + 60 days</span></span>         |<span data-ttu-id="fa19a-211">60 日</span><span class="sxs-lookup"><span data-stu-id="fa19a-211">60 days</span></span>         |
|<span data-ttu-id="fa19a-212">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="fa19a-212">Recurring with no end time</span></span>     |<span data-ttu-id="fa19a-213">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="fa19a-213">Start time + 60 days</span></span>         |<span data-ttu-id="fa19a-214">60 日</span><span class="sxs-lookup"><span data-stu-id="fa19a-214">60 days</span></span>         |
|<span data-ttu-id="fa19a-215">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="fa19a-215">Recurring with end time</span></span>     |<span data-ttu-id="fa19a-216">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="fa19a-216">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="fa19a-217">60 日</span><span class="sxs-lookup"><span data-stu-id="fa19a-217">60 days</span></span>         |

## <a name="teams-live-events"></a><span data-ttu-id="fa19a-218">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="fa19a-218">Teams live events</span></span>

|<span data-ttu-id="fa19a-219">機能</span><span class="sxs-lookup"><span data-stu-id="fa19a-219">Feature</span></span>     | <span data-ttu-id="fa19a-220">上限</span><span class="sxs-lookup"><span data-stu-id="fa19a-220">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="fa19a-221">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="fa19a-221">Audience size</span></span> | <span data-ttu-id="fa19a-222">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="fa19a-222">10,000 attendees</span></span> |
|<span data-ttu-id="fa19a-223">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="fa19a-223">Duration of event</span></span> | <span data-ttu-id="fa19a-224">4 時間</span><span class="sxs-lookup"><span data-stu-id="fa19a-224">4 hours</span></span> |
|<span data-ttu-id="fa19a-225">Office 365 組織の同時ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="fa19a-225">Concurrent live events in an Office 365 organization</span></span> | <span data-ttu-id="fa19a-226">15</span><span class="sxs-lookup"><span data-stu-id="fa19a-226">15</span></span> |

<span data-ttu-id="fa19a-227">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="fa19a-227">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa19a-228">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="fa19a-228">**Microsoft 365 live event limit increases**</span></span>
> 
> <span data-ttu-id="fa19a-229">お客様が急速に変化するコミュニケーションのニーズに対応できるように、Microsoft 365 ライブ イベントは、2020 年 7 月 1 日まで、Teams でホストされるライブ イベントの既定の上限を一時的に引き上げます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-229">To help customers meet rapidly changing communication needs, Microsoft 365 live events will temporarily raise default limits until July 1, 2020, for live events hosted in Teams.</span></span> <span data-ttu-id="fa19a-230">2020 年 4 月下旬から次の上限が適用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="fa19a-230">The following increases are being rolled out in late April 2020:</span></span>
> - <span data-ttu-id="fa19a-231">参加者の制限: イベントは最大 20,000 人の参加者をサポートできます</span><span class="sxs-lookup"><span data-stu-id="fa19a-231">Attendee limit: events can suport up to 20,000 attendees</span></span>
> - <span data-ttu-id="fa19a-232">同時イベント: テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="fa19a-232">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="fa19a-233">イベントの時間: イベントの長さが 1 回のブロードキャストにつき 16 時間に延長されました</span><span class="sxs-lookup"><span data-stu-id="fa19a-233">Event duration: event length has been increased to 16 hours per broadcast</span></span>



## <a name="presence-in-outlook"></a><span data-ttu-id="fa19a-234">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="fa19a-234">Presence in Outlook</span></span>

<span data-ttu-id="fa19a-235">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fa19a-235">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="fa19a-236">Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa19a-236">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="fa19a-237">ストレージ</span><span class="sxs-lookup"><span data-stu-id="fa19a-237">Storage</span></span>

<span data-ttu-id="fa19a-p108">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-p108">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="fa19a-240">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa19a-240">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="fa19a-241">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="fa19a-241">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="fa19a-242">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-242">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="fa19a-243">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="fa19a-243">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="fa19a-244">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-244">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="fa19a-245">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="fa19a-245">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="fa19a-246">機能</span><span class="sxs-lookup"><span data-stu-id="fa19a-246">Feature</span></span>                 |<span data-ttu-id="fa19a-247">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="fa19a-247">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="fa19a-248">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="fa19a-248">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="fa19a-249">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="fa19a-249">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="fa19a-250">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="fa19a-250">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="fa19a-251">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="fa19a-251">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="fa19a-252">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="fa19a-252">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="fa19a-253">ストレージ</span><span class="sxs-lookup"><span data-stu-id="fa19a-253">Storage</span></span>                 |<span data-ttu-id="fa19a-254">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-254">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="fa19a-255">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-255">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="fa19a-256">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-256">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="fa19a-257">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-257">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="fa19a-258">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-258">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="fa19a-259">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="fa19a-259">1 TB per organization</span></span>           |
|<span data-ttu-id="fa19a-260">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="fa19a-260">Storage for Teams Files</span></span> |<span data-ttu-id="fa19a-261">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="fa19a-261">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="fa19a-262">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="fa19a-262">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="fa19a-263">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="fa19a-263">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="fa19a-264">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="fa19a-264">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="fa19a-265">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="fa19a-265">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="fa19a-266">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="fa19a-266">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="fa19a-267">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="fa19a-267">File upload limit  (per file)</span></span>    |<span data-ttu-id="fa19a-268">15 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-268">15 GB</span></span>    |<span data-ttu-id="fa19a-269">15 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-269">15 GB</span></span>    |<span data-ttu-id="fa19a-270">15 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-270">15 GB</span></span>    |<span data-ttu-id="fa19a-271">15 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-271">15 GB</span></span>    |<span data-ttu-id="fa19a-272">15 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-272">15 GB</span></span>    |<span data-ttu-id="fa19a-273">15 GB</span><span class="sxs-lookup"><span data-stu-id="fa19a-273">15 GB</span></span>    |

<span data-ttu-id="fa19a-274">チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="fa19a-274">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="fa19a-275">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa19a-275">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="tags"></a><span data-ttu-id="fa19a-276">タグ</span><span class="sxs-lookup"><span data-stu-id="fa19a-276">Tags</span></span>

|<span data-ttu-id="fa19a-277">機能</span><span class="sxs-lookup"><span data-stu-id="fa19a-277">Feature</span></span>  |<span data-ttu-id="fa19a-278">上限</span><span class="sxs-lookup"><span data-stu-id="fa19a-278">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="fa19a-279">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="fa19a-279">Number of tags per team</span></span>    | <span data-ttu-id="fa19a-280">100</span><span class="sxs-lookup"><span data-stu-id="fa19a-280">100</span></span>        |
|<span data-ttu-id="fa19a-281">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="fa19a-281">Number of suggested default tags per team</span></span>    | <span data-ttu-id="fa19a-282">25</span><span class="sxs-lookup"><span data-stu-id="fa19a-282">25</span></span>        |
|<span data-ttu-id="fa19a-283">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="fa19a-283">Number of team members assign to a tag</span></span>    |<span data-ttu-id="fa19a-284">100</span><span class="sxs-lookup"><span data-stu-id="fa19a-284">100</span></span>         |
|<span data-ttu-id="fa19a-285">ユーザーに割り当てられたるタグ数</span><span class="sxs-lookup"><span data-stu-id="fa19a-285">Number of tags assigned to a user</span></span>    |<span data-ttu-id="fa19a-286">25</span><span class="sxs-lookup"><span data-stu-id="fa19a-286">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="fa19a-287">連絡先</span><span class="sxs-lookup"><span data-stu-id="fa19a-287">Contacts</span></span>

<span data-ttu-id="fa19a-288">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa19a-288">Teams uses these contacts:</span></span>

- <span data-ttu-id="fa19a-289">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="fa19a-289">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="fa19a-290">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="fa19a-290">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="fa19a-291">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-291">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="fa19a-292">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa19a-292">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="fa19a-293">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="fa19a-293">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="fa19a-294">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="fa19a-294">Operating systems</span></span>

<span data-ttu-id="fa19a-295">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa19a-295">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
