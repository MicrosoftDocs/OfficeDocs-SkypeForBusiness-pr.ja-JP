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
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 854c6beeccdae6286bc609a226a49b15de1114e6
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493003"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="b7ea6-103">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="b7ea6-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="b7ea6-104">この記事では、Teams に適用される制限、仕様、およびその他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="b7ea6-105">Teams とチャネル</span><span class="sxs-lookup"><span data-stu-id="b7ea6-105">Teams and channels</span></span>

|<span data-ttu-id="b7ea6-106">機能</span><span class="sxs-lookup"><span data-stu-id="b7ea6-106">Feature</span></span>    | <span data-ttu-id="b7ea6-107">上限</span><span class="sxs-lookup"><span data-stu-id="b7ea6-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="b7ea6-108">ユーザーが作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-108">Number of teams a user can create</span></span> | <span data-ttu-id="b7ea6-109">オブジェクト制限 250、&sup1</span><span class="sxs-lookup"><span data-stu-id="b7ea6-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="b7ea6-110">チームのメンバーの数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-110">Number of members in a team</span></span> | <span data-ttu-id="b7ea6-111">5,000</span><span class="sxs-lookup"><span data-stu-id="b7ea6-111">5,000</span></span>       |
|<span data-ttu-id="b7ea6-112">テナントで許可されている組織全体のチームの数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="b7ea6-113">5</span><span class="sxs-lookup"><span data-stu-id="b7ea6-113">5</span></span>     |
|<span data-ttu-id="b7ea6-114">[組織全体のチーム](create-an-org-wide-team.md)のメンバーの数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="b7ea6-115">5,000</span><span class="sxs-lookup"><span data-stu-id="b7ea6-115">5,000</span></span>       |
|<span data-ttu-id="b7ea6-116">グローバル管理者を作成できるチームの数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="b7ea6-117">500,000</span><span class="sxs-lookup"><span data-stu-id="b7ea6-117">500,000</span></span>   |
|<span data-ttu-id="b7ea6-118">Office 365 テナントが持てるチームの数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="b7ea6-119">50万&sup2;</span><span class="sxs-lookup"><span data-stu-id="b7ea6-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="b7ea6-120">チームごとのチャネル数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-120">Number of channels per team</span></span>    | <span data-ttu-id="b7ea6-121">200 (削除されたチャンネルを含む) &sup3;</span><span class="sxs-lookup"><span data-stu-id="b7ea6-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="b7ea6-122">&sup1; Azure Active Directory の任意のディレクトリ オブジェクトは、この制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="b7ea6-123">グローバル管理者は、[アプリケーションのアクセス許可](https://docs.microsoft.com/graph/permissions-reference)を使用して Microsoft Graph を呼び出すアプリと同様に、この制限から除外されます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="b7ea6-124">&sup2;この制限には、アーカイブされたチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="b7ea6-125">&sup3; 削除されたチャンネルは、30日以内に復元できます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="b7ea6-126">30日以内に、削除されたチャネルは、チームの上限に対して200チャネルに対してカウントされ続けます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="b7ea6-127">30日が経過すると、削除されたチャネルとそのコンテンツは完全に削除され、チャネルはチームの制限に従って200チャネルにカウントされなくなります。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="messaging"></a><span data-ttu-id="b7ea6-128">メッセージング </span><span class="sxs-lookup"><span data-stu-id="b7ea6-128">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="b7ea6-129">チャット</span><span class="sxs-lookup"><span data-stu-id="b7ea6-129">Chat</span></span>

<span data-ttu-id="b7ea6-130">チームのチャットリストの一部である会話に参加するユーザーには、管理者がチャットの会話を検索するための Exchange Online (クラウドベース) のメールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-130">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="b7ea6-131">これは、チャットリストに含まれている会話が、チャット参加者のクラウドベースのメールボックスに保存されているためです。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-131">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="b7ea6-132">チャット参加者が Exchange Online メールボックスを持っていない場合、管理者はチャットの会話を検索または保留することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-132">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="b7ea6-133">たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャットリストの一部である会話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-133">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="b7ea6-134">ただし、この例では、ユーザーがクラウド ベースのメールボックスを持っていないために、これらの会話のコンテンツを検索できないし、保留することもできません。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-134">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="b7ea6-135">(詳しくは、[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="b7ea6-135">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="b7ea6-136">Teams chat は Microsoft Exchange バックエンドで動作するため、Exchange メッセージングの制限が Teams 内のチャット機能に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-136">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="b7ea6-137">機能</span><span class="sxs-lookup"><span data-stu-id="b7ea6-137">Feature</span></span>  | <span data-ttu-id="b7ea6-138">上限</span><span class="sxs-lookup"><span data-stu-id="b7ea6-138">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="b7ea6-139">プライベートチャット<sup>1</sup>の参加者数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-139">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="b7ea6-140">100</span><span class="sxs-lookup"><span data-stu-id="b7ea6-140">100</span></span>    |
|<span data-ttu-id="b7ea6-141">添付ファイルの数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b7ea6-141">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="b7ea6-142">常用</span><span class="sxs-lookup"><span data-stu-id="b7ea6-142">10</span></span>     |

