---
title: コンテンツの電子情報開示調査を実施する
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 法的手続きのためにすべての電子的に保存された情報を送信する必要がある場合など、電子情報開示を実行する必要がある場合の操作について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ca1a679fbdce7ca2840c41266053cf13f1452fe0
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197532"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="40c48-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="40c48-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="40c48-104">多くの場合、大企業は、すべての電子的に保存された情報 (ESI) の提出を要求する高いペナルティ訴訟手続きにさらされます。</span><span class="sxs-lookup"><span data-stu-id="40c48-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="40c48-105">Microsoft Teamsコンテンツは、電子情報開示調査中に検索して使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="40c48-106">概要</span><span class="sxs-lookup"><span data-stu-id="40c48-106">Overview</span></span>

<span data-ttu-id="40c48-107">すべてのMicrosoft Teams 1:1 またはグループ チャットは、それぞれのユーザーのメールボックスにジャーナルされます。</span><span class="sxs-lookup"><span data-stu-id="40c48-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="40c48-108">すべての標準チャネル メッセージは、チームを表すグループ メールボックスにジャーナルされます。</span><span class="sxs-lookup"><span data-stu-id="40c48-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="40c48-109">標準チャネルでアップロードされたファイルは、SharePoint Online および OneDrive for Business の電子情報開示機能の下で扱OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="40c48-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="40c48-110">プライベート チャネルでのメッセージとファイルの電子情報開示 [は、](private-channels.md) 標準チャネルとは異なる方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="40c48-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="40c48-111">詳細については、「プライベート チャネルの [電子情報開示」を参照してください](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="40c48-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="40c48-112">すべてのコンテンツTeams eDiscoverable ではありません。</span><span class="sxs-lookup"><span data-stu-id="40c48-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="40c48-113">次の表は、Microsoft 電子情報開示ツールを使用して検索できるコンテンツ タイプを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c48-113">The following table shows the content types that you can search for using Microsoft eDiscovery tools:</span></span>

| <span data-ttu-id="40c48-114">コンテンツの種類</span><span class="sxs-lookup"><span data-stu-id="40c48-114">Content type</span></span> | <span data-ttu-id="40c48-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="40c48-115">eDiscoverable</span></span> | <span data-ttu-id="40c48-116">備考</span><span class="sxs-lookup"><span data-stu-id="40c48-116">Notes</span></span> |
|:--- | :--- |:--- |
|<span data-ttu-id="40c48-117">オーディオ録音</span><span class="sxs-lookup"><span data-stu-id="40c48-117">Audio recordings</span></span> | <span data-ttu-id="40c48-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="40c48-118">No</span></span> | |
|<span data-ttu-id="40c48-119">カードの内容</span><span class="sxs-lookup"><span data-stu-id="40c48-119">Card content</span></span>|<span data-ttu-id="40c48-120">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-120">Yes</span></span>|<span data-ttu-id="40c48-121">詳細については [、「カードコンテンツを検索する](#search-for-card-content) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c48-121">See [Search for card content](#search-for-card-content) for more information.</span></span>|
|<span data-ttu-id="40c48-122">チャット リンク</span><span class="sxs-lookup"><span data-stu-id="40c48-122">Chat links</span></span> | <span data-ttu-id="40c48-123">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-123">Yes</span></span> | |
|<span data-ttu-id="40c48-124">チャット メッセージ</span><span class="sxs-lookup"><span data-stu-id="40c48-124">Chat messages</span></span> | <span data-ttu-id="40c48-125">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-125">Yes</span></span> |<span data-ttu-id="40c48-126">これには、Teams チャネルのコンテンツ、1 対 1 のチャット、1:N グループ チャット、ゲスト ユーザー参加者とのチャットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="40c48-126">This includes content in Teams channels, 1:1 chats, 1:N group chats, and chats with guest user participants.</span></span>  |
|<span data-ttu-id="40c48-127">コード スニペット</span><span class="sxs-lookup"><span data-stu-id="40c48-127">Code snippets</span></span> | <span data-ttu-id="40c48-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="40c48-128">No</span></span> | |
|<span data-ttu-id="40c48-129">編集されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="40c48-129">Edited messages</span></span> | <span data-ttu-id="40c48-130">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-130">Yes</span></span> | <span data-ttu-id="40c48-131">ユーザーが保留の場合、以前のバージョンの編集されたメッセージも保持されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-131">If the user is on hold, previous versions of edited messages are also preserved.</span></span> |
|<span data-ttu-id="40c48-132">絵文字、GIF、ステッカー</span><span class="sxs-lookup"><span data-stu-id="40c48-132">Emojis, GIFs, and stickers</span></span> | <span data-ttu-id="40c48-133">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-133">Yes</span></span> | |
|<span data-ttu-id="40c48-134">インライン 画像</span><span class="sxs-lookup"><span data-stu-id="40c48-134">Inline images</span></span> | <span data-ttu-id="40c48-135">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-135">Yes</span></span> | |
|<span data-ttu-id="40c48-136">IM 会話を会議する</span><span class="sxs-lookup"><span data-stu-id="40c48-136">Meeting IM conversations</span></span> | <span data-ttu-id="40c48-137">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-137">Yes</span></span> | |
|<span data-ttu-id="40c48-138">会議メタデータ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="40c48-138">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="40c48-139">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-139">Yes</span></span> |  |
|<span data-ttu-id="40c48-140">チャネルの名前</span><span class="sxs-lookup"><span data-stu-id="40c48-140">Name of channel</span></span> | <span data-ttu-id="40c48-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="40c48-141">No</span></span> | |
|<span data-ttu-id="40c48-142">プライベート チャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="40c48-142">Private channel messages</span></span> | <span data-ttu-id="40c48-143">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-143">Yes</span></span> | |
|<span data-ttu-id="40c48-144">引用符</span><span class="sxs-lookup"><span data-stu-id="40c48-144">Quotes</span></span> | <span data-ttu-id="40c48-145">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-145">Yes</span></span> | <span data-ttu-id="40c48-146">引用符で囲まれたコンテンツは検索可能です。</span><span class="sxs-lookup"><span data-stu-id="40c48-146">Quoted content is searchable.</span></span> <span data-ttu-id="40c48-147">ただし、検索結果は、コンテンツが引用されたというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="40c48-147">However, search results don't indicate that the content was quoted.</span></span> |
|<span data-ttu-id="40c48-148">反応 (例: Likes、ハート、その他の反応)</span><span class="sxs-lookup"><span data-stu-id="40c48-148">Reactions (such as likes, hearts, and other reactions)</span></span> | <span data-ttu-id="40c48-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="40c48-149">No</span></span> | |
|<span data-ttu-id="40c48-150">件名</span><span class="sxs-lookup"><span data-stu-id="40c48-150">Subject</span></span> | <span data-ttu-id="40c48-151">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-151">Yes</span></span> | |
|<span data-ttu-id="40c48-152">テーブル</span><span class="sxs-lookup"><span data-stu-id="40c48-152">Tables</span></span> | <span data-ttu-id="40c48-153">はい</span><span class="sxs-lookup"><span data-stu-id="40c48-153">Yes</span></span> | |
|<span data-ttu-id="40c48-154">フィード通知</span><span class="sxs-lookup"><span data-stu-id="40c48-154">Feed notifications</span></span> | <span data-ttu-id="40c48-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="40c48-155">No</span></span> | |
|||

<span data-ttu-id="40c48-156"><sup>1 会議</sup> (および通話) メタデータには、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="40c48-156"><sup>1</sup> Meeting (and call) metadata includes the following:</span></span>

- <span data-ttu-id="40c48-157">会議の開始時刻と終了時刻、および期間</span><span class="sxs-lookup"><span data-stu-id="40c48-157">Meeting start and end time, and duration</span></span>
- <span data-ttu-id="40c48-158">各参加者の会議への参加と退出のイベント</span><span class="sxs-lookup"><span data-stu-id="40c48-158">Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="40c48-159">VOIP 参加/通話</span><span class="sxs-lookup"><span data-stu-id="40c48-159">VOIP join/calls</span></span>
- <span data-ttu-id="40c48-160">匿名結合</span><span class="sxs-lookup"><span data-stu-id="40c48-160">Anonymous join</span></span>
- <span data-ttu-id="40c48-161">フェデレーション ユーザー参加</span><span class="sxs-lookup"><span data-stu-id="40c48-161">Federated user join</span></span>
- <span data-ttu-id="40c48-162">ゲスト ユーザー参加</span><span class="sxs-lookup"><span data-stu-id="40c48-162">Guest user join</span></span>

  <span data-ttu-id="40c48-163">この画像は、会議メタデータの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="40c48-163">The image shows an example of meeting metadata.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="40c48-164">![画像は、CVR レコード会議メタデータの画像です。](media/conversationOption3.png)</span><span class="sxs-lookup"><span data-stu-id="40c48-164">![Image is of the CVR records meeting metadata.](media/conversationOption3.png)</span></span>

<span data-ttu-id="40c48-165">会議中の参加者間の IM 会話の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40c48-165">Here's an example of an IM conversation between participants during the meeting.</span></span>

![Teams での参加者間の会話。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="40c48-167">![電子情報開示検索結果の参加者間の会話。](media/MeetingImConversation2.png)</span><span class="sxs-lookup"><span data-stu-id="40c48-167">![Conversation between participants in eDiscovery search results.](media/MeetingImConversation2.png)</span></span>

<span data-ttu-id="40c48-168">電子情報開示調査の実施の詳細については、「Core eDiscovery の概要 [」を参照してください](/microsoft-365/compliance/get-started-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="40c48-168">For more information about conducting an eDiscovery investigation, see [Get started with Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="40c48-169">Microsoft Teams電子情報開示のエクスポート出力に、データが IM または会話Excel表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-169">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="40c48-170">ファイルをエクスポートした `.pst` 後、Outlookファイルを開き、それらのメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-170">You can open the `.pst` file in Outlook to view those messages after you export them.</span></span>

<span data-ttu-id="40c48-171">チームの .pst ファイルを表示すると、すべての会話が [会話履歴] の [チーム チャット] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-171">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="40c48-172">メッセージのタイトルには、チーム名とチャネル名が含まれている。</span><span class="sxs-lookup"><span data-stu-id="40c48-172">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="40c48-173">たとえば、次の図は、製造仕様チームの Project 7 標準チャネルにメッセージを送信した Bob からのメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c48-173">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![グループ内のユーザーのメールボックス内のチーム チャット フォルダーのスクリーンショットOutlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="40c48-175">ユーザーのメールボックス内のプライベート チャットは、[会話履歴] の [チーム チャット] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-175">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="40c48-176">プライベート チャネルの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="40c48-176">eDiscovery of private channels</span></span>

<span data-ttu-id="40c48-177">プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-177">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="40c48-178">レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="40c48-178">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="40c48-179">各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイトが用意されています。プライベート チャネル内のファイルは、親チームとは独立して管理されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-179">Because each private channel has its own SharePoint site that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="40c48-180">Teamsは、チーム内の 1 つのチャネルの電子情報開示検索をサポートしないので、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c48-180">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="40c48-181">プライベート チャネル内のコンテンツの電子情報開示検索を実行するには、チーム全体、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含める)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。</span><span class="sxs-lookup"><span data-stu-id="40c48-181">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="40c48-182">次の手順を使用して、電子情報開示検索に含めるプライベート チャネル内のファイルとメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="40c48-182">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="40c48-183">電子情報開示検索にプライベート チャネル ファイルを含める</span><span class="sxs-lookup"><span data-stu-id="40c48-183">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="40c48-184">これらの手順を実行する前に、SharePoint Online Management Shell をインストールし、SharePoint [Online に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="40c48-184">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

1. <span data-ttu-id="40c48-185">次のコマンドを実行して、チーム内のプライベート SharePointに関連付けられているすべてのサイト コレクションの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="40c48-185">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="40c48-186">次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルSharePoint関連付けられているすべてのサイト コレクション URL と親チーム グループ ID の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="40c48-186">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="40c48-187">各チームまたはグループ ID について、次の PowerShell スクリプトを実行して、関連するすべてのプライベート チャネル サイトを識別します。$groupID はチームのグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="40c48-187">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="40c48-188">電子情報開示検索にプライベート チャネル メッセージを含める</span><span class="sxs-lookup"><span data-stu-id="40c48-188">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="40c48-189">これらの手順を実行する前に、PowerShell モジュールの最新バージョンが[インストールTeams確認](teams-powershell-overview.md)してください。</span><span class="sxs-lookup"><span data-stu-id="40c48-189">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="40c48-190">次のコマンドを実行して、チーム内のプライベート チャネルの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="40c48-190">Run the following command to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="40c48-191">次のコマンドを実行して、プライベート チャネル メンバーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="40c48-191">Run the following command to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="40c48-192">電子情報開示検索クエリの一部として、チーム内の各プライベート チャネルのすべてのメンバーの [メールボックスを含める](/microsoft-365/compliance/search-for-content-in-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="40c48-192">Include the mailboxes of all members from each private channel in the team as part of your [eDiscovery search query](/microsoft-365/compliance/search-for-content-in-core-ediscovery).</span></span>

## <a name="search-for-content-for-guest-users"></a><span data-ttu-id="40c48-193">ゲスト ユーザーのコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="40c48-193">Search for content for guest users</span></span>

<span data-ttu-id="40c48-194">電子情報開示ツールを使用して、組織内のゲスト Teams関連するコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-194">You can use eDiscovery tools to search for Teams content related to guest users in your organization.</span></span> <span data-ttu-id="40c48-195">Teamsに関連付けられているチャット コンテンツは、クラウドベースの保存場所に保持され、電子情報開示を使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-195">Teams chat content that's associated with a guest user is preserved in a cloud-based storage location and can be searched for using eDiscovery.</span></span> <span data-ttu-id="40c48-196">これには、ゲスト ユーザーが組織内の他のユーザーと参加者である 1:1 と 1:N のチャット会話のコンテンツの検索が含まれます。</span><span class="sxs-lookup"><span data-stu-id="40c48-196">This includes searching for content in 1:1 and 1:N chat conversations in which a guest user is a participant with other users in your organization.</span></span> <span data-ttu-id="40c48-197">ゲスト ユーザーが参加者であるプライベート チャネル メッセージを検索し、ゲスト *と* ゲスト チャットの会話でコンテンツを検索することもできます。この会話では、参加者はゲスト ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="40c48-197">You can also search for private channel messages in which a guest user is a participant and search for content in *guest:guest* chat conversations where the only participants are guest users.</span></span>

<span data-ttu-id="40c48-198">ゲスト ユーザーのコンテンツを検索するには:</span><span class="sxs-lookup"><span data-stu-id="40c48-198">To search for content for guest users:</span></span>

1. <span data-ttu-id="40c48-199">Connect Azure AD PowerShell にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="40c48-199">Connect to Azure AD PowerShell.</span></span> <span data-ttu-id="40c48-200">手順については、「PowerShell を使用したConnect」の「Azure Active Directory PowerShell での[Connect」Microsoft 365を参照してください](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="40c48-200">For instructions, see the "Connect with the Azure Active Directory PowerShell" section in [Connect to Microsoft 365 with PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="40c48-201">前のトピックの手順 1 と手順 2 を必ず完了してください。</span><span class="sxs-lookup"><span data-stu-id="40c48-201">Be sure to complete Step 1 and Step 2 in the previous topic.</span></span>

2. <span data-ttu-id="40c48-202">Azure AD PowerShell に正常に接続したら、次のコマンドを実行して、組織内のすべてのゲスト ユーザーのユーザー プリンシパル名 (UPN) を表示します。</span><span class="sxs-lookup"><span data-stu-id="40c48-202">After you successfully connect to Azure AD PowerShell, run the following command to display the user principal name (UPN) for all guest users in your organization.</span></span> <span data-ttu-id="40c48-203">手順 4 で検索を作成するときに、ゲスト ユーザーの UPN を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c48-203">You have to use the UPN of the guest user when you create the search in step 4.</span></span>

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > <span data-ttu-id="40c48-204">コンピューターの画面にユーザー プリンシパル名の一覧を表示する代わりに、コマンドの出力をテキスト ファイルにリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-204">Instead of displaying a list of user principal names on the computer screen, you can redirect the output of the command to a text file.</span></span> <span data-ttu-id="40c48-205">これを行うには、前のコマンド `> filename.txt` に を追加します。</span><span class="sxs-lookup"><span data-stu-id="40c48-205">You can do this by appending `> filename.txt` to the previous command.</span></span> <span data-ttu-id="40c48-206">ユーザー プリンシパル名を持つテキスト ファイルは、現在のフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-206">The text file with the user principal names will be saved to the current folder.</span></span>

3. <span data-ttu-id="40c48-207">別のウィンドウWindows PowerShell、Security & Compliance Center PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="40c48-207">In a different Windows PowerShell window, connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="40c48-208">手順については、「Security [Connect Compliance Center PowerShell &」を参照してください](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="40c48-208">For instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="40c48-209">多要素認証を使用する場合と接続せずに接続できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-209">You can connect with or without using multi-factor authentication.</span></span>

4. <span data-ttu-id="40c48-210">次のコマンドを実行して、指定されたゲスト ユーザーが参加者だったすべてのコンテンツ (チャット メッセージやメール メッセージなど) を検索するコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="40c48-210">Create a content search that searches for all content (such as chat messages and email messages) in which the specified guest user was a participant by running the following command.</span></span>

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   <span data-ttu-id="40c48-211">たとえば、ゲスト ユーザー Sara Davis に関連付けられているコンテンツを検索するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40c48-211">For example, to search for content associated with the guest user Sara Davis, you would run the following command.</span></span>

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    <span data-ttu-id="40c48-212">PowerShell を使用してコンテンツ検索を作成する方法の詳細については [、New-ComplianceSearch に関するページを参照してください](/powershell/module/exchange/new-compliancesearch)。</span><span class="sxs-lookup"><span data-stu-id="40c48-212">For more information about using PowerShell to create content searches, see [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).</span></span>

5. <span data-ttu-id="40c48-213">次のコマンドを実行して、手順 4 で作成したコンテンツ検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="40c48-213">Run the following command to start the content search that you created in step 4:</span></span>

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. <span data-ttu-id="40c48-214">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com) 、[すべてのコンテンツ検索 **を表示]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="40c48-214">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Show all** > **Content search**.</span></span>

7. <span data-ttu-id="40c48-215">検索の一覧で、手順 4 で作成した検索を選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="40c48-215">In the list of searches, select the search that you created in step 4 to display the flyout page.</span></span>

8. <span data-ttu-id="40c48-216">フライアウト ページでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="40c48-216">On the flyout page, you can do the following things:</span></span>

   - <span data-ttu-id="40c48-217">[ **結果の表示]** をクリックして検索結果を表示し、コンテンツをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="40c48-217">Click **View results** to view the search results and preview the content.</span></span>

   - <span data-ttu-id="40c48-218">[クエリ] **フィールドの横** にある [編集] **をクリック** して編集し、検索を再実行します。</span><span class="sxs-lookup"><span data-stu-id="40c48-218">Next to the **Query** field, click **Edit** to edit and then rerun the search.</span></span> <span data-ttu-id="40c48-219">たとえば、検索クエリを追加して結果を絞り込むなどです。</span><span class="sxs-lookup"><span data-stu-id="40c48-219">For example, you can add a search query to narrow the results.</span></span>

   - <span data-ttu-id="40c48-220">[結果 **のエクスポート]** をクリックして、検索結果をエクスポートしてダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="40c48-220">Click **Export results** to export and download the search results.</span></span>

## <a name="search-for-card-content"></a><span data-ttu-id="40c48-221">カードコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="40c48-221">Search for card content</span></span>

<span data-ttu-id="40c48-222">Teams チャネル、1 対 1 のチャット、1xN チャットのアプリによって生成されたカード コンテンツはメールボックスに格納され、検索できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-222">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="40c48-223">カード *は* 、短いコンテンツの UI コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="40c48-223">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="40c48-224">カードには複数のプロパティと添付ファイルを含め、カードアクションをトリガーできるボタンを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="40c48-224">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="40c48-225">詳細については、「カード」を [参照してください。](/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span><span class="sxs-lookup"><span data-stu-id="40c48-225">For more information, see [Cards](/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

<span data-ttu-id="40c48-226">他のTeamsコンテンツと同様に、カードコンテンツが格納される場所は、カードが使用された場所に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="40c48-226">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="40c48-227">チャネルで使用されるカードのTeamsは、グループ メールボックスTeams保存されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-227">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="40c48-228">1 対 1 および 1xN のチャットのカード コンテンツは、チャット参加者のメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-228">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

<span data-ttu-id="40c48-229">カードコンテンツを検索するには、 または 検索条件 `kind:microsoftteams` を `itemclass:IPM.SkypeTeams.Message` 使用します。</span><span class="sxs-lookup"><span data-stu-id="40c48-229">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="40c48-230">検索結果を確認すると、Teams チャネル内のボットによって生成されたカード コンテンツは **、Sender/Author** メール プロパティとして として設定されます。ここでは、カード コンテンツを生成したアプリの名前です `<appname>@teams.microsoft.com` `appname` 。</span><span class="sxs-lookup"><span data-stu-id="40c48-230">When reviewing search results, card content generated by bots in a Teams channel has the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="40c48-231">カードコンテンツがユーザーによって生成された場合 **、Sender/Author** の値はユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="40c48-231">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

<span data-ttu-id="40c48-232">コンテンツ検索結果でカードコンテンツを表示すると、そのコンテンツがメッセージの添付ファイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-232">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="40c48-233">添付ファイルの名前 `appname.html` は です。 `appname` ここでは、カードコンテンツを生成したアプリの名前です。</span><span class="sxs-lookup"><span data-stu-id="40c48-233">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="40c48-234">次のスクリーンショットは、(Asana という名前のアプリの) カード コンテンツが検索の結果Teamsに表示される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="40c48-234">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

<span data-ttu-id="40c48-235">**Teams 内のカードのTeams**</span><span class="sxs-lookup"><span data-stu-id="40c48-235">**Card content in Teams**</span></span>

![チャネル メッセージのTeamsコンテンツ](media/CardContentTeams.png)

<span data-ttu-id="40c48-237">**検索結果のカード コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="40c48-237">**Card content in search results**</span></span>
  
![コンテンツ検索の結果と同じカード コンテンツ](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> <span data-ttu-id="40c48-239">この時点でカードコンテンツの画像を検索結果に表示するには (前のスクリーンショットのチェックマークなど)、(検索結果の表示に使用したのと同じブラウザー セッションの別のタブにある) Teams にサインインする必要があります。 https://teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="40c48-239">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="40c48-240">それ以外の場合は、画像プレースホルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-240">Otherwise, image placeholders are displayed.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="40c48-241">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="40c48-241">Advanced eDiscovery</span></span>

<span data-ttu-id="40c48-242">一部Microsoft Teamsは、ワークフロー を使用して検索[および保持Advanced eDiscoveryできます](/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="40c48-242">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="40c48-243">電子情報開示は、さまざまな検索、保留、エクスポート機能を提供しますが、Advanced eDiscovery では、コンプライアンス管理者はデータ ソースを識別し、その内容を分析するためのより多くのツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="40c48-243">While eDiscovery provides a range of search, hold, and export functionality, Advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="40c48-244">Advanced eDiscoveryコンテンツの管理Teamsワークフロー</span><span class="sxs-lookup"><span data-stu-id="40c48-244">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="40c48-245">管理人は、さまざまなチームのメンバーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40c48-245">Custodians might be a member of various teams.</span></span> <span data-ttu-id="40c48-246">これらの管理者にTeamsコンテンツをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-246">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="40c48-247">カストディアン ワークフローの手順については、「ケースに管理者を追加する[」をAdvanced eDiscoveryしてください](/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="40c48-247">For instructions on the custodian workflow, see [Add custodians to an Advanced eDiscovery case](/microsoft-365/compliance/add-custodians-to-case).</span></span>

<span data-ttu-id="40c48-248">管理人を追加したら、[次へ] ボタン **をクリック** し、[追加] **ボタンをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="40c48-248">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="40c48-249">ウィンドウが表示され、追加の場所を選択するように求めるメッセージが表示されます。このウィンドウには、管理人のすべてのメンバーシップと、そのデータに対応する SharePoint サイトの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-249">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="40c48-250">これらのすべてのデータ ソースとチームから、電子情報開示に使用するコンテンツを選択し、そのユーザーと、特定したすべてのデータ ソースを保留にできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-250">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="40c48-251">ユーザーのコンテンツを含めるか、ExchangeコンテンツOneDrive、または両方を含めるかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-251">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="40c48-252">Exchangeには、ユーザーのメールボックス内のすべてのアプリケーション コンテンツ (メール、メールボックスに格納されている Teams コンテンツなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="40c48-252">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="40c48-253">OneDrive コンテンツには、ユーザーのコンテンツだけでなく、1 対 1 のチャット、1:N チャット、チャットで共有されるファイルなど、OneDrive に保存されている Teams のすべてのコンテンツも含まれます。</span><span class="sxs-lookup"><span data-stu-id="40c48-253">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="40c48-254">また、管理人がメンバーであるチームを関連付け、管理人がアクセスできるチャネル チャット メッセージとファイルを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-254">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="40c48-255">さらに、他のすべてのチームを管理人に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-255">Additionally, any other team can be associated with a custodian.</span></span>

> [!NOTE]
> <span data-ttu-id="40c48-256">プライベート チャネルでのメッセージとファイルの電子情報開示 [は、](private-channels.md) 標準チャネルとは異なる方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="40c48-256">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="40c48-257">詳細については、「プライベート チャネルの [電子情報開示」を参照してください](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="40c48-257">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="40c48-258">データ ソースを保留する</span><span class="sxs-lookup"><span data-stu-id="40c48-258">Placing a data source on hold</span></span>

<span data-ttu-id="40c48-259">管理人として指定する特定のユーザーがいない場合は、データ ソース全体を保留にできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-259">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="40c48-260">保留の詳細については、「Manage [holds in Advanced eDiscovery 」を参照してください](/microsoft-365/compliance/managing-holds)。</span><span class="sxs-lookup"><span data-stu-id="40c48-260">For more information on holds, see [Manage holds in Advanced eDiscovery](/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="40c48-261">コンテンツの保留リストTeams、保留リストに含めるすべての場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-261">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="40c48-262">ユーザーがコンテンツを削除または変更している場合でも、保留は、そのコンテンツのすべての以前のバージョンのコピーを保持します。</span><span class="sxs-lookup"><span data-stu-id="40c48-262">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="40c48-263">オプションのクエリを使用して、キーワード、日付範囲、作成者、その他の多くの条件に基づいて保留の条件を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-263">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="40c48-264">キーワードを指定しない場合、そのデータ ソースからのすべてが保留の対象です。</span><span class="sxs-lookup"><span data-stu-id="40c48-264">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="40c48-265">Advanced eDiscovery検索</span><span class="sxs-lookup"><span data-stu-id="40c48-265">Advanced eDiscovery searches</span></span>

<span data-ttu-id="40c48-266">Teamsコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-266">Teams content can also be searched.</span></span> <span data-ttu-id="40c48-267">検索の詳細については、「ケースのデータ[を収集する」を参照Advanced eDiscovery。](/microsoft-365/compliance/collecting-data-for-ediscovery)</span><span class="sxs-lookup"><span data-stu-id="40c48-267">For more information on searches, see [Collect data for a case in Advanced eDiscovery](/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="40c48-268">1 つのメッセージが検索クエリと一致する場合、検索は会話全体を返します。</span><span class="sxs-lookup"><span data-stu-id="40c48-268">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="40c48-269">検索クエリを作成するときに、既に選択しているすべてのソースが検索されるカストディアンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-269">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="40c48-270">また、ユーザーにマップされていないサイトTeams、管理されていないソースを検索できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-270">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="40c48-271">オプションのクエリは、コンテンツ内で検索を絞り込むTeamsもあります。</span><span class="sxs-lookup"><span data-stu-id="40c48-271">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="40c48-272">検索を作成して選択すると、選択した検索に対して実行できる追加の詳細とアクションがウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-272">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="40c48-273">[統計情報]ボタンをクリックすると、場所の種類、コンテンツの元のソース、コンテンツがグループ メールボックス、個々のユーザー メールボックス、または SharePoint サイトに含かどうかに応じて内訳を含む、検索に関する統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-273">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="40c48-274">そのため、検索結果にどのソースが影響を受け取ったかの内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-274">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="40c48-275">また、クエリ ビュー **を** 使用して、結果にどのキーワードが影響を受け取ったのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-275">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="40c48-276">検索を完了した後、[結果を追加してレビューセット] ボタンをクリックし、レビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-276">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="40c48-277">レビュー セットの詳細については、この記事の後半の「レビュー セットの管理[」](/microsoft-365/compliance/managing-review-sets)および「Advanced eDiscoveryのワークフロー [」](#review-sets-workflow)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c48-277">For more information about review sets, see [Manage review sets in Advanced eDiscovery](/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="40c48-278">通常のレビュー セットと会話レビュー セット</span><span class="sxs-lookup"><span data-stu-id="40c48-278">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="40c48-279">レビュー セットに検索を追加するときに、通常のレビュー セットまたは会話レビュー セットから選択できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-279">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="40c48-280">通常のレビュー セットはエクスポートに似ています。コンテンツの個々 `.msg` のファイルTeams表示し、基本的なビューでコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="40c48-280">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="40c48-281">通常、他のソフトウェア ツールを使用して後でファイルを再処理する場合は、通常のレビュー セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="40c48-281">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="40c48-282">会話レビュー セットは、会話のより直感的でスレッド化されたビューを提供します。関連するメッセージが適切な順序で一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-282">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="40c48-283">![会話レビュー セットのスクリーンショット](media/conversationOptions2.png)</span><span class="sxs-lookup"><span data-stu-id="40c48-283">![Screenshot of conversation review set](media/conversationOptions2.png)</span></span>

<span data-ttu-id="40c48-284">redaction などの機能は、両方の種類のレビュー セットで使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-284">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="40c48-285">レビュー セットの詳細については、「高度な電子情報開示で [会話を確認する」を参照してください](/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="40c48-285">For more information about review sets, see [Review conversations in advanced eDiscovery](/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="40c48-286">コレクション オプション</span><span class="sxs-lookup"><span data-stu-id="40c48-286">Collection options</span></span>

<span data-ttu-id="40c48-287">レビュー セットに追加する場合、ウィンドウの [コレクション オプション]セクションのチェック ボックスとして、[会話の取得オプション] や [会話] Teams **があります**。</span><span class="sxs-lookup"><span data-stu-id="40c48-287">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="40c48-288">これらのオプションを有効にした場合、レビュー セットTeams含む個々のメッセージも、コンテキストのためにそれらを囲む追加のメッセージと一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-288">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="40c48-289">たとえば、クエリが特定であり、結果として返されるメッセージが 1 つしか返されていない場合、これらのオプションを有効にすると、クエリに一致したメッセージの後に続く複数のメッセージも返されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-289">For example, if your query is specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="40c48-290">クエリに一致するメッセージに対して追加のメッセージがコンテキストを提供するかどうかを判断するには、多くの論理条件が使用されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-290">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="40c48-291">たとえば、Teamsの場合、これらのオプションを有効にすると、メッセージがスレッド化される方法のために、親メッセージとすべての子メッセージが取得されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-291">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="40c48-292">メッセージのタイム スタンプもチェックされます。</span><span class="sxs-lookup"><span data-stu-id="40c48-292">Message time stamps are also checked.</span></span> <span data-ttu-id="40c48-293">メッセージがクエリと一致する場合、4 時間以内にメッセージの前に表示される隣接するメッセージ、または 4 時間以内に続く隣接するメッセージは会話の一部と見なされ、結果にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="40c48-293">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="40c48-294">検索クエリに一致するコンテキスト メッセージを確実に返す必要がある場合は、これらのオプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c48-294">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="40c48-295">すべてのコンテンツを収集するか、検索の日付範囲を広くして、クエリの結果として返されるメッセージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-295">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="40c48-296">レビュー セットのワークフロー</span><span class="sxs-lookup"><span data-stu-id="40c48-296">Review sets workflow</span></span>

<span data-ttu-id="40c48-297">既存のレビュー セットを表示するか、[レビュー セット] タブをクリックして新しいレビュー セット **を作成** できます。レビュー セットの詳細については、レビュー セットの管理に関するページ [をAdvanced eDiscovery。](/microsoft-365/compliance/managing-review-sets)</span><span class="sxs-lookup"><span data-stu-id="40c48-297">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="40c48-298">ドキュメントに加えて、メール、Teams、Yammer、その他のコンテンツをレビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-298">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="40c48-299">レビュー セット内では、コンテンツの検索やカスタム クエリの作成など、他のコンテキストで実行できる操作の多くを実行できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-299">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="40c48-300">これらの操作は、レビュー セットに追加されたアイテムにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-300">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="40c48-301">[ **レビュー セットの** 管理] ボタンには、分析、概要レポート、追加されたロード セットの数などの追加オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-301">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="40c48-302">データの視覚エフェクトとグラフにアクセスするには、右上にある [ **個々の結果** \> **] [検索プロファイル** ] ビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="40c48-302">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="40c48-303">これらのグラフのくさびをクリックすると、クエリを実行するコンテンツの種類を対話形式で選択できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-303">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="40c48-304">たとえば、コンテンツのクエリのみを実行Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-304">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="40c48-305">これらのクエリは、手動で書き込むクエリを保存するのと同じ方法で保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-305">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="40c48-306">概要ビュー、テキスト ビュー、注釈ビュー</span><span class="sxs-lookup"><span data-stu-id="40c48-306">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="40c48-307">レビュー セット内の Teams 会話をクリックすると、[概要] ビューが表示されます。このビューには、Teams 会話全体が個別に操作できるメッセージの一覧として表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-307">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="40c48-308">メッセージの右側にある下向き矢印をクリックすると、メッセージの詳細を表示したり、個々のファイルをダウンロードしたりできるコンテキスト メニューが表示 `.msg` されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-308">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="40c48-309">メッセージの詳細をクリックすると、メタデータの概要またはメッセージの完全なメタデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-309">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="40c48-310">PDF をダウンロードするには、概要ビューの右上にあるダウンロード ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="40c48-310">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="40c48-311">[テキスト **ビュー] タブ** をクリックして、会話の抽出されたテキストのプレーンテキスト ビュー Teamsします。</span><span class="sxs-lookup"><span data-stu-id="40c48-311">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="40c48-312">このプレーン テキスト コンテンツはエクスポートに適しています。他のソフトウェア ツールを使用して簡単に作業できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-312">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="40c48-313">[注釈ビュー] **タブをクリックして** 注釈機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="40c48-313">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="40c48-314">このタブには、会話に似た形式でコンテンツがTeams表示されますが、編集するための追加のオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-314">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="40c48-315">鉛筆ツールを使用して、メモを作成したり、メッセージに描画したり、編集のためにきめ細かくスクラッチすることができます。</span><span class="sxs-lookup"><span data-stu-id="40c48-315">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="40c48-316">領域を **黒くして** "編集" としてマークする四角形を描画するために使用できる領域編集ツールもあります。</span><span class="sxs-lookup"><span data-stu-id="40c48-316">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="40c48-317">ユーザー間のスレッド化された会話用に変更されたファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40c48-317">Here's an example of a redacted file for threaded conversation between users.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="40c48-318">![変更されたファイルのスクリーンショット](media/RedactedFileExample.png)</span><span class="sxs-lookup"><span data-stu-id="40c48-318">![Screenshot of redacted file](media/RedactedFileExample.png)</span></span>

<span data-ttu-id="40c48-319">[注釈ビュー] タブ **の** 下部には、[ドキュメント **の** タグ付け] ボタンが表示され、タグ付けパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40c48-319">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="40c48-320">このパネル内で、会話内のすべてのメッセージにタグTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-320">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="40c48-321">会話に "興味深いアイテム" が含まれているかどうか、エクスポートに含める必要があるかどうか、さらにレビューが必要かどうかなど、応答型または応答性の高くない、特権付きまたは特権を持たない会話としてラベルを付けできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-321">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="40c48-322">他のカスタマイズ可能なタグを管理して適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="40c48-322">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="40c48-323">[アクション] メニュー</span><span class="sxs-lookup"><span data-stu-id="40c48-323">Action menu</span></span>

<span data-ttu-id="40c48-324">レビュー セット ウィンドウで、[アクション のエクスポート] をクリックしてコンテンツ **をエクスポート** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="40c48-324">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="40c48-325">エクスポート時には、多くのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-325">There are many options available when exporting.</span></span>

<span data-ttu-id="40c48-326">すべてのメッセージのすべてのメタデータを含むファイルをエクスポートするには、Teamsをクリックして [ファイルの読み込み **] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="40c48-326">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="40c48-327">コンテンツに適用したタグをファイルに含めるには、クリックして [タグ] チェック ボックス **をオン** にします。</span><span class="sxs-lookup"><span data-stu-id="40c48-327">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="40c48-328">[ネイティブ **ファイル] オプションを** 使用して、ネイティブ形式でファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="40c48-328">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="40c48-329">会話を 1 つのファイルとしてエクスポートするか、個別の個別のファイル内のすべてのチャット メッセージとしてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="40c48-329">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="40c48-330">[ **テキスト ファイル]** オプションでは、テキスト形式のコンテンツを保存できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-330">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="40c48-331">レビュー セット内の Teams 会話のプレーン テキスト ビューを取得する方法の詳細については、上の「概要ビュー、テキスト ビュー、注釈ビュー」[を参照](#summary-view-text-view-and-annotate-view)してください。</span><span class="sxs-lookup"><span data-stu-id="40c48-331">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="40c48-332">前の「概要ビュー、テキスト ビュー、注釈ビュー」セクション [](#summary-view-text-view-and-annotate-view)で説明したように、コンテンツに編集を適用した場合は、[編集したネイティブを変換された **PDF** に置き換える] オプションを選択して、ネイティブ ファイルを PDF で変換されたコピーに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="40c48-332">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="40c48-333">Microsoft 提供の Azure Blob Storage コンテナーにエクスポートするか、独自の Azure Blob Storage コンテナーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="40c48-333">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="40c48-334">エクスポート プロセスを開始する準備ができたら、[エクスポート] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="40c48-334">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="40c48-335">Azure BLOB [ストレージ コンテナーに](/microsoft-365/compliance/download-export-jobs) アクセスし、エクスポートが完了した後にエクスポートされたコンテンツをダウンロードする方法の詳細については、「エクスポート ジョブのダウンロード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c48-335">See [Download export jobs](/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="40c48-336">エクスポートには長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="40c48-336">Exporting can take an extended period of time.</span></span> <span data-ttu-id="40c48-337">エクスポート プロセスの状態を追跡するには、[レビューセット] タブを終了し、[エクスポート] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="40c48-337">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="40c48-338">関連トピック</span><span class="sxs-lookup"><span data-stu-id="40c48-338">Related topics</span></span>

- [<span data-ttu-id="40c48-339">eDiscovery in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="40c48-339">eDiscovery in Microsoft 365</span></span>](/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="40c48-340">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="40c48-340">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)