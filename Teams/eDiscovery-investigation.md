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
description: 法的手続きのために電子的に保存された情報を送信する必要がある場合など、電子情報開示を実行する必要がある場合の操作について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980461"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="c0575-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="c0575-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="c0575-104">大企業は、電子的に保存された情報 (ESI) の提出を要求する高いペナルティ法的手続きにさらされる場合が多いです。</span><span class="sxs-lookup"><span data-stu-id="c0575-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="c0575-105">Microsoft Teams のコンテンツは、電子情報開示の調査中に検索して使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="c0575-106">概要</span><span class="sxs-lookup"><span data-stu-id="c0575-106">Overview</span></span>

<span data-ttu-id="c0575-107">すべての Microsoft Teams 1 対 1 またはグループ チャットは、各ユーザーのメールボックスにジャーナル処理されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="c0575-108">すべての標準チャネル メッセージは、チームを表すグループ メールボックスにジャーナリングされます。</span><span class="sxs-lookup"><span data-stu-id="c0575-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="c0575-109">標準チャネルでアップロードされたファイルは、SharePoint Online と OneDrive for Business の電子情報開示機能の下で扱います。</span><span class="sxs-lookup"><span data-stu-id="c0575-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="c0575-110">プライベート チャネル内のメッセージとファイルの電子情報開示は [、](private-channels.md) 標準チャネルとは異なる方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="c0575-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="c0575-111">詳細については、「プライベート チャネル [の電子情報開示」を参照してください](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="c0575-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="c0575-112">すべての Teams コンテンツが eDiscoverable という訳ではありません。</span><span class="sxs-lookup"><span data-stu-id="c0575-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="c0575-113">次の表に、Microsoft 電子情報開示ツールを使用して検索できるコンテンツ タイプを示します。</span><span class="sxs-lookup"><span data-stu-id="c0575-113">The following table shows the content types that you can search for using Microsoft eDiscovery tools:</span></span>