<span data-ttu-id="b7ea6-143"><sup>1</sup>チャットで参加者が20人を超える場合は、次のチャット機能がオフになります: Outlook の自動返信とチームの状態メッセージ入力状態のインジケータービデオ通話と音声通話共用開封確認メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-143"><sup>1</sup>If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="b7ea6-144"><sup>2</sup>添付ファイルの数がこの制限を超えている場合は、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-144"><sup>2</sup>If the number of attachments exceeds this limit, you'll see an error message.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="b7ea6-145">チャネルをメールで送信する</span><span class="sxs-lookup"><span data-stu-id="b7ea6-145">Emailing a channel</span></span>

 <span data-ttu-id="b7ea6-146">ユーザーが Teams のチャネルにメールを送信する場合、チャネルのメール アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-146">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="b7ea6-147">メールがチャネルの一部になっている場合、全員に返信して会話を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-147">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="b7ea6-148">チャネルにメールを送信するための適用可能な制限の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-148">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="b7ea6-149">機能</span><span class="sxs-lookup"><span data-stu-id="b7ea6-149">Feature</span></span>  | <span data-ttu-id="b7ea6-150">上限</span><span class="sxs-lookup"><span data-stu-id="b7ea6-150">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="b7ea6-151">メッセージサイズ<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="b7ea6-151">Message size<sup>1<sup></span></span> | <span data-ttu-id="b7ea6-152">24 KB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-152">24 KB</span></span> |
|<span data-ttu-id="b7ea6-153">添付ファイルの数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b7ea6-153">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="b7ea6-154">超える</span><span class="sxs-lookup"><span data-stu-id="b7ea6-154">20</span></span>     |
|<span data-ttu-id="b7ea6-155">各添付ファイルのサイズ</span><span class="sxs-lookup"><span data-stu-id="b7ea6-155">Size of each file attachment</span></span> | <span data-ttu-id="b7ea6-156">10 MB 未満</span><span class="sxs-lookup"><span data-stu-id="b7ea6-156">Less than 10 MB</span></span> |
|<span data-ttu-id="b7ea6-157">インライン画像の数<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b7ea6-157">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="b7ea6-158">50</span><span class="sxs-lookup"><span data-stu-id="b7ea6-158">50</span></span>   |

