---
title: Microsoft Teams の制限事項と仕様
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Microsoft Teams に適用される制限、仕様、およびその他の要件について説明します。
localization_priority: Priority
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa6fad448f0251a44d31c5277b43390daeb3441c
ms.sourcegitcommit: e43a66a7f769f855dc45c1bb7f83636d0390949b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823912"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="8a13e-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="8a13e-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="8a13e-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a13e-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="8a13e-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="8a13e-105">Teams and channels</span></span>

|<span data-ttu-id="8a13e-106">機能</span><span class="sxs-lookup"><span data-stu-id="8a13e-106">Feature</span></span>    | <span data-ttu-id="8a13e-107">上限</span><span class="sxs-lookup"><span data-stu-id="8a13e-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="8a13e-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="8a13e-108">Number of teams a user can create</span></span> | <span data-ttu-id="8a13e-109">オブジェクト制限 250、&sup1;</span><span class="sxs-lookup"><span data-stu-id="8a13e-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="8a13e-110">ユーザーがメンバーの一員になることができるチームの数</span><span class="sxs-lookup"><span data-stu-id="8a13e-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="8a13e-111">1,000</span><span class="sxs-lookup"><span data-stu-id="8a13e-111">1,000</span></span>|
|<span data-ttu-id="8a13e-112">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8a13e-112">Number of members in a team</span></span> | <span data-ttu-id="8a13e-113">5,000</span><span class="sxs-lookup"><span data-stu-id="8a13e-113">5,000</span></span>       |
|<span data-ttu-id="8a13e-114">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="8a13e-114">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="8a13e-115">5</span><span class="sxs-lookup"><span data-stu-id="8a13e-115">5</span></span>     |
|<span data-ttu-id="8a13e-116">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="8a13e-116">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="8a13e-117">5,000</span><span class="sxs-lookup"><span data-stu-id="8a13e-117">5,000</span></span>       |
|<span data-ttu-id="8a13e-118">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="8a13e-118">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="8a13e-119">500,000</span><span class="sxs-lookup"><span data-stu-id="8a13e-119">500,000</span></span>   |
|<span data-ttu-id="8a13e-120">Office 365 テナントが持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="8a13e-120">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="8a13e-121">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="8a13e-121">500,000&sup2;</span></span>     |
|<span data-ttu-id="8a13e-122">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="8a13e-122">Number of channels per team</span></span>    | <span data-ttu-id="8a13e-123">200 (削除されたチャネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="8a13e-123">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="8a13e-124">チームごとのプライベート チャネル数</span><span class="sxs-lookup"><span data-stu-id="8a13e-124">Number of Private channels per team</span></span>    |<span data-ttu-id="8a13e-125">30</span><span class="sxs-lookup"><span data-stu-id="8a13e-125">30</span></span>|

<span data-ttu-id="8a13e-126">&sup1; Azure Active Directory の任意のディレクトリ オブジェクトは、この制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-126">&sup1; Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="8a13e-127">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-127">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="8a13e-128">&sup2; この制限には、アーカイブ済みのチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-128">&sup2; This limit includes archived teams.</span></span>

<span data-ttu-id="8a13e-129">&sup3; 削除したチャネルは、30 日以内であれば復元できます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-129">&sup3; Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="8a13e-130">この 30 日間、削除されたチャンネルはチームごとの制限である 200 チャンネルとしてカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-130">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="8a13e-131">30 日を経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャンネルはチームごとの制限である 200 チャンネルとしてカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="8a13e-131">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="messaging"></a><span data-ttu-id="8a13e-132">メッセージング </span><span class="sxs-lookup"><span data-stu-id="8a13e-132">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="8a13e-133">チャット</span><span class="sxs-lookup"><span data-stu-id="8a13e-133">Chat</span></span>

<span data-ttu-id="8a13e-134">Teams のチャット リストの一部である会話に参加したユーザーは、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a13e-134">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="8a13e-135">これは、チャット リストの一部である会話が、チャット参加者のクラウドベースのメールボックスに保存されるためです。</span><span class="sxs-lookup"><span data-stu-id="8a13e-135">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="8a13e-136">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a13e-136">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="8a13e-137">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a13e-137">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="8a13e-138">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="8a13e-138">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="8a13e-139">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="8a13e-139">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="8a13e-140">Teams チャットは、Microsoft Exchange のバックエンドで動作するため、Teams 内のチャット機能に Exchange メッセージングの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-140">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="8a13e-141">機能</span><span class="sxs-lookup"><span data-stu-id="8a13e-141">Feature</span></span>  | <span data-ttu-id="8a13e-142">上限</span><span class="sxs-lookup"><span data-stu-id="8a13e-142">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8a13e-143">プライベート チャットに参加できるユーザー数 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8a13e-143">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="8a13e-144">100</span><span class="sxs-lookup"><span data-stu-id="8a13e-144">100</span></span>    |
|<span data-ttu-id="8a13e-145">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a13e-145">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="8a13e-146">10</span><span class="sxs-lookup"><span data-stu-id="8a13e-146">10</span></span>     |

<span data-ttu-id="8a13e-147"><sup>1</sup> チャットに 20 人以上いる場合、次のチャット機能は無効になります。Outlook の自動応答と Teams 状態メッセージ、入力インジケーター、ビデオおよび音声通話、共有、開封確認。</span><span class="sxs-lookup"><span data-stu-id="8a13e-147"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="8a13e-148"><sup>2</sup> 添付ファイルの数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-148"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="8a13e-149">電子メールでチャネルを送信する</span><span class="sxs-lookup"><span data-stu-id="8a13e-149">Emailing a channel</span></span>

 <span data-ttu-id="8a13e-150">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a13e-150">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="8a13e-151">メールがチャネルの一部の場合、誰でもそれに返信して会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-151">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="8a13e-152">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a13e-152">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="8a13e-153">機能</span><span class="sxs-lookup"><span data-stu-id="8a13e-153">Feature</span></span>  | <span data-ttu-id="8a13e-154">上限</span><span class="sxs-lookup"><span data-stu-id="8a13e-154">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="8a13e-155">メッセージ サイズ <sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="8a13e-155">Message size<sup>1<sup></span></span> | <span data-ttu-id="8a13e-156">24 KB</span><span class="sxs-lookup"><span data-stu-id="8a13e-156">24 KB</span></span> |
|<span data-ttu-id="8a13e-157">添付ファイルの数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a13e-157">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="8a13e-158">20</span><span class="sxs-lookup"><span data-stu-id="8a13e-158">20</span></span>     |
|<span data-ttu-id="8a13e-159">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="8a13e-159">Size of each file attachment</span></span> | <span data-ttu-id="8a13e-160">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="8a13e-160">Less than 10 MB</span></span> |
|<span data-ttu-id="8a13e-161">インライン画像の数 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a13e-161">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="8a13e-162">50</span><span class="sxs-lookup"><span data-stu-id="8a13e-162">50</span></span>   |

<span data-ttu-id="8a13e-163"><sup>1</sup> メッセージがこの制限を超えると、プレビュー メッセージが生成され、ユーザーは提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-163"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="8a13e-164"><sup>2</sup> 添付ファイルまたは画像の数がこの制限を超えると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-164"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="8a13e-165">詳細については、「[ Exchange Online の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a13e-165">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="8a13e-166">メッセージ サイズ、添付ファイル、およびインライン イメージの制限は、すべての Office 365 ライセンスで同じです。</span><span class="sxs-lookup"><span data-stu-id="8a13e-166">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="8a13e-167">チャネル名</span><span class="sxs-lookup"><span data-stu-id="8a13e-167">Channel names</span></span>

<span data-ttu-id="8a13e-168">チャネル名に次の文字や単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="8a13e-168">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="8a13e-169">文字</span><span class="sxs-lookup"><span data-stu-id="8a13e-169">Characters</span></span>     | <span data-ttu-id="8a13e-170">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="8a13e-170">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="8a13e-171">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="8a13e-171">&#124; ' " ..</span></span>        |
|<span data-ttu-id="8a13e-172">この範囲内の文字</span><span class="sxs-lookup"><span data-stu-id="8a13e-172">Characters in these ranges</span></span>    | <span data-ttu-id="8a13e-173">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="8a13e-173">0 to 1F</span></span><br><span data-ttu-id="8a13e-174">80 ~ 9F</span><span class="sxs-lookup"><span data-stu-id="8a13e-174">80 to 9F</span></span>        |
|<span data-ttu-id="8a13e-175">単語数</span><span class="sxs-lookup"><span data-stu-id="8a13e-175">Words</span></span>     | <span data-ttu-id="8a13e-176">フォーム、CON、CONIN$、CONOUT$、PRN、AUX、NUL、COM1 ~ COM9、LPT1 ~  LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="8a13e-176">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="8a13e-177">チャネル名は、アンダースコア (_) またはピリオド (。) で始まったり終わったりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="8a13e-177">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="8a13e-178">会議と通話</span><span class="sxs-lookup"><span data-stu-id="8a13e-178">Meetings and calls</span></span>

|<span data-ttu-id="8a13e-179">機能</span><span class="sxs-lookup"><span data-stu-id="8a13e-179">Feature</span></span>     | <span data-ttu-id="8a13e-180">上限</span><span class="sxs-lookup"><span data-stu-id="8a13e-180">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="8a13e-181">会議に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="8a13e-181">Number of people in a meeting</span></span>  | <span data-ttu-id="8a13e-182">250 人</span><span class="sxs-lookup"><span data-stu-id="8a13e-182">250</span></span>    |
|<span data-ttu-id="8a13e-183">PowerPoint ファイルの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="8a13e-183">Max PowerPoint File Size</span></span> | <span data-ttu-id="8a13e-184">2GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-184">2GB</span></span>|

### <a name="meeting-expiration"></a><span data-ttu-id="8a13e-185">会議の有効期限</span><span class="sxs-lookup"><span data-stu-id="8a13e-185">Meeting expiration</span></span>

|<span data-ttu-id="8a13e-186">会議の種類</span><span class="sxs-lookup"><span data-stu-id="8a13e-186">Meeting type</span></span>  |<span data-ttu-id="8a13e-187">この時間が経過すると、会議は期限切れになります</span><span class="sxs-lookup"><span data-stu-id="8a13e-187">Meeting expires after this much time</span></span>  |<span data-ttu-id="8a13e-188">会議を開始または更新するたびに、有効期限はこの時間だけ延長されます</span><span class="sxs-lookup"><span data-stu-id="8a13e-188">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8a13e-189">今すぐ会議</span><span class="sxs-lookup"><span data-stu-id="8a13e-189">Meet now</span></span>     |<span data-ttu-id="8a13e-190">開始時刻 + 8 時間</span><span class="sxs-lookup"><span data-stu-id="8a13e-190">Start time + 8 hours</span></span>         |<span data-ttu-id="8a13e-191">該当なし</span><span class="sxs-lookup"><span data-stu-id="8a13e-191">N/A</span></span>         |
|<span data-ttu-id="8a13e-192">終了時刻のない標準</span><span class="sxs-lookup"><span data-stu-id="8a13e-192">Regular with no end time</span></span>     |<span data-ttu-id="8a13e-193">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8a13e-193">Start time + 60 days</span></span>         | <span data-ttu-id="8a13e-194">60 日</span><span class="sxs-lookup"><span data-stu-id="8a13e-194">60 days</span></span>        |
|<span data-ttu-id="8a13e-195">終了時刻のある標準</span><span class="sxs-lookup"><span data-stu-id="8a13e-195">Regular with end time</span></span>     |<span data-ttu-id="8a13e-196">終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8a13e-196">End time + 60 days</span></span>         |<span data-ttu-id="8a13e-197">60 日</span><span class="sxs-lookup"><span data-stu-id="8a13e-197">60 days</span></span>         |
|<span data-ttu-id="8a13e-198">終了時刻のない定期</span><span class="sxs-lookup"><span data-stu-id="8a13e-198">Recurring with no end time</span></span>     |<span data-ttu-id="8a13e-199">開始時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8a13e-199">Start time + 60 days</span></span>         |<span data-ttu-id="8a13e-200">60 日</span><span class="sxs-lookup"><span data-stu-id="8a13e-200">60 days</span></span>         |
|<span data-ttu-id="8a13e-201">終了時刻のある定期</span><span class="sxs-lookup"><span data-stu-id="8a13e-201">Recurring with end time</span></span>     |<span data-ttu-id="8a13e-202">最後の発生の終了時刻 + 60 日</span><span class="sxs-lookup"><span data-stu-id="8a13e-202">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="8a13e-203">60 日</span><span class="sxs-lookup"><span data-stu-id="8a13e-203">60 days</span></span>         |



## <a name="teams-live-events"></a><span data-ttu-id="8a13e-204">Teams のライブ イベント</span><span class="sxs-lookup"><span data-stu-id="8a13e-204">Teams live events</span></span>

|<span data-ttu-id="8a13e-205">機能</span><span class="sxs-lookup"><span data-stu-id="8a13e-205">Feature</span></span>     | <span data-ttu-id="8a13e-206">上限</span><span class="sxs-lookup"><span data-stu-id="8a13e-206">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="8a13e-207">対象ユーザーの規模</span><span class="sxs-lookup"><span data-stu-id="8a13e-207">Audience size</span></span> | <span data-ttu-id="8a13e-208">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="8a13e-208">10,000 attendees</span></span> |
|<span data-ttu-id="8a13e-209">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="8a13e-209">Duration of event</span></span> | <span data-ttu-id="8a13e-210">4 時間</span><span class="sxs-lookup"><span data-stu-id="8a13e-210">4 hours</span></span> |
|<span data-ttu-id="8a13e-211">Office 365 テナントの同時ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="8a13e-211">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="8a13e-212">15</span><span class="sxs-lookup"><span data-stu-id="8a13e-212">1.5</span></span> |

<span data-ttu-id="8a13e-213">ライブ イベントおよび Teams のライブ イベントと Skype 会議ブロードキャストの比較の詳細については、「[Teams ライブ イベントと Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="8a13e-213">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="8a13e-214">Outlook でのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="8a13e-214">Presence in Outlook</span></span>

<span data-ttu-id="8a13e-215">Outlook での Teams のプレゼンスは、Outlook 2013 デスクトップ版アプリ以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8a13e-215">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="8a13e-216">Teams のプレゼンスの詳細については、「[Teams でのユーザーのプレゼンス](presence-admins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a13e-216">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="8a13e-217">ストレージ</span><span class="sxs-lookup"><span data-stu-id="8a13e-217">Storage</span></span>

<span data-ttu-id="8a13e-p107">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-p107">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="8a13e-220">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a13e-220">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="8a13e-221">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="8a13e-221">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="8a13e-222">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-222">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="8a13e-223">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="8a13e-223">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="8a13e-224">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-224">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="8a13e-225">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="8a13e-225">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="8a13e-226">機能</span><span class="sxs-lookup"><span data-stu-id="8a13e-226">Feature</span></span>                 |<span data-ttu-id="8a13e-227">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="8a13e-227">Office 365 Business Essentials</span></span>  |<span data-ttu-id="8a13e-228">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="8a13e-228">Office 365 Business Premium</span></span>   |<span data-ttu-id="8a13e-229">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="8a13e-229">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="8a13e-230">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="8a13e-230">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="8a13e-231">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="8a13e-231">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="8a13e-232">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="8a13e-232">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="8a13e-233">ストレージ</span><span class="sxs-lookup"><span data-stu-id="8a13e-233">Storage</span></span>                 |<span data-ttu-id="8a13e-234">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-234">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8a13e-235">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-235">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8a13e-236">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-236">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="8a13e-237">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-237">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="8a13e-238">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-238">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="8a13e-239">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="8a13e-239">1 TB per organization</span></span>           |
|<span data-ttu-id="8a13e-240">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="8a13e-240">Storage for Teams Files</span></span> |<span data-ttu-id="8a13e-241">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8a13e-241">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8a13e-242">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8a13e-242">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8a13e-243">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8a13e-243">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8a13e-244">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8a13e-244">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8a13e-245">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8a13e-245">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="8a13e-246">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="8a13e-246">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="8a13e-247">ファイル アップロードの上限 (ファイルあたり)</span><span class="sxs-lookup"><span data-stu-id="8a13e-247">File upload limit  (per file)</span></span>    |<span data-ttu-id="8a13e-248">15 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-248">15 GB</span></span>    |<span data-ttu-id="8a13e-249">15 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-249">15 GB</span></span>    |<span data-ttu-id="8a13e-250">15 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-250">15 GB</span></span>    |<span data-ttu-id="8a13e-251">15 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-251">15 GB</span></span>    |<span data-ttu-id="8a13e-252">15 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-252">15 GB</span></span>    |<span data-ttu-id="8a13e-253">15 GB</span><span class="sxs-lookup"><span data-stu-id="8a13e-253">15 GB</span></span>    |

<span data-ttu-id="8a13e-254">チャンネルは、チーム用に作成された SharePoint Online サイト コレクション内のフォルダーによってバックアップされるため、チャンネル内のファイル タブは、所属するチームのストレージ制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="8a13e-254">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="8a13e-255">詳細については、「[SharePoint Online の制限](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a13e-255">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="contacts"></a><span data-ttu-id="8a13e-256">連絡先</span><span class="sxs-lookup"><span data-stu-id="8a13e-256">Contacts</span></span>

<span data-ttu-id="8a13e-257">Teams は次の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a13e-257">Teams uses these contacts:</span></span>

- <span data-ttu-id="8a13e-258">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="8a13e-258">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="8a13e-259">ユーザーの Outlook 既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="8a13e-259">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="8a13e-260">Teams ユーザーは、組織の Active Directory 内の任意のユーザと通信できます。また、[**チャット**]  >  [**連絡先**] または [**通話**]  >  [**連絡先**] に移動して、組織の Active Directory 内の任意のユーザを連絡先として連絡先リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-260">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="8a13e-261">Teams ユーザーは、[**通話**]  >  [**連絡先**] に移動して、組織の Active Directory にない人を連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a13e-261">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="8a13e-262">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="8a13e-262">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="8a13e-263">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="8a13e-263">Operating systems</span></span>

<span data-ttu-id="8a13e-264">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a13e-264">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