| <span data-ttu-id="c0575-114">コンテンツの種類</span><span class="sxs-lookup"><span data-stu-id="c0575-114">Content type</span></span> | <span data-ttu-id="c0575-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="c0575-115">eDiscoverable</span></span> | <span data-ttu-id="c0575-116">備考</span><span class="sxs-lookup"><span data-stu-id="c0575-116">Notes</span></span> |
|:--- | :--- |:--- |
|<span data-ttu-id="c0575-117">オーディオ録音</span><span class="sxs-lookup"><span data-stu-id="c0575-117">Audio recordings</span></span> | <span data-ttu-id="c0575-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0575-118">No</span></span> | |
|<span data-ttu-id="c0575-119">カードの内容</span><span class="sxs-lookup"><span data-stu-id="c0575-119">Card content</span></span>|<span data-ttu-id="c0575-120">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-120">Yes</span></span>|<span data-ttu-id="c0575-121">詳細 [については、「カードのコンテンツを検索する](#search-for-card-content) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0575-121">See [Search for card content](#search-for-card-content) for more information.</span></span>|
|<span data-ttu-id="c0575-122">チャット リンク</span><span class="sxs-lookup"><span data-stu-id="c0575-122">Chat links</span></span> | <span data-ttu-id="c0575-123">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-123">Yes</span></span> | |
|<span data-ttu-id="c0575-124">チャット メッセージ</span><span class="sxs-lookup"><span data-stu-id="c0575-124">Chat messages</span></span> | <span data-ttu-id="c0575-125">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-125">Yes</span></span> |<span data-ttu-id="c0575-126">これには、Teams チャネルのコンテンツ、1 対 1 のチャット、1:N グループ チャット、ゲスト ユーザーの参加者とのチャットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0575-126">This includes content in Teams channels, 1:1 chats, 1:N group chats, and chats with guest user participants.</span></span>  |
|<span data-ttu-id="c0575-127">コード スニペット</span><span class="sxs-lookup"><span data-stu-id="c0575-127">Code snippets</span></span> | <span data-ttu-id="c0575-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0575-128">No</span></span> | |
|<span data-ttu-id="c0575-129">編集したメッセージ</span><span class="sxs-lookup"><span data-stu-id="c0575-129">Edited messages</span></span> | <span data-ttu-id="c0575-130">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-130">Yes</span></span> | <span data-ttu-id="c0575-131">ユーザーが保留にされている場合、以前のバージョンの編集されたメッセージも保持されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-131">If the user is on hold, previous versions of edited messages are also preserved.</span></span> |
|<span data-ttu-id="c0575-132">絵文字、GIF、ステッカー</span><span class="sxs-lookup"><span data-stu-id="c0575-132">Emojis, GIFs, and stickers</span></span> | <span data-ttu-id="c0575-133">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-133">Yes</span></span> | |
|<span data-ttu-id="c0575-134">インライン画像</span><span class="sxs-lookup"><span data-stu-id="c0575-134">Inline images</span></span> | <span data-ttu-id="c0575-135">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-135">Yes</span></span> | |
|<span data-ttu-id="c0575-136">会議の IM 会話</span><span class="sxs-lookup"><span data-stu-id="c0575-136">Meeting IM conversations</span></span> | <span data-ttu-id="c0575-137">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-137">Yes</span></span> | |
|<span data-ttu-id="c0575-138">会議のメタデータ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0575-138">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="c0575-139">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-139">Yes</span></span> |  |
|<span data-ttu-id="c0575-140">チャネルの名前</span><span class="sxs-lookup"><span data-stu-id="c0575-140">Name of channel</span></span> | <span data-ttu-id="c0575-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0575-141">No</span></span> | |
|<span data-ttu-id="c0575-142">プライベート チャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="c0575-142">Private channel messages</span></span> | <span data-ttu-id="c0575-143">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-143">Yes</span></span> | |
|<span data-ttu-id="c0575-144">見積もり</span><span class="sxs-lookup"><span data-stu-id="c0575-144">Quotes</span></span> | <span data-ttu-id="c0575-145">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-145">Yes</span></span> | <span data-ttu-id="c0575-146">引用符で囲まれたコンテンツは検索可能です。</span><span class="sxs-lookup"><span data-stu-id="c0575-146">Quoted content is searchable.</span></span> <span data-ttu-id="c0575-147">ただし、検索結果は、コンテンツが引用されたというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c0575-147">However, search results don't indicate that the content was quoted.</span></span> |
|<span data-ttu-id="c0575-148">リアクション ("良い"、"ハート"、"その他のリアクション" など)</span><span class="sxs-lookup"><span data-stu-id="c0575-148">Reactions (such as likes, hearts, and other reactions)</span></span> | <span data-ttu-id="c0575-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="c0575-149">No</span></span> | |
|<span data-ttu-id="c0575-150">件名</span><span class="sxs-lookup"><span data-stu-id="c0575-150">Subject</span></span> | <span data-ttu-id="c0575-151">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-151">Yes</span></span> | |
|<span data-ttu-id="c0575-152">テーブル</span><span class="sxs-lookup"><span data-stu-id="c0575-152">Tables</span></span> | <span data-ttu-id="c0575-153">はい</span><span class="sxs-lookup"><span data-stu-id="c0575-153">Yes</span></span> | |
|||

<span data-ttu-id="c0575-154"><sup>1 つの</sup> 会議 (および通話) メタデータには、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0575-154"><sup>1</sup> Meeting (and call) metadata includes the following:</span></span>

- <span data-ttu-id="c0575-155">会議の開始時刻と終了時刻、および期間</span><span class="sxs-lookup"><span data-stu-id="c0575-155">Meeting start and end time, and duration</span></span>
- <span data-ttu-id="c0575-156">各参加者の会議への参加と退出のイベント</span><span class="sxs-lookup"><span data-stu-id="c0575-156">Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="c0575-157">VOIP の参加/通話</span><span class="sxs-lookup"><span data-stu-id="c0575-157">VOIP join/calls</span></span>
- <span data-ttu-id="c0575-158">匿名参加</span><span class="sxs-lookup"><span data-stu-id="c0575-158">Anonymous join</span></span>
- <span data-ttu-id="c0575-159">フェデレーション ユーザーの参加</span><span class="sxs-lookup"><span data-stu-id="c0575-159">Federated user join</span></span>
- <span data-ttu-id="c0575-160">ゲスト ユーザーの参加</span><span class="sxs-lookup"><span data-stu-id="c0575-160">Guest user join</span></span>

  <span data-ttu-id="c0575-161">この画像は、会議のメタデータの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="c0575-161">The image shows an example of meeting metadata.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="c0575-162">![画像は、CVR レコードの会議メタデータの画像です。](media/conversationOption3.png)</span><span class="sxs-lookup"><span data-stu-id="c0575-162">![Image is of the CVR records meeting metadata.](media/conversationOption3.png)</span></span>

<span data-ttu-id="c0575-163">会議中の参加者間の IM 会話の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c0575-163">Here's an example of an IM conversation between participants during the meeting.</span></span>

![Teams の参加者間の会話。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c0575-165">![電子情報開示検索結果の参加者間の会話。](media/MeetingImConversation2.png)</span><span class="sxs-lookup"><span data-stu-id="c0575-165">![Conversation between participants in eDiscovery search results.](media/MeetingImConversation2.png)</span></span>

<span data-ttu-id="c0575-166">電子情報開示調査の実施の詳細については、「コア電子情報開示の使用を開始する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="c0575-166">For more information about conducting an eDiscovery investigation, see [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="c0575-167">Microsoft Teams のデータは、Excel の電子情報開示エクスポート出力に IM またはスレッドとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-167">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="c0575-168">Outlook でファイルを `.pst` 開き、エクスポート後にそれらのメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-168">You can open the `.pst` file in Outlook to view those messages after you export them.</span></span>

<span data-ttu-id="c0575-169">チームの .pst ファイルを表示すると、すべての会話は [会話履歴] の [チーム チャット] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-169">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="c0575-170">メッセージのタイトルには、チーム名とチャネル名が含まれている。</span><span class="sxs-lookup"><span data-stu-id="c0575-170">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="c0575-171">たとえば、次の画像は、製造仕様チームの Project 7 標準チャネルにメッセージを送信した Bob からのメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="c0575-171">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook のユーザーのメールボックス内のチーム チャット フォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="c0575-173">ユーザーのメールボックス内のプライベート チャットは、[会話履歴] の下の [チーム チャット] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-173">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="c0575-174">プライベート チャネルの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="c0575-174">eDiscovery of private channels</span></span>

<span data-ttu-id="c0575-175">プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-175">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="c0575-176">レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="c0575-176">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="c0575-177">各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイトが用意されています。プライベート チャネル内のファイルは、親チームとは独立して管理されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-177">Because each private channel has its own SharePoint site that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="c0575-178">Teams は、チーム内の 1 つのチャネルの電子情報開示検索をサポートしないので、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0575-178">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="c0575-179">プライベート チャネル内のコンテンツの電子情報開示検索を実行するには、チーム、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含める)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。</span><span class="sxs-lookup"><span data-stu-id="c0575-179">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="c0575-180">次の手順を使用して、電子情報開示検索に含めるプライベート チャネル内のファイルとメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="c0575-180">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="c0575-181">電子情報開示検索にプライベート チャネル ファイルを含める</span><span class="sxs-lookup"><span data-stu-id="c0575-181">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="c0575-182">これらの手順を実行する前に、SharePoint Online 管理シェルをインストールし [、SharePoint Online に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="c0575-182">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

1. <span data-ttu-id="c0575-183">チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0575-183">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="c0575-184">次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクション URL と親チーム グループ ID の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0575-184">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="c0575-185">チームまたはグループ ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベート チャネル サイトを特定します。$groupID はチームのグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="c0575-185">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="c0575-186">電子情報開示検索にプライベート チャネル メッセージを含める</span><span class="sxs-lookup"><span data-stu-id="c0575-186">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="c0575-187">これらの手順を実行する前に、最新バージョンの [Teams PowerShell モジュールがインストールされていることを確認](teams-powershell-overview.md) します。</span><span class="sxs-lookup"><span data-stu-id="c0575-187">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="c0575-188">次のコマンドを実行して、チーム内のプライベート チャネルの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0575-188">Run the following command to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="c0575-189">次のコマンドを実行して、プライベート チャネル メンバーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0575-189">Run the following command to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="c0575-190">電子情報開示検索クエリの一部として、チームの各プライベート チャネルのすべてのメンバーの [メールボックスを含める](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="c0575-190">Include the mailboxes of all members from each private channel in the team as part of your [eDiscovery search query](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery).</span></span>

## <a name="search-for-content-for-guest-users"></a><span data-ttu-id="c0575-191">ゲスト ユーザーのコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="c0575-191">Search for content for guest users</span></span>

<span data-ttu-id="c0575-192">電子情報開示ツールを使用して、組織内のゲスト ユーザーに関連する Teams コンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-192">You can use eDiscovery tools to search for Teams content related to guest users in your organization.</span></span> <span data-ttu-id="c0575-193">ゲスト ユーザーに関連付けられている Teams チャット コンテンツは、クラウドベースの保存場所に保持され、電子情報開示を使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-193">Teams chat content that's associated with a guest user is preserved in a cloud-based storage location and can be searched for using eDiscovery.</span></span> <span data-ttu-id="c0575-194">これには、ゲスト ユーザーが組織内の他のユーザーとの参加者である 1 対 1 と 1:N のチャット会話のコンテンツの検索が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0575-194">This includes searching for content in 1:1 and 1:N chat conversations in which a guest user is a participant with other users in your organization.</span></span> <span data-ttu-id="c0575-195">ゲスト ユーザーが参加者であるプライベート チャネル メッセージを検索し、ゲスト *と* ゲスト チャットの会話のコンテンツを検索することもできます。ゲスト ユーザーはゲスト ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="c0575-195">You can also search for private channel messages in which a guest user is a participant and search for content in *guest:guest* chat conversations where the only participants are guest users.</span></span>

<span data-ttu-id="c0575-196">ゲスト ユーザーのコンテンツを検索するには:</span><span class="sxs-lookup"><span data-stu-id="c0575-196">To search for content for guest users:</span></span>

1. <span data-ttu-id="c0575-197">Azure AD PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="c0575-197">Connect to Azure AD PowerShell.</span></span> <span data-ttu-id="c0575-198">手順については、「PowerShell で Microsoft 365 に接続する」の「Azure Active Directory PowerShell で接続する [」セクションを参照してください](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="c0575-198">For instructions, see the "Connect with the Azure Active Directory PowerShell" section in [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="c0575-199">前のトピックの手順 1 と手順 2 を必ず完了してください。</span><span class="sxs-lookup"><span data-stu-id="c0575-199">Be sure to complete Step 1 and Step 2 in the previous topic.</span></span>

2. <span data-ttu-id="c0575-200">Azure AD PowerShell に正常に接続したら、次のコマンドを実行して、組織内のすべてのゲスト ユーザーのユーザー プリンシパル名 (UPN) を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0575-200">After you successfully connect to Azure AD PowerShell, run the following command to display the user principal name (UPN) for all guest users in your organization.</span></span> <span data-ttu-id="c0575-201">手順 4 で検索を作成する場合は、ゲスト ユーザーの UPN を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0575-201">You have to use the UPN of the guest user when you create the search in step 4.</span></span>

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > <span data-ttu-id="c0575-202">コンピューター画面にユーザー プリンシパル名のリストを表示する代わりに、コマンドの出力をテキスト ファイルにリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-202">Instead of displaying a list of user principal names on the computer screen, you can redirect the output of the command to a text file.</span></span> <span data-ttu-id="c0575-203">この操作を行うには、前の `> filename.txt` コマンドに追加します。</span><span class="sxs-lookup"><span data-stu-id="c0575-203">You can do this by appending `> filename.txt` to the previous command.</span></span> <span data-ttu-id="c0575-204">ユーザー プリンシパル名を含むテキスト ファイルは、現在のフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-204">The text file with the user principal names will be saved to the current folder.</span></span>

3. <span data-ttu-id="c0575-205">別のウィンドウWindows PowerShell、セキュリティ/コンプライアンス センターの PowerShell &接続します。</span><span class="sxs-lookup"><span data-stu-id="c0575-205">In a different Windows PowerShell window, connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="c0575-206">手順については、「セキュリティ/コンプライアンス [センター PowerShell への&を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c0575-206">For instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="c0575-207">多要素認証を使用するか、または使用せずに接続できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-207">You can connect with or without using multi-factor authentication.</span></span>

4. <span data-ttu-id="c0575-208">指定したゲスト ユーザーが参加者だったすべてのコンテンツ (チャット メッセージやメール メッセージなど) を検索するコンテンツ検索を作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0575-208">Create a content search that searches for all content (such as chat messages and email messages) in which the specified guest user was a participant by running the following command.</span></span>

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   <span data-ttu-id="c0575-209">たとえば、ゲスト ユーザー Sara Davis に関連付けられているコンテンツを検索するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0575-209">For example, to search for content associated with the guest user Sara Davis, you would run the following command.</span></span>

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    <span data-ttu-id="c0575-210">PowerShell を使用してコンテンツ検索を作成する方法の詳細については [、「New-ComplianceSearch」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)。</span><span class="sxs-lookup"><span data-stu-id="c0575-210">For more information about using PowerShell to create content searches, see [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch).</span></span>

5. <span data-ttu-id="c0575-211">次のコマンドを実行して、手順 4 で作成したコンテンツ検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="c0575-211">Run the following command to start the content search that you created in step 4:</span></span>

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. <span data-ttu-id="c0575-212">[すべてのコンテンツ [https://compliance.microsoft.com](https://compliance.microsoft.com) 検索を表示] に  >  **移動し、[すべてのコンテンツ検索を表示] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c0575-212">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Show all** > **Content search**.</span></span>

7. <span data-ttu-id="c0575-213">検索の一覧で、手順 4 で作成した検索を選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="c0575-213">In the list of searches, select the search that you created in step 4 to display the flyout page.</span></span>

8. <span data-ttu-id="c0575-214">フライアウト ページでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c0575-214">On the flyout page, you can do the following things:</span></span>

   - <span data-ttu-id="c0575-215">[ **結果の表示]** をクリックして検索結果を表示し、コンテンツをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="c0575-215">Click **View results** to view the search results and preview the content.</span></span>

   - <span data-ttu-id="c0575-216">[クエリ] **フィールドの横** にある [編集] を **クリック** して編集し、検索を再実行します。</span><span class="sxs-lookup"><span data-stu-id="c0575-216">Next to the **Query** field, click **Edit** to edit and then rerun the search.</span></span> <span data-ttu-id="c0575-217">たとえば、検索クエリを追加して結果を絞り込むなどです。</span><span class="sxs-lookup"><span data-stu-id="c0575-217">For example, you can add a search query to narrow the results.</span></span>

   - <span data-ttu-id="c0575-218">[ **結果のエクスポート] を** クリックして、検索結果をエクスポートしてダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c0575-218">Click **Export results** to export and download the search results.</span></span>

## <a name="search-for-card-content"></a><span data-ttu-id="c0575-219">カードコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="c0575-219">Search for card content</span></span>

<span data-ttu-id="c0575-220">Teams チャネルのアプリ、1 対 1 のチャット、1xN チャットによって生成されたカード コンテンツはメールボックスに保存され、検索できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-220">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="c0575-221">カード *は* 、短いコンテンツの UI コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c0575-221">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="c0575-222">カードには複数のプロパティと添付ファイルを含め、カードの操作をトリガーできるボタンを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c0575-222">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="c0575-223">詳細については、「カード」を [参照してください。](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span><span class="sxs-lookup"><span data-stu-id="c0575-223">For more information, see [Cards](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

<span data-ttu-id="c0575-224">他の Teams コンテンツと同様に、カードコンテンツが保存される場所は、カードが使用された場所に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="c0575-224">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="c0575-225">Teams チャネルで使用されるカードのコンテンツは、Teams グループ メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-225">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="c0575-226">1 対 1 および 1xN のチャットのカード コンテンツは、チャット参加者のメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-226">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

<span data-ttu-id="c0575-227">カードのコンテンツを検索するには、または検索条件 `kind:microsoftteams` を `itemclass:IPM.SkypeTeams.Message` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-227">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="c0575-228">検索結果を確認すると、Teams チャネルのボットによって生成されたカード コンテンツには、送信者 **/** 作成者のメール プロパティがあります。カード コンテンツを生成したアプリの名前です `<appname>@teams.microsoft.com` `appname` 。</span><span class="sxs-lookup"><span data-stu-id="c0575-228">When reviewing search results, card content generated by bots in a Teams channel has the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="c0575-229">カードコンテンツがユーザーによって生成された場合、 **送信者/作成者の** 値によってユーザーが識別されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-229">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

<span data-ttu-id="c0575-230">コンテンツ検索結果でカードコンテンツを表示すると、そのコンテンツはメッセージの添付ファイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-230">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="c0575-231">添付ファイルの名前 `appname.html` は、 `appname` カードコンテンツを生成したアプリの名前です。</span><span class="sxs-lookup"><span data-stu-id="c0575-231">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="c0575-232">次のスクリーンショットは、カードコンテンツ (Asana という名前のアプリの場合) が Teams および検索の結果に表示される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c0575-232">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

<span data-ttu-id="c0575-233">**Teams のカード コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="c0575-233">**Card content in Teams**</span></span>

![Teams チャネル メッセージのカード コンテンツ](media/CardContentTeams.png)

<span data-ttu-id="c0575-235">**検索結果のカード コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="c0575-235">**Card content in search results**</span></span>
  
![コンテンツ検索の結果と同じカード コンテンツ](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> <span data-ttu-id="c0575-237">現時点でカードコンテンツの画像を検索結果に表示するには (前のスクリーンショットのチェックマークなど)、Teams にサインインする必要があります (検索結果の表示に使用したのと同じブラウザー セッションの別のタブで)。 https://teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c0575-237">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="c0575-238">それ以外の場合は、画像のプレースホルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-238">Otherwise, image placeholders are displayed.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="c0575-239">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c0575-239">Advanced eDiscovery</span></span>

<span data-ttu-id="c0575-240">一部の Microsoft Teams コンテンツは、Advanced eDiscovery ワークフローを使用して検索 [および保持できます](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="c0575-240">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="c0575-241">電子情報開示にはさまざまな検索、保留、エクスポート機能が含まれていますが、Advanced eDiscovery では、コンプライアンス管理者がデータ ソースを特定し、その内容を分析するためのより多くのツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0575-241">While eDiscovery provides a range of search, hold, and export functionality, Advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="c0575-242">Teams コンテンツの高度な電子情報開示カストディアン ワークフロー</span><span class="sxs-lookup"><span data-stu-id="c0575-242">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="c0575-243">カストディアンは、さまざまなチームのメンバーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0575-243">Custodians might be a member of various teams.</span></span> <span data-ttu-id="c0575-244">これらのカストディアンに関連する Teams コンテンツをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-244">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="c0575-245">カストディアン ワークフローの手順については、「Advanced eDiscovery ケースにカストディアンを追加する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="c0575-245">For instructions on the custodian workflow, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

<span data-ttu-id="c0575-246">カストディアンを追加したら、[次へ] ボタンを **クリック** し、[追加] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="c0575-246">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="c0575-247">ウィンドウが表示され、追加の場所を選択するように求めるメッセージが表示されます。このウィンドウには、カストディアンのすべてのメンバーシップとそのデータに対応する SharePoint サイトの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-247">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="c0575-248">これらのすべてのデータ ソースとチームから、電子情報開示に使用するコンテンツを選択し、そのユーザーと、特定したすべてのデータ ソースを保留にできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-248">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="c0575-249">Exchange コンテンツ、OneDrive コンテンツ、または両方を含めるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-249">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="c0575-250">Exchange コンテンツには、ユーザーのメールボックス内のすべてのアプリケーション コンテンツ (メール、メールボックスに保存されている Teams コンテンツなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0575-250">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="c0575-251">OneDrive のコンテンツには、ユーザーのコンテンツだけでなく、1 対 1 のチャット、1:N チャット、チャットで共有されているファイルなど、OneDrive に保存されている Teams のすべてのコンテンツも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0575-251">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="c0575-252">また、カストディアンがメンバーであるチームを関連付け、カストディアンがアクセスできるチャネル チャット メッセージとファイルを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-252">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="c0575-253">さらに、他のすべてのチームをカストディアンと関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-253">Additionally, any other team can be associated with a custodian.</span></span>

> [!NOTE]
> <span data-ttu-id="c0575-254">プライベート チャネル内のメッセージとファイルの電子情報開示は [、](private-channels.md) 標準チャネルとは異なる方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="c0575-254">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="c0575-255">詳細については、「プライベート チャネル [の電子情報開示」を参照してください](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="c0575-255">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="c0575-256">データ ソースを保留する</span><span class="sxs-lookup"><span data-stu-id="c0575-256">Placing a data source on hold</span></span>

<span data-ttu-id="c0575-257">カストディアンとして指定する特定のユーザーがない場合は、データ ソース全体を保留にできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-257">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="c0575-258">保留の詳細については、「Advanced eDiscovery で保留を管理する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。</span><span class="sxs-lookup"><span data-stu-id="c0575-258">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="c0575-259">Teams コンテンツの保留リストを作成する場合は、保留に含めるすべての場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-259">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="c0575-260">ユーザーがコンテンツを削除または変更している場合でも、保留すると、そのコンテンツのすべての以前のバージョンのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-260">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="c0575-261">オプションのクエリを使用して、キーワード、日付範囲、作成者、その他の多くの条件に基づいて保留の条件を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-261">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="c0575-262">キーワードを指定しない場合、そのデータ ソースのすべての内容が保留の対象と見なされます。</span><span class="sxs-lookup"><span data-stu-id="c0575-262">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="c0575-263">高度な電子情報開示検索</span><span class="sxs-lookup"><span data-stu-id="c0575-263">Advanced eDiscovery searches</span></span>

<span data-ttu-id="c0575-264">Teams のコンテンツも検索できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-264">Teams content can also be searched.</span></span> <span data-ttu-id="c0575-265">検索の詳細については [、「Advanced eDiscovery でケースのデータを収集する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="c0575-265">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="c0575-266">1 つのメッセージが検索クエリと一致する場合でも、検索は会話全体を返します。</span><span class="sxs-lookup"><span data-stu-id="c0575-266">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="c0575-267">検索クエリを作成するときに、既に選択しているすべてのソースが検索されるカストディアンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-267">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="c0575-268">また、ユーザーにマップされていない Teams サイトなど、管理者以外のソースを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-268">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="c0575-269">Teams コンテンツ内の検索を絞り込むには、オプションのクエリも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-269">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="c0575-270">検索を作成して選択すると、ウィンドウが表示され、選択した検索に対して実行できる追加の詳細とアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-270">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="c0575-271">[統計情報]ボタンをクリックすると、場所の種類、コンテンツの元のソースに応じて内訳が表示され、コンテンツがグループ メールボックス、個々のユーザー メールボックス、または SharePoint サイトにあるかどうかなど、検索に関する統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-271">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="c0575-272">したがって、どのソースが検索結果に貢献しているのかの内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-272">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="c0575-273">また、クエリ ビュー **も** 利用できます。クエリ ビューでは、結果にどのキーワードが関連付けられているのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-273">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="c0575-274">検索を完了した後、[結果をレビュー セットに追加] ボタンをクリックし、レビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-274">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="c0575-275">レビュー セットの詳細については、この記事の後半にある [「Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) ワークフローと [レビュー](#review-sets-workflow) セット ワークフローでレビュー セットを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0575-275">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="c0575-276">標準レビュー セットとスレッド レビュー セット</span><span class="sxs-lookup"><span data-stu-id="c0575-276">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="c0575-277">レビュー セットに検索を追加する場合は、通常のレビュー セットまたは会話レビュー セットから選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-277">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="c0575-278">通常のレビュー セットはエクスポートに似ています。Teams コンテンツの `.msg` 個々のファイルが提供され、基本的なビューでコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-278">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="c0575-279">通常、他のソフトウェア ツールを使用して後でファイルを再処理する場合は、通常のレビュー セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0575-279">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="c0575-280">会話レビュー セットは、会話のより直感的でスレッド化されたビューを提供します。関連するメッセージが適切な順序でまとめて表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-280">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c0575-281">![会話レビュー セットのスクリーンショット](media/conversationOptions2.png)</span><span class="sxs-lookup"><span data-stu-id="c0575-281">![Screenshot of conversation review set](media/conversationOptions2.png)</span></span>

<span data-ttu-id="c0575-282">やり直しなどの機能は、両方の種類のレビュー セットで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-282">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="c0575-283">レビュー セットの詳細については、「Advanced eDiscovery での会話 [のレビュー」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="c0575-283">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="c0575-284">コレクション オプション</span><span class="sxs-lookup"><span data-stu-id="c0575-284">Collection options</span></span>

<span data-ttu-id="c0575-285">レビュー セットに追加する場合、ウィンドウの [コレクション オプション]セクションのチェック ボックスとして、[会話の取得オプション] や [Teams の会話] など、いくつかの **オプションを\*\*\*\*使用できます**。</span><span class="sxs-lookup"><span data-stu-id="c0575-285">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="c0575-286">これらのオプションを有効にした場合、レビュー セットの一部である個々の Teams メッセージも、コンテキストのためにそれらを囲む追加のメッセージと一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-286">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="c0575-287">たとえば、クエリが特定であり、結果として 1 つのメッセージだけが返される場合、これらのオプションを有効にすると、クエリに一致したメッセージの後に続く複数のメッセージも返されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-287">For example, if your query is specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="c0575-288">多くの論理条件は、追加のメッセージがクエリに一致するメッセージにコンテキストを提供するかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-288">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="c0575-289">たとえば、Teams コンテンツの場合、これらのオプションを有効にすると、メッセージのスレッド化方法のために、親メッセージとすべての子メッセージが取得されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-289">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="c0575-290">メッセージのタイム スタンプもチェックされます。</span><span class="sxs-lookup"><span data-stu-id="c0575-290">Message time stamps are also checked.</span></span> <span data-ttu-id="c0575-291">メッセージがクエリと一致する場合、メッセージの前に 4 時間の範囲にあるか、4 時間以内に続く隣接するメッセージは会話の一部であると見なされ、結果にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0575-291">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="c0575-292">検索クエリに一致するコンテキスト メッセージを確実に返す必要がある場合は、これらのオプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0575-292">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="c0575-293">すべてのコンテンツを収集するか、検索の日付範囲を広くして、クエリの結果として返されるメッセージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-293">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="c0575-294">レビュー セットワークフロー</span><span class="sxs-lookup"><span data-stu-id="c0575-294">Review sets workflow</span></span>

<span data-ttu-id="c0575-295">既存のレビュー セットを表示したり、[レビュー セット] タブをクリックして新しい **レビュー セットを作成** することができます。レビュー セットの詳細については、「Advanced eDiscovery でレビュー セットを管理 [する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="c0575-295">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="c0575-296">ドキュメントに加えて、メール、Teams メッセージ、Yammer、その他のコンテンツをレビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-296">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="c0575-297">レビュー セット内では、コンテンツの検索やカスタム クエリの作成など、他のコンテキストで実行できる操作の多くを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-297">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="c0575-298">これらの操作は、レビュー セットに追加されたアイテムにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-298">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="c0575-299">[ **レビュー セットの管理** ] ボタンには、分析、サマリー レポート、追加されたロード セットの数などの追加オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-299">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="c0575-300">データの視覚エフェクトやグラフにアクセスするには、右上にある [個々の **結果** の \> 検索] プロファイル ビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0575-300">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="c0575-301">これらのグラフのくさび形をクリックすると、クエリを実行するコンテンツの種類を対話的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-301">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="c0575-302">たとえば、Teams のコンテンツにのみクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-302">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="c0575-303">手動で作成したクエリを保存するのと同じ方法で、これらのクエリを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-303">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="c0575-304">概要ビュー、テキスト ビュー、注釈ビュー</span><span class="sxs-lookup"><span data-stu-id="c0575-304">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="c0575-305">レビュー セットで Teams の会話をクリックすると、[概要]ビューが表示され、Teams の会話全体が個別にやり取りできるメッセージの一覧として表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-305">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="c0575-306">メッセージの右側にある下向き矢印をクリックすると、メッセージの詳細を表示したり、個々のファイルをダウンロードしたりできるコンテキスト メニューが表示 `.msg` されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-306">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="c0575-307">メッセージの詳細をクリックすると、メタデータの概要またはメッセージの完全なメタデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-307">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="c0575-308">PDF をダウンロードするには、概要ビューの右上にあるダウンロード ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0575-308">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="c0575-309">[テキスト **ビュー] タブを** クリックして、Teams の会話の抽出されたテキストのプレーン テキスト ビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="c0575-309">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="c0575-310">このテキスト形式のコンテンツはエクスポートに適しています。他のソフトウェア ツールを使用して簡単に作業できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-310">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="c0575-311">コメント機能にアクセス **するには、[注釈ビュー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0575-311">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="c0575-312">このタブには、Teams の会話に似た形式でコンテンツが表示されますが、編集するためのその他のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c0575-312">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="c0575-313">鉛筆ツールを使用して、メモを作成したり、メッセージに描画したり、やり直しのために細かいスクラッチを行う場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-313">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="c0575-314">また、 **領域を黒** くして "赤字" とマークする四角形を描画するために使用できる領域の再編集ツールもあります。</span><span class="sxs-lookup"><span data-stu-id="c0575-314">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="c0575-315">次に、ユーザー間のスレッド化された会話に対して、ファイルが機能し直した例を示します。</span><span class="sxs-lookup"><span data-stu-id="c0575-315">Here's an example of a redacted file for threaded conversation between users.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c0575-316">![破損したファイルのスクリーンショット](media/RedactedFileExample.png)</span><span class="sxs-lookup"><span data-stu-id="c0575-316">![Screenshot of redacted file](media/RedactedFileExample.png)</span></span>

<span data-ttu-id="c0575-317">[注釈ビュー] **タブの** 下部には、[タグ **付** けドキュメント] ボタンが表示され、タグ付けパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0575-317">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="c0575-318">このパネル内で、Teams の会話内のすべてのメッセージにタグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-318">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="c0575-319">会話に "興味を持つアイテム" が含まれているかどうか、エクスポートに含める必要があるかどうか、さらに確認する必要があるかどうかなど、応答型または非応答型、特権付き、または特権ではない会話としてラベルを付けできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-319">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="c0575-320">その他のカスタマイズ可能なタグを管理して適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0575-320">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="c0575-321">アクション メニュー</span><span class="sxs-lookup"><span data-stu-id="c0575-321">Action menu</span></span>

<span data-ttu-id="c0575-322">[レビュー セット] ウィンドウ内で、[アクション エクスポート] をクリックしてコンテンツ **をエクスポート** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="c0575-322">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="c0575-323">エクスポート時には、多くのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-323">There are many options available when exporting.</span></span>

<span data-ttu-id="c0575-324">すべての Teams メッセージのすべてのメタデータを含むファイルをエクスポートするには、[ファイルの読み込み] チェック ボックス **をオンにします** 。</span><span class="sxs-lookup"><span data-stu-id="c0575-324">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="c0575-325">コンテンツに適用したタグをファイルに含めるには、[タグ] チェック ボックスを **オン** にします。</span><span class="sxs-lookup"><span data-stu-id="c0575-325">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="c0575-326">[ネイティブ ファイル **] オプションを** 使用して、ネイティブ形式でファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c0575-326">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="c0575-327">1 つの会話を 1 つのファイルとしてエクスポートするか、個別のファイル内のすべてのチャット メッセージとしてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0575-327">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="c0575-328">[ **テキスト ファイル]** オプションでは、テキスト形式のコンテンツを保存できます。</span><span class="sxs-lookup"><span data-stu-id="c0575-328">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="c0575-329">レビュー セットで Teams の会話のプレーン テキスト ビューを取得する方法の詳細については、上記の概要ビュー、テキスト ビュー、注釈 [ビューを参照](#summary-view-text-view-and-annotate-view) してください。</span><span class="sxs-lookup"><span data-stu-id="c0575-329">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="c0575-330">上記の概要ビュー、テキスト ビュー、注釈ビューのセクションで[](#summary-view-text-view-and-annotate-view)説明したように、コンテンツにやり直しを適用した場合は、[変換された PDFで編集したネイティブを置き換える] オプションを選択して、ネイティブ ファイルを PDF の変換されたコピーに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c0575-330">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="c0575-331">Microsoft が提供する Azure BLOB ストレージ コンテナーにエクスポートするか、独自の Azure BLOB ストレージ コンテナーを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="c0575-331">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="c0575-332">エクスポート プロセスを開始する準備ができたら、[エクスポート] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="c0575-332">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="c0575-333">エクスポート [が完了したら、Azure](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) BLOB ストレージ コンテナーにアクセスし、エクスポートしたコンテンツをダウンロードする方法の詳細については、エクスポート ジョブのダウンロードに関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0575-333">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="c0575-334">エクスポートには、長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0575-334">Exporting can take an extended period of time.</span></span> <span data-ttu-id="c0575-335">エクスポート プロセスの状態を追跡するには、[レビューセット] タブを終了し、[エクスポート] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="c0575-335">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0575-336">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0575-336">Related topics</span></span>

- [<span data-ttu-id="c0575-337">Microsoft 365 の電子情報開示</span><span class="sxs-lookup"><span data-stu-id="c0575-337">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="c0575-338">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="c0575-338">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
