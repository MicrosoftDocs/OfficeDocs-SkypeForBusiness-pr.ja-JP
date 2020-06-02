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
ms.openlocfilehash: 85879d55ad50a6c68bbe59d9c1fb51663988c661
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489059"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="a6b8a-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="a6b8a-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="a6b8a-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="a6b8a-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="a6b8a-105">Teams and channels</span></span>

|<span data-ttu-id="a6b8a-106">機能</span><span class="sxs-lookup"><span data-stu-id="a6b8a-106">Feature</span></span>    | <span data-ttu-id="a6b8a-107">上限</span><span class="sxs-lookup"><span data-stu-id="a6b8a-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="a6b8a-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-108">Number of teams a user can create</span></span> | <span data-ttu-id="a6b8a-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="a6b8a-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="a6b8a-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="a6b8a-111">1,000</span><span class="sxs-lookup"><span data-stu-id="a6b8a-111">1,000</span></span>|
|<span data-ttu-id="a6b8a-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-112">Number of members in a team</span></span> | <span data-ttu-id="a6b8a-113">10,000</span><span class="sxs-lookup"><span data-stu-id="a6b8a-113">10,000</span></span>       |
|<span data-ttu-id="a6b8a-114">チーム 1 つあたりの所有者数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-114">Number of owners per team</span></span> | <span data-ttu-id="a6b8a-115">100</span><span class="sxs-lookup"><span data-stu-id="a6b8a-115">100</span></span>   |
|<span data-ttu-id="a6b8a-116">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="a6b8a-117">5</span><span class="sxs-lookup"><span data-stu-id="a6b8a-117">5</span></span>     |
|<span data-ttu-id="a6b8a-118">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="a6b8a-119">5,000</span><span class="sxs-lookup"><span data-stu-id="a6b8a-119">5,000</span></span>       |
|<span data-ttu-id="a6b8a-120">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="a6b8a-121">500,000</span><span class="sxs-lookup"><span data-stu-id="a6b8a-121">500,000</span></span>   |
|<span data-ttu-id="a6b8a-122">Office 365 組織が持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-122">Number of teams an Office 365 organization can have</span></span>    | <span data-ttu-id="a6b8a-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="a6b8a-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="a6b8a-124">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-124">Number of channels per team</span></span>    | <span data-ttu-id="a6b8a-125">200 (削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="a6b8a-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="a6b8a-126">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-126">Number of Private channels per team</span></span>    |<span data-ttu-id="a6b8a-127">30</span><span class="sxs-lookup"><span data-stu-id="a6b8a-127">30</span></span>|
|<span data-ttu-id="a6b8a-128">プライベート チャネルのメンバー数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="a6b8a-129">250 人</span><span class="sxs-lookup"><span data-stu-id="a6b8a-129">250</span></span>|
|<span data-ttu-id="a6b8a-130">チャネル会話の投稿サイズ</span><span class="sxs-lookup"><span data-stu-id="a6b8a-130">Channel conversation post size</span></span> | <span data-ttu-id="a6b8a-131">投稿ごとに約 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a6b8a-131">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="a6b8a-132">&sup1; Azure Active Directory の任意のディレクトリ オブジェクトは、この制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-132">&sup1; Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="a6b8a-133">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-133">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="a6b8a-134">&sup2; この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-134">&sup2; This limit includes archived teams.</span></span>

<span data-ttu-id="a6b8a-135">&sup3; 削除したチャネルは、30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-135">&sup3; Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="a6b8a-136">この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルとしてカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-136">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="a6b8a-137">30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限である 200 チャンネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-137">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="a6b8a-138"><sup>4</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、コネクタの数、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-138"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="a6b8a-139">Messaging</span><span class="sxs-lookup"><span data-stu-id="a6b8a-139">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="a6b8a-140">チャット</span><span class="sxs-lookup"><span data-stu-id="a6b8a-140">Chat</span></span>

<span data-ttu-id="a6b8a-141">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-141">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="a6b8a-142">これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-142">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="a6b8a-143">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-143">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="a6b8a-144">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-144">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="a6b8a-145">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-145">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="a6b8a-146">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-146">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="a6b8a-147">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-147">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="a6b8a-148">機能</span><span class="sxs-lookup"><span data-stu-id="a6b8a-148">Feature</span></span>  | <span data-ttu-id="a6b8a-149">上限</span><span class="sxs-lookup"><span data-stu-id="a6b8a-149">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="a6b8a-150">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6b8a-150">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="a6b8a-151">100</span><span class="sxs-lookup"><span data-stu-id="a6b8a-151">100</span></span>    |
|<span data-ttu-id="a6b8a-152">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-152">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="a6b8a-153">20</span><span class="sxs-lookup"><span data-stu-id="a6b8a-153">20</span></span> |
|<span data-ttu-id="a6b8a-154">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a6b8a-154">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="a6b8a-155">10</span><span class="sxs-lookup"><span data-stu-id="a6b8a-155">10</span></span>     |
|<span data-ttu-id="a6b8a-156">チャットのサイズ</span><span class="sxs-lookup"><span data-stu-id="a6b8a-156">Chat size</span></span> | <span data-ttu-id="a6b8a-157">投稿ごとに約 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a6b8a-157">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="a6b8a-158"><sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-158"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="a6b8a-159"><sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-159"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="a6b8a-160"><sup>3</sup> 28 KBは、メッセージ自体 （テキスト、画像リンクなど）、@メンション、およびリアクションを含むため、おおよその制限です。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-160"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="a6b8a-161">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="a6b8a-161">Emailing a channel</span></span>

 <span data-ttu-id="a6b8a-162">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-162">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="a6b8a-163">メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-163">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="a6b8a-164">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-164">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="a6b8a-165">機能</span><span class="sxs-lookup"><span data-stu-id="a6b8a-165">Feature</span></span>  | <span data-ttu-id="a6b8a-166">上限</span><span class="sxs-lookup"><span data-stu-id="a6b8a-166">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="a6b8a-167">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="a6b8a-167">Message size<sup>1<sup></span></span> | <span data-ttu-id="a6b8a-168">24 KB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-168">24 KB</span></span> |
|<span data-ttu-id="a6b8a-169">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a6b8a-169">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="a6b8a-170">20</span><span class="sxs-lookup"><span data-stu-id="a6b8a-170">20</span></span>     |
|<span data-ttu-id="a6b8a-171">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="a6b8a-171">Size of each file attachment</span></span> | <span data-ttu-id="a6b8a-172">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="a6b8a-172">Less than 10 MB</span></span> |
|<span data-ttu-id="a6b8a-173">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a6b8a-173">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="a6b8a-174">50</span><span class="sxs-lookup"><span data-stu-id="a6b8a-174">50</span></span>   |

<span data-ttu-id="a6b8a-175"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-175"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="a6b8a-176"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-176"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="a6b8a-177">詳細については、「[ Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-177">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="a6b8a-178">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-178">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="a6b8a-179">チャネル名</span><span class="sxs-lookup"><span data-stu-id="a6b8a-179">Channel names</span></span>

<span data-ttu-id="a6b8a-180">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-180">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="a6b8a-181">文字</span><span class="sxs-lookup"><span data-stu-id="a6b8a-181">Characters</span></span>     | <span data-ttu-id="a6b8a-182">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="a6b8a-182">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="a6b8a-183">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="a6b8a-183">&#124; ' " ..</span></span>        |
|<span data-ttu-id="a6b8a-184">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="a6b8a-184">Characters in these ranges</span></span>    | <span data-ttu-id="a6b8a-185">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="a6b8a-185">0 to 1F</span></span><br><span data-ttu-id="a6b8a-186">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="a6b8a-186">80 to 9F</span></span>        |
|<span data-ttu-id="a6b8a-187">単語</span><span class="sxs-lookup"><span data-stu-id="a6b8a-187">Words</span></span>     | <span data-ttu-id="a6b8a-188">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="a6b8a-188">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="a6b8a-189">チャネル名は、アンダースコア (_) またはピリオド (。) で始まったり終わったりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-189">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="a6b8a-190">会議と通話</span><span class="sxs-lookup"><span data-stu-id="a6b8a-190">Meetings and calls</span></span>

|<span data-ttu-id="a6b8a-191">機能</span><span class="sxs-lookup"><span data-stu-id="a6b8a-191">Feature</span></span>     | <span data-ttu-id="a6b8a-192">上限</span><span class="sxs-lookup"><span data-stu-id="a6b8a-192">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="a6b8a-193">会議に参加できるユーザー数 (チャットして電話をかけることができる)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-193">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="a6b8a-194">250 人</span><span class="sxs-lookup"><span data-stu-id="a6b8a-194">250</span></span>    |
|<span data-ttu-id="a6b8a-195">ビデオまたは音声通話でチャットに参加できるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-195">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="a6b8a-196">20</span><span class="sxs-lookup"><span data-stu-id="a6b8a-196">20</span></span> |
|<span data-ttu-id="a6b8a-197">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="a6b8a-197">Max PowerPoint File Size</span></span> | <span data-ttu-id="a6b8a-198">2GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-198">2GB</span></span>|
|<span data-ttu-id="a6b8a-199">Teams は[会議の記録](cloud-recording.md)を保持しますが、これは Microsoft Stream にはアップロードされず、ローカルのダウンロード用です</span><span class="sxs-lookup"><span data-stu-id="a6b8a-199">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="a6b8a-200">20 日間</span><span class="sxs-lookup"><span data-stu-id="a6b8a-200">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="a6b8a-201">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="a6b8a-201">Meeting expiration</span></span>

|<span data-ttu-id="a6b8a-202">会議の種類</span><span class="sxs-lookup"><span data-stu-id="a6b8a-202">Meeting type</span></span>  |<span data-ttu-id="a6b8a-203">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="a6b8a-203">Meeting expires after this much time</span></span>  |<span data-ttu-id="a6b8a-204">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="a6b8a-204">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a6b8a-205">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="a6b8a-205">Meet now</span></span>     |<span data-ttu-id="a6b8a-206">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="a6b8a-206">Start time + 8 hours</span></span>         |<span data-ttu-id="a6b8a-207">該当なし</span><span class="sxs-lookup"><span data-stu-id="a6b8a-207">N/A</span></span>         |
|<span data-ttu-id="a6b8a-208">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="a6b8a-208">Regular with no end time</span></span>     |<span data-ttu-id="a6b8a-209">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="a6b8a-209">Start time + 60 days</span></span>         | <span data-ttu-id="a6b8a-210">60 日</span><span class="sxs-lookup"><span data-stu-id="a6b8a-210">60 days</span></span>        |
|<span data-ttu-id="a6b8a-211">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="a6b8a-211">Regular with end time</span></span>     |<span data-ttu-id="a6b8a-212">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="a6b8a-212">End time + 60 days</span></span>         |<span data-ttu-id="a6b8a-213">60 日</span><span class="sxs-lookup"><span data-stu-id="a6b8a-213">60 days</span></span>         |
|<span data-ttu-id="a6b8a-214">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="a6b8a-214">Recurring with no end time</span></span>     |<span data-ttu-id="a6b8a-215">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="a6b8a-215">Start time + 60 days</span></span>         |<span data-ttu-id="a6b8a-216">60 日</span><span class="sxs-lookup"><span data-stu-id="a6b8a-216">60 days</span></span>         |
|<span data-ttu-id="a6b8a-217">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="a6b8a-217">Recurring with end time</span></span>     |<span data-ttu-id="a6b8a-218">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="a6b8a-218">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="a6b8a-219">60 日</span><span class="sxs-lookup"><span data-stu-id="a6b8a-219">60 days</span></span>         |

## <a name="teams-live-events"></a><span data-ttu-id="a6b8a-220">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="a6b8a-220">Teams live events</span></span>

|<span data-ttu-id="a6b8a-221">機能</span><span class="sxs-lookup"><span data-stu-id="a6b8a-221">Feature</span></span>     | <span data-ttu-id="a6b8a-222">上限</span><span class="sxs-lookup"><span data-stu-id="a6b8a-222">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="a6b8a-223">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="a6b8a-223">Audience size</span></span> | <span data-ttu-id="a6b8a-224">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="a6b8a-224">10,000 attendees</span></span> |
|<span data-ttu-id="a6b8a-225">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="a6b8a-225">Duration of event</span></span> | <span data-ttu-id="a6b8a-226">4 時間</span><span class="sxs-lookup"><span data-stu-id="a6b8a-226">4 hours</span></span> |
|<span data-ttu-id="a6b8a-227">Office 365 組織で実行されている同時ライブ イベント <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6b8a-227">Concurrent live events running in an Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="a6b8a-228">15</span><span class="sxs-lookup"><span data-stu-id="a6b8a-228">15</span></span> |

<span data-ttu-id="a6b8a-229"><sup>1</sup> ライブ イベントはいくつでもスケジュールできますが、一度に実行できるのは 15 件のみです。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-229"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="a6b8a-230">プロデューサーがライブ イベントに参加するとすぐに、実行中と見なされます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-230">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="a6b8a-231">16 回目のライブ イベントに参加しようとしたプロデューサーにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-231">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="a6b8a-232">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-232">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6b8a-233">**Microsoft 365 ライブ イベントの上限の引き上げ**</span><span class="sxs-lookup"><span data-stu-id="a6b8a-233">**Microsoft 365 live event limit increases**</span></span>
> 
> <span data-ttu-id="a6b8a-234">お客様が急速に変化するコミュニケーションのニーズに対応できるように、Microsoft 365 ライブ イベントは、2020 年 7 月 1 日まで、Teams でホストされるライブ イベントの既定の上限を一時的に引き上げます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-234">To help customers meet rapidly changing communication needs, Microsoft 365 live events will temporarily raise default limits until July 1, 2020, for live events hosted in Teams.</span></span> <span data-ttu-id="a6b8a-235">2020 年 4 月下旬から次の上限が適用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-235">The following increases are being rolled out in late April 2020:</span></span>
> - <span data-ttu-id="a6b8a-236">参加者の制限: イベントは最大 20,000 人の参加者をサポートできます</span><span class="sxs-lookup"><span data-stu-id="a6b8a-236">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="a6b8a-237">同時イベント: テナント全体で 50 のイベントを同時にホストできます</span><span class="sxs-lookup"><span data-stu-id="a6b8a-237">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="a6b8a-238">イベントの時間: イベントの長さが 1 回のブロードキャストにつき 16 時間に延長されました</span><span class="sxs-lookup"><span data-stu-id="a6b8a-238">Event duration: event length has been increased to 16 hours per broadcast</span></span>



## <a name="presence-in-outlook"></a><span data-ttu-id="a6b8a-239">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="a6b8a-239">Presence in Outlook</span></span>

<span data-ttu-id="a6b8a-240">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-240">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="a6b8a-241">Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-241">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="a6b8a-242">ストレージ</span><span class="sxs-lookup"><span data-stu-id="a6b8a-242">Storage</span></span>

<span data-ttu-id="a6b8a-p109">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-p109">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="a6b8a-245">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-245">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="a6b8a-246">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-246">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="a6b8a-247">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-247">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="a6b8a-248">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-248">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="a6b8a-249">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-249">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="a6b8a-250">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-250">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="a6b8a-251">機能</span><span class="sxs-lookup"><span data-stu-id="a6b8a-251">Feature</span></span>                 |<span data-ttu-id="a6b8a-252">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="a6b8a-252">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="a6b8a-253">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="a6b8a-253">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="a6b8a-254">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="a6b8a-254">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="a6b8a-255">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="a6b8a-255">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="a6b8a-256">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="a6b8a-256">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="a6b8a-257">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="a6b8a-257">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="a6b8a-258">ストレージ</span><span class="sxs-lookup"><span data-stu-id="a6b8a-258">Storage</span></span>                 |<span data-ttu-id="a6b8a-259">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-259">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="a6b8a-260">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-260">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="a6b8a-261">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-261">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="a6b8a-262">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-262">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="a6b8a-263">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-263">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="a6b8a-264">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-264">1 TB per organization</span></span>           |
|<span data-ttu-id="a6b8a-265">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="a6b8a-265">Storage for Teams Files</span></span> |<span data-ttu-id="a6b8a-266">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-266">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a6b8a-267">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-267">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a6b8a-268">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-268">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a6b8a-269">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-269">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a6b8a-270">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-270">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="a6b8a-271">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-271">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="a6b8a-272">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-272">File upload limit  (per file)</span></span>    |<span data-ttu-id="a6b8a-273">15 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-273">15 GB</span></span>    |<span data-ttu-id="a6b8a-274">15 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-274">15 GB</span></span>    |<span data-ttu-id="a6b8a-275">15 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-275">15 GB</span></span>    |<span data-ttu-id="a6b8a-276">15 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-276">15 GB</span></span>    |<span data-ttu-id="a6b8a-277">15 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-277">15 GB</span></span>    |<span data-ttu-id="a6b8a-278">15 GB</span><span class="sxs-lookup"><span data-stu-id="a6b8a-278">15 GB</span></span>    |

<span data-ttu-id="a6b8a-279">チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-279">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="a6b8a-280">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-280">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="tags"></a><span data-ttu-id="a6b8a-281">タグ</span><span class="sxs-lookup"><span data-stu-id="a6b8a-281">Tags</span></span>

|<span data-ttu-id="a6b8a-282">機能</span><span class="sxs-lookup"><span data-stu-id="a6b8a-282">Feature</span></span>  |<span data-ttu-id="a6b8a-283">上限</span><span class="sxs-lookup"><span data-stu-id="a6b8a-283">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="a6b8a-284">チームごとのタグ数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-284">Number of tags per team</span></span>    | <span data-ttu-id="a6b8a-285">100</span><span class="sxs-lookup"><span data-stu-id="a6b8a-285">100</span></span>        |
|<span data-ttu-id="a6b8a-286">チームごとに推奨される既定のタグ数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-286">Number of suggested default tags per team</span></span>    | <span data-ttu-id="a6b8a-287">25</span><span class="sxs-lookup"><span data-stu-id="a6b8a-287">25</span></span>        |
|<span data-ttu-id="a6b8a-288">タグに割り当てられたチームメンバーの数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-288">Number of team members assign to a tag</span></span>    |<span data-ttu-id="a6b8a-289">100</span><span class="sxs-lookup"><span data-stu-id="a6b8a-289">100</span></span>         |
|<span data-ttu-id="a6b8a-290">ユーザーに割り当てられたるタグ数</span><span class="sxs-lookup"><span data-stu-id="a6b8a-290">Number of tags assigned to a user</span></span>    |<span data-ttu-id="a6b8a-291">25</span><span class="sxs-lookup"><span data-stu-id="a6b8a-291">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="a6b8a-292">連絡先</span><span class="sxs-lookup"><span data-stu-id="a6b8a-292">Contacts</span></span>

<span data-ttu-id="a6b8a-293">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-293">Teams uses these contacts:</span></span>

- <span data-ttu-id="a6b8a-294">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="a6b8a-294">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="a6b8a-295">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="a6b8a-295">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="a6b8a-296">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-296">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="a6b8a-297">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-297">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="a6b8a-298">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="a6b8a-298">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="a6b8a-299">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="a6b8a-299">Operating systems</span></span>

<span data-ttu-id="a6b8a-300">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6b8a-300">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