<span data-ttu-id="b7ea6-159"><sup>1</sup>メッセージがこの制限を超えると、プレビューメッセージが生成され、提供されたリンクから元のメールをダウンロードして表示するように求められます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-159"><sup>1</sup>If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="b7ea6-160"><sup>2</sup>添付ファイルまたは画像の数がこの制限を超えると、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-160"><sup>2</sup>If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="b7ea6-161">詳細については、[「 Exchange Online の制限 」](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-161">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="b7ea6-162">すべての Office 365 ライセンスで、メッセージサイズ、添付ファイル、インライン画像の制限は同じです。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-162">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="b7ea6-163">チャネル名</span><span class="sxs-lookup"><span data-stu-id="b7ea6-163">Channel names</span></span>

<span data-ttu-id="b7ea6-164">チャネル名には、次の文字または単語を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-164">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="b7ea6-165">アルファベット</span><span class="sxs-lookup"><span data-stu-id="b7ea6-165">Characters</span></span>     | <span data-ttu-id="b7ea6-166">~ #% & \* {} +/\:  < > ?</span><span class="sxs-lookup"><span data-stu-id="b7ea6-166">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="b7ea6-167">&#124; ' "..</span><span class="sxs-lookup"><span data-stu-id="b7ea6-167">&#124; ' " ..</span></span>        |
|<span data-ttu-id="b7ea6-168">これらの範囲に含まれる文字</span><span class="sxs-lookup"><span data-stu-id="b7ea6-168">Characters in these ranges</span></span>    | <span data-ttu-id="b7ea6-169">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="b7ea6-169">0 to 1F</span></span><br><span data-ttu-id="b7ea6-170">80から9F</span><span class="sxs-lookup"><span data-stu-id="b7ea6-170">80 to 9F</span></span>        |
|<span data-ttu-id="b7ea6-171">いう</span><span class="sxs-lookup"><span data-stu-id="b7ea6-171">Words</span></span>     | <span data-ttu-id="b7ea6-172">フォーム、CON、CONIN $、CONIN $、PRN、AUX、NUL、COM1 から COM9、LPT1 から LPT9、desktop.ini、&#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="b7ea6-172">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="b7ea6-173">チャネル名には、アンダースコア (_) またはピリオド (.) で始めることも、ピリオド (.) で終わらせることもできません。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-173">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="b7ea6-174">会議と通話</span><span class="sxs-lookup"><span data-stu-id="b7ea6-174">Meetings and calls</span></span>

|<span data-ttu-id="b7ea6-175">機能</span><span class="sxs-lookup"><span data-stu-id="b7ea6-175">Feature</span></span>     | <span data-ttu-id="b7ea6-176">上限</span><span class="sxs-lookup"><span data-stu-id="b7ea6-176">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="b7ea6-177">会議に参加できるユーザー数</span><span class="sxs-lookup"><span data-stu-id="b7ea6-177">Number of people in a meeting</span></span>  | <span data-ttu-id="b7ea6-178">250</span><span class="sxs-lookup"><span data-stu-id="b7ea6-178">250</span></span>    |

## <a name="teams-live-events"></a><span data-ttu-id="b7ea6-179">Teams ライブイベント</span><span class="sxs-lookup"><span data-stu-id="b7ea6-179">Teams live events</span></span>

|<span data-ttu-id="b7ea6-180">機能</span><span class="sxs-lookup"><span data-stu-id="b7ea6-180">Feature</span></span>     | <span data-ttu-id="b7ea6-181">上限</span><span class="sxs-lookup"><span data-stu-id="b7ea6-181">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="b7ea6-182">対象ユーザーのサイズ</span><span class="sxs-lookup"><span data-stu-id="b7ea6-182">Audience size</span></span> | <span data-ttu-id="b7ea6-183">出席者 10,000 名</span><span class="sxs-lookup"><span data-stu-id="b7ea6-183">10,000 attendees</span></span> |
|<span data-ttu-id="b7ea6-184">イベントの期間</span><span class="sxs-lookup"><span data-stu-id="b7ea6-184">Duration of event</span></span> | <span data-ttu-id="b7ea6-185">4 時間</span><span class="sxs-lookup"><span data-stu-id="b7ea6-185">4 hours</span></span> |
|<span data-ttu-id="b7ea6-186">Office 365 テナントでの同時ライブイベント</span><span class="sxs-lookup"><span data-stu-id="b7ea6-186">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="b7ea6-187">マート</span><span class="sxs-lookup"><span data-stu-id="b7ea6-187">15</span></span> |

<span data-ttu-id="b7ea6-188">ライブイベントと、Teams ライブイベントと Skype 会議ブロードキャストの比較の詳細については、「 [teams live イベント」および「Skype 会議ブロードキャスト](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-188">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="storage"></a><span data-ttu-id="b7ea6-189">ストレージ</span><span class="sxs-lookup"><span data-stu-id="b7ea6-189">Storage</span></span>

<span data-ttu-id="b7ea6-p106">Microsoft Teams の各チームには SharePoint Online にチーム サイトがあり、チーム内の各チャネルには既定のチーム サイト ドキュメント ライブラリが作成されます。会話内で共有したファイルはドキュメント ライブラリに自動的に格納されます。SharePoint で設定した権限やファイル セキュリティ オプションは Teams 内で自動的に反映されます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-p106">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="b7ea6-192">テナントで有効な SharePoint Online をお持ちでない場合は、 Microsoft Teams ユーザーがチーム内のファイルを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-192">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="b7ea6-193">プライベート チャット内のユーザーもファイルを共有できません。これは OneDrive for Business (SharePoint のライセンスに関連付けられています) がその機能に必要だからです。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-193">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="b7ea6-194">SharePoint Online ドキュメント ライブラリと OneDrive for Business にファイルを格納することで、テナントレベルで構成されるすべてのコンプライアンス ルールが順守されます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-194">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="b7ea6-195">(詳しくは、[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)をご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="b7ea6-195">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="b7ea6-196">Team は、SharePoint Online のバックエンドのファイル共有で実行しているために、SharePoint の制限は、Team 内のファイルのセクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-196">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="b7ea6-197">ここでは、SharePoint Online の適用可能な記憶域の制限を示します。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-197">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="b7ea6-198">機能</span><span class="sxs-lookup"><span data-stu-id="b7ea6-198">Feature</span></span>                 |<span data-ttu-id="b7ea6-199">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="b7ea6-199">Office 365 Business Essentials</span></span>  |<span data-ttu-id="b7ea6-200">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b7ea6-200">Office 365 Business Premium</span></span>   |<span data-ttu-id="b7ea6-201">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b7ea6-201">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="b7ea6-202">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b7ea6-202">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="b7ea6-203">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="b7ea6-203">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="b7ea6-204">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="b7ea6-204">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="b7ea6-205">ストレージ</span><span class="sxs-lookup"><span data-stu-id="b7ea6-205">Storage</span></span>                 |<span data-ttu-id="b7ea6-206">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-206">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="b7ea6-207">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-207">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="b7ea6-208">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-208">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="b7ea6-209">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-209">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="b7ea6-210">1 組織につき 1 TB、さらに購入したライセンスごとに 10 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-210">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="b7ea6-211">1 組織につき 1 TB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-211">1 TB per organization</span></span>           |
|<span data-ttu-id="b7ea6-212">Teams ファイル用のストレージ</span><span class="sxs-lookup"><span data-stu-id="b7ea6-212">Storage for Teams Files</span></span> |<span data-ttu-id="b7ea6-213">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-213">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b7ea6-214">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-214">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b7ea6-215">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-215">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b7ea6-216">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-216">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b7ea6-217">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-217">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="b7ea6-218">サイト コレクションまたはグループあたり最大 25 TB。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-218">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="b7ea6-219">ファイルアップロードの上限 (ファイル単位)</span><span class="sxs-lookup"><span data-stu-id="b7ea6-219">File upload limit  (per file)</span></span>    |<span data-ttu-id="b7ea6-220">15 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-220">15 GB</span></span>    |<span data-ttu-id="b7ea6-221">15 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-221">15 GB</span></span>    |<span data-ttu-id="b7ea6-222">15 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-222">15 GB</span></span>    |<span data-ttu-id="b7ea6-223">15 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-223">15 GB</span></span>    |<span data-ttu-id="b7ea6-224">15 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-224">15 GB</span></span>    |<span data-ttu-id="b7ea6-225">15 GB</span><span class="sxs-lookup"><span data-stu-id="b7ea6-225">15 GB</span></span>    |

<span data-ttu-id="b7ea6-226">チャネルは、チーム用に作成された SharePoint Online サイトコレクション内のフォルダーによってサポートされるため、チャネル内のファイルタブは、所属するチームの記憶域制限を共有します。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-226">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="b7ea6-227">詳細については、「[SharePoint Online の制限事項](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-227">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="contacts"></a><span data-ttu-id="b7ea6-228">連絡先</span><span class="sxs-lookup"><span data-stu-id="b7ea6-228">Contacts</span></span>

<span data-ttu-id="b7ea6-229">チームは以下の連絡先を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-229">Teams uses these contacts:</span></span>

- <span data-ttu-id="b7ea6-230">組織の Active Directory の連絡先</span><span class="sxs-lookup"><span data-stu-id="b7ea6-230">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="b7ea6-231">ユーザーの Outlook の既定フォルダーに追加された連絡先</span><span class="sxs-lookup"><span data-stu-id="b7ea6-231">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="b7ea6-232">Teams ユーザーは、組織の active directory 内のユーザーと通信でき、組織の active directory のすべてのユーザーを連絡先として、また\*\*\*\*  > は連絡先リスト\*\*\*\* > \*\*\*\* に追加することができます。**コンタクト**。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-232">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="b7ea6-233">チームユーザーは、[ \*\*\*\* > **連絡先**に発信] に移動して、組織の Active Directory に含まれていないユーザーを連絡先として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-233">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="b7ea6-234">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="b7ea6-234">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="b7ea6-235">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b7ea6-235">Operating systems</span></span>

<span data-ttu-id="b7ea6-236">各オペレーティング システムの要件については、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7ea6-236">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
