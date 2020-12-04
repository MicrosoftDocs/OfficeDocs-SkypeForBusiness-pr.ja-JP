---
title: コンテンツの電子情報開示調査の実施
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
description: 法的手続きのために電子的に保存された情報をすべて提出する必要がある場合など、電子情報開示を実行する必要がある場合の対処方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 53f3f1f3d8146b06b69a70dbbf7c00bdb979c43c
ms.sourcegitcommit: b6aeaa3d98c29bdc120db8ccfcb7ff2c11d246af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570826"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="37c10-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="37c10-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="37c10-104">大企業は、多くの場合、電子的に保存されている情報 (ESI) の申請を要求する高ペナルティ法的手続きにさらされています。</span><span class="sxs-lookup"><span data-stu-id="37c10-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="37c10-105">Microsoft Teams のコンテンツは、電子情報開示調査の際に検索して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="37c10-106">概要</span><span class="sxs-lookup"><span data-stu-id="37c10-106">Overview</span></span>

<span data-ttu-id="37c10-107">すべての Microsoft Teams 1:1 またはグループチャットは、それぞれのユーザーのメールボックスにジャーナリングされます。</span><span class="sxs-lookup"><span data-stu-id="37c10-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="37c10-108">すべての標準チャネルメッセージは、チームを表すグループメールボックスによってジャーナリングされます。</span><span class="sxs-lookup"><span data-stu-id="37c10-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="37c10-109">標準チャネルにアップロードされたファイルについては、SharePoint Online と OneDrive for business の電子情報開示機能の下に記載されています。</span><span class="sxs-lookup"><span data-stu-id="37c10-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="37c10-110">[プライベートチャネル](private-channels.md)でのメッセージやファイルの電子情報開示は、標準チャネルでの動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="37c10-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="37c10-111">詳細については、「 [プライベートチャネルの電子情報開示](#ediscovery-of-private-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="37c10-112">すべてのチームコンテンツが e 検出可能であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="37c10-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="37c10-113">次の表は、電子情報開示で検索できるコンテンツタイプを示しています。</span><span class="sxs-lookup"><span data-stu-id="37c10-113">The following table shows the content types that can be located through eDiscovery.</span></span>

| <span data-ttu-id="37c10-114">コンテンツの種類</span><span class="sxs-lookup"><span data-stu-id="37c10-114">Content type</span></span> | <span data-ttu-id="37c10-115">e 検出可能</span><span class="sxs-lookup"><span data-stu-id="37c10-115">eDiscoverable</span></span> | <span data-ttu-id="37c10-116">メモ</span><span class="sxs-lookup"><span data-stu-id="37c10-116">Notes</span></span> |
|:--- | --- |:--- |
| <span data-ttu-id="37c10-117">Teams のチャットメッセージ</span><span class="sxs-lookup"><span data-stu-id="37c10-117">Teams chat messages</span></span> | <span data-ttu-id="37c10-118">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-118">Yes</span></span> |  |
| <span data-ttu-id="37c10-119">プライベートチャネルメッセージ</span><span class="sxs-lookup"><span data-stu-id="37c10-119">Private channel messages</span></span> | <span data-ttu-id="37c10-120">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-120">Yes</span></span> | |
| <span data-ttu-id="37c10-121">チャネルの名前</span><span class="sxs-lookup"><span data-stu-id="37c10-121">Name of channel</span></span> | <span data-ttu-id="37c10-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="37c10-122">No</span></span> | |
| <span data-ttu-id="37c10-123">会議の IM 会話</span><span class="sxs-lookup"><span data-stu-id="37c10-123">Meeting IM conversations</span></span> | <span data-ttu-id="37c10-124">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-124">Yes</span></span> | |
| <span data-ttu-id="37c10-125">会議のメタデータ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="37c10-125">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="37c10-126">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-126">Yes</span></span> |  |
| <span data-ttu-id="37c10-127">編集済みメッセージ</span><span class="sxs-lookup"><span data-stu-id="37c10-127">Edited messages</span></span> | <span data-ttu-id="37c10-128">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-128">Yes</span></span> | <span data-ttu-id="37c10-129">ユーザーが保留になっている場合、以前のバージョンの編集済みメッセージは保持されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-129">If the user is on hold, previous versions of edited messages are preserved.</span></span> |
| <span data-ttu-id="37c10-130">絵文字、Gif、ステッカー</span><span class="sxs-lookup"><span data-stu-id="37c10-130">Emojis, GIFs, stickers</span></span> | <span data-ttu-id="37c10-131">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-131">Yes</span></span> | |
| <span data-ttu-id="37c10-132">コードスニペット</span><span class="sxs-lookup"><span data-stu-id="37c10-132">Code snippets</span></span> | <span data-ttu-id="37c10-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="37c10-133">No</span></span> | |
| <span data-ttu-id="37c10-134">チャットリンク</span><span class="sxs-lookup"><span data-stu-id="37c10-134">Chat links</span></span> | <span data-ttu-id="37c10-135">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-135">Yes</span></span> | |
| <span data-ttu-id="37c10-136">反力 (いいね!、ハートなど)</span><span class="sxs-lookup"><span data-stu-id="37c10-136">Reactions (likes, hearts, and so on)</span></span> | <span data-ttu-id="37c10-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="37c10-137">No</span></span> | |
| <span data-ttu-id="37c10-138">インライン画像</span><span class="sxs-lookup"><span data-stu-id="37c10-138">Inline images</span></span> | <span data-ttu-id="37c10-139">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-139">Yes</span></span> | |
| <span data-ttu-id="37c10-140">示し</span><span class="sxs-lookup"><span data-stu-id="37c10-140">Tables</span></span> | <span data-ttu-id="37c10-141">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-141">Yes</span></span> | |
| <span data-ttu-id="37c10-142">件名</span><span class="sxs-lookup"><span data-stu-id="37c10-142">Subject</span></span> | <span data-ttu-id="37c10-143">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-143">Yes</span></span> | |
| <span data-ttu-id="37c10-144">意味</span><span class="sxs-lookup"><span data-stu-id="37c10-144">Quotes</span></span> | <span data-ttu-id="37c10-145">はい</span><span class="sxs-lookup"><span data-stu-id="37c10-145">Yes</span></span> | <span data-ttu-id="37c10-146">引用符で囲まれたコンテンツは検索可能です。</span><span class="sxs-lookup"><span data-stu-id="37c10-146">Quoted content is searchable.</span></span> <span data-ttu-id="37c10-147">ただし、検索結果は、コンテンツが引用符で囲まれていることを示すわけではありません。</span><span class="sxs-lookup"><span data-stu-id="37c10-147">However, search results don't indicate that the content was quoted.</span></span> |
| <span data-ttu-id="37c10-148">音声録音</span><span class="sxs-lookup"><span data-stu-id="37c10-148">Audio recordings</span></span> | <span data-ttu-id="37c10-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="37c10-149">No</span></span> | |

<span data-ttu-id="37c10-150"><sup>1</sup> 会議のメタデータには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="37c10-150"><sup>1</sup> Meeting metadata includes the following:</span></span>

- <span data-ttu-id="37c10-151">会議または通話の開始時刻、終了時刻、および期間</span><span class="sxs-lookup"><span data-stu-id="37c10-151">Meeting or call start and end time, and duration</span></span>
- <span data-ttu-id="37c10-152">参加者ごとに通話/会議への参加とイベントの退出</span><span class="sxs-lookup"><span data-stu-id="37c10-152">Call/Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="37c10-153">VOIP の参加/通話</span><span class="sxs-lookup"><span data-stu-id="37c10-153">VOIP join/calls</span></span>
- <span data-ttu-id="37c10-154">匿名での参加</span><span class="sxs-lookup"><span data-stu-id="37c10-154">Anonymous join</span></span>
- <span data-ttu-id="37c10-155">フェデレーションされたユーザーの参加</span><span class="sxs-lookup"><span data-stu-id="37c10-155">Federated user join</span></span>
- <span data-ttu-id="37c10-156">ゲストユーザー参加</span><span class="sxs-lookup"><span data-stu-id="37c10-156">Guest user join</span></span>

<span data-ttu-id="37c10-157">この画像は、メタデータの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="37c10-157">The image shows an example of the metadata.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37c10-158">![画像は、会議メタデータの記録です。](media/conversationOption3.png)</span><span class="sxs-lookup"><span data-stu-id="37c10-158">![Image is of the CVR records meeting metadata.](media/conversationOption3.png)</span></span>

<span data-ttu-id="37c10-159">会議中の参加者間の IM 会話の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="37c10-159">Here's an example of IM conversation between participants during the meeting.</span></span>

![Teams の参加者間の会話。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37c10-161">![電子情報開示検索結果での参加者間の会話。](media/MeetingImConversation2.png)</span><span class="sxs-lookup"><span data-stu-id="37c10-161">![Conversation between participants in eDiscovery search results.](media/MeetingImConversation2.png)</span></span>

<span data-ttu-id="37c10-162">Microsoft Teams コンテンツを使用して eDiscovery 調査を実施するには、「 [Core eDiscovery の概要](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)」の手順1を確認します。</span><span class="sxs-lookup"><span data-stu-id="37c10-162">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="37c10-163">Microsoft Teams のデータは、Excel eDiscovery のエクスポート出力で IM または会話として表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-163">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="37c10-164">`.pst`エクスポート後にメッセージを表示するには、Outlook でファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-164">You can open the `.pst` file in Outlook to view those messages after export.</span></span>

<span data-ttu-id="37c10-165">チームの .pst ファイルを表示すると、すべての会話が [会話履歴] の下にあるチームチャットフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-165">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="37c10-166">メッセージのタイトルには、チーム名とチャネル名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="37c10-166">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="37c10-167">たとえば、次の図は、製造仕様チームの Project 7 標準チャネルを送信先しているボブからのメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="37c10-167">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook のユーザーのメールボックス内のチームチャットフォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="37c10-169">ユーザーのメールボックス内のプライベートチャットは、[会話履歴] の下の [チームチャット] フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-169">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="37c10-170">プライベートチャネルの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="37c10-170">eDiscovery of private channels</span></span>

<span data-ttu-id="37c10-171">プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-171">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="37c10-172">レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="37c10-172">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="37c10-173">各プライベートチャネルには、親チームサイトとは別の SharePoint サイトコレクションがあるため、プライベートチャネルのファイルは親チームとは独立して管理されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-173">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="37c10-174">チームはチーム内の1つのチャネルの電子情報開示検索をサポートしていないため、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c10-174">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="37c10-175">プライベートチャネルのコンテンツの電子情報開示検索を実行するには、チーム全体、プライベートチャネルに関連付けられたサイトコレクション (ファイルを含む)、プライベートチャネルメンバーのメールボックス (メッセージを含む) を検索します。</span><span class="sxs-lookup"><span data-stu-id="37c10-175">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="37c10-176">次の手順を使用して、プライベートチャネル内のファイルとメッセージを特定し、電子情報開示検索に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-176">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="37c10-177">電子情報開示検索でプライベートチャネルファイルを含める</span><span class="sxs-lookup"><span data-stu-id="37c10-177">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="37c10-178">これらの手順を実行する前に、 [Sharepoint Online 管理シェルをインストールして、Sharepoint online に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)します。</span><span class="sxs-lookup"><span data-stu-id="37c10-178">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

1. <span data-ttu-id="37c10-179">チーム内のプライベートチャネルに関連付けられているすべての SharePoint サイトコレクションの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="37c10-179">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="37c10-180">次の PowerShell スクリプトを実行して、チーム内のプライベートチャネルと親チームグループ ID に関連付けられたすべての SharePoint サイトコレクション Url の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="37c10-180">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="37c10-181">チームまたはグループの ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベートチャネルサイト ($groupID はチームのグループ ID) を特定します。</span><span class="sxs-lookup"><span data-stu-id="37c10-181">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="37c10-182">電子情報開示検索でプライベートチャネルメッセージを含める</span><span class="sxs-lookup"><span data-stu-id="37c10-182">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="37c10-183">これらの手順を実行する前に、 [最新バージョンの Teams PowerShell モジュール](teams-powershell-overview.md) がインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-183">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="37c10-184">チーム内のプライベートチャネルの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="37c10-184">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="37c10-185">プライベートチャネルメンバーの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="37c10-185">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="37c10-186">電子情報開示検索クエリの一部として、チーム内の各プライベートチャネルからすべてのメンバーのメールボックスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-186">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="37c10-187">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="37c10-187">Advanced eDiscovery</span></span>

<span data-ttu-id="37c10-188">一部の Microsoft Teams コンテンツは、 [アドバンスト eDiscovery ワークフロー](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)を使用して検索および保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c10-188">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="37c10-189">電子情報開示では、さまざまな検索、保留、エクスポート機能が提供されますが、advanced eDiscovery は、データソースを識別し、その内容を分析するために、コンプライアンス管理者により多くのツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="37c10-189">While eDiscovery provides a range of search, hold, and export functionality, advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="37c10-190">アドバンスト eDiscovery カストディアンチームコンテンツのワークフロー</span><span class="sxs-lookup"><span data-stu-id="37c10-190">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="37c10-191">カストディアンは、さまざまなチームのメンバーである場合があります。</span><span class="sxs-lookup"><span data-stu-id="37c10-191">Custodians might be a member of various teams.</span></span> <span data-ttu-id="37c10-192">これらのカストディアンに関連するチームコンテンツをキャプチャすることができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-192">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="37c10-193">カストディアンワークフローの背景と手順については、「 [Advanced eDiscovery ワークフロー](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-193">For background and instructions on the custodian workflow, see [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span>

<span data-ttu-id="37c10-194">カストディアンを追加した後、[ **次へ** ] ボタンをクリックし、[ **追加** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37c10-194">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="37c10-195">ウィンドウが表示され、追加の場所を選択するように求められます。これにより、すべてのカストディアンのメンバーシップと、そのデータに対応する SharePoint サイトの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-195">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="37c10-196">これらのすべてのデータソースとチームから、電子情報開示に使用するコンテンツを選択し、そのユーザーと、そのユーザーと、そのユーザーが保持しているすべてのデータソースを保存します。</span><span class="sxs-lookup"><span data-stu-id="37c10-196">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="37c10-197">Exchange のコンテンツ、OneDrive のコンテンツ、またはその両方を含めるかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-197">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="37c10-198">Exchange のコンテンツには、ユーザーのメールボックス内のすべてのアプリケーションのコンテンツが含まれます。たとえば、メール、自分のメールボックスに保存されている Teams のコンテンツなどです。</span><span class="sxs-lookup"><span data-stu-id="37c10-198">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="37c10-199">OneDrive のコンテンツには、ユーザーのコンテンツだけでなく、OneDrive に保存されているすべてのチームコンテンツ (1:1 のチャット、1: N のチャット、チャットで共有されたファイルなど) も含まれます。</span><span class="sxs-lookup"><span data-stu-id="37c10-199">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="37c10-200">また、カストディアンがメンバーになっているチームを関連付けることもできます。そのためには、カストディアンによってアクセス権があるチャネルチャットメッセージとファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="37c10-200">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="37c10-201">さらに、他のチームもカストディアンに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-201">Additionally, any other team can be associated with a custodian.</span></span> <span data-ttu-id="37c10-202">詳細については、「 [Advanced eDiscovery ケースにカストディアンを追加する](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-202">For more information, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

> [!NOTE]
> <span data-ttu-id="37c10-203">[プライベートチャネル](private-channels.md)でのメッセージやファイルの電子情報開示は、標準チャネルでの動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="37c10-203">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="37c10-204">詳細については、「 [プライベートチャネルの電子情報開示](#ediscovery-of-private-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-204">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="37c10-205">データソースを保留にする</span><span class="sxs-lookup"><span data-stu-id="37c10-205">Placing a data source on hold</span></span>

<span data-ttu-id="37c10-206">カストディアンとして指定する特定のユーザーがいない場合は、データソース全体を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-206">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="37c10-207">保留の詳細については、「 [Advanced eDiscovery で保留リストを管理](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-207">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="37c10-208">チームコンテンツの保留リストを作成する場合は、保留リストに含めるすべての場所を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-208">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="37c10-209">ユーザーがコンテンツを削除または変更している場合でも、保留によって、そのコンテンツの以前のすべてのバージョンのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-209">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="37c10-210">また、オプションのクエリを使用して、キーワード、日付の範囲、作成者などのさまざまな条件に基づいて、保留の条件を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c10-210">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="37c10-211">キーワードを指定しない場合、そのデータソースからのすべての内容が保留されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-211">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="37c10-212">Advanced eDiscovery の検索</span><span class="sxs-lookup"><span data-stu-id="37c10-212">Advanced eDiscovery searches</span></span>

<span data-ttu-id="37c10-213">チームコンテンツを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c10-213">Teams content can also be searched.</span></span> <span data-ttu-id="37c10-214">検索の詳細については、「 [Advanced eDiscovery でケースのデータを収集](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-214">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="37c10-215">検索クエリと一致するメッセージが1つであっても、検索はスレッド全体を返します。</span><span class="sxs-lookup"><span data-stu-id="37c10-215">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="37c10-216">検索クエリを作成するときに、選択したすべてのソースが検索されるように、[カストディアン] を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-216">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="37c10-217">また、ユーザーにマップされていない Teams サイトなどの、非 custodial ソースを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c10-217">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="37c10-218">オプションのクエリを使用して、チームのコンテンツ内で検索を絞り込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="37c10-218">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="37c10-219">検索を作成して選択すると、選択した検索に対して実行できる追加の詳細とアクションのウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-219">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="37c10-220">[ **統計** ] ボタンをクリックすると、場所の種類に基づくブレークダウン、コンテンツの元のソース、コンテンツがグループメールボックス、個々のユーザーのメールボックス、または SharePoint サイトにあるかどうかなど、検索に関する統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="37c10-220">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="37c10-221">そのため、検索結果にどのようなソースが投稿されているかがわかります。</span><span class="sxs-lookup"><span data-stu-id="37c10-221">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="37c10-222">また、 **クエリ** ビューも用意されているので、結果に寄与している個々のキーワードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="37c10-222">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="37c10-223">検索を完了したら、[ **結果をレビューに追加** ] ボタンをクリックして、レビューセットに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-223">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="37c10-224">レビューセットの詳細については、この記事の後半の「Advanced eDiscovery とレビュー[セットワークフロー](#review-sets-workflow) [のレビューセットを管理](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-224">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="37c10-225">通常のレビューセットと会話レビューセット</span><span class="sxs-lookup"><span data-stu-id="37c10-225">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="37c10-226">レビューセットに検索を追加するときは、通常のレビューセットまたは会話レビューセットから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-226">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="37c10-227">通常のレビューセットは、エクスポートと似ています。このアプリでは、チームコンテンツの個々のファイルが提供され、 `.msg` 基本的なビューにコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-227">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="37c10-228">通常、他のソフトウェアツールを使用して後でファイルを再処理する場合は、通常のレビューセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="37c10-228">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="37c10-229">会話のレビューセットを使用すると、より直感的な会話をスレッド形式で表示できます。関連メッセージが適切な順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-229">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37c10-230">![スレッドレビューセットのスクリーンショット](media/conversationOptions2.png)</span><span class="sxs-lookup"><span data-stu-id="37c10-230">![Screenshot of conversation review set](media/conversationOptions2.png)</span></span>

<span data-ttu-id="37c10-231">墨消しなどの機能は、どちらの種類のレビューセットでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="37c10-231">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="37c10-232">校閲セットの詳細については、「 [Advanced eDiscovery で会話を確認](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-232">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="37c10-233">コレクションオプション</span><span class="sxs-lookup"><span data-stu-id="37c10-233">Collection options</span></span>

<span data-ttu-id="37c10-234">レビューセットに追加する場合、**会話の検索オプション** や **チームの会話** など、ウィンドウの [**コレクションのオプション**] セクションには、チェックボックスとして使用できるいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="37c10-234">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="37c10-235">これらのオプションを有効にした場合、レビューセットに含まれている個々の Teams メッセージも、コンテキストに関連するメッセージと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-235">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="37c10-236">たとえば、クエリが固有であり、その結果として1つのメッセージしか返されなかった場合、これらのオプションを有効にすると、クエリに一致したメッセージに先行する複数のメッセージを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-236">For example, if your query is specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="37c10-237">多くの論理条件は、クエリに一致するメッセージに追加のメッセージがコンテキストを提供するかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-237">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="37c10-238">たとえば、Teams のコンテンツについては、これらのオプションを有効にすると、メッセージのスレッド化によって親メッセージとすべての子メッセージが取得されるようになります。</span><span class="sxs-lookup"><span data-stu-id="37c10-238">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="37c10-239">メッセージのタイムスタンプもチェックされます。</span><span class="sxs-lookup"><span data-stu-id="37c10-239">Message time stamps are also checked.</span></span> <span data-ttu-id="37c10-240">メッセージがクエリに一致した場合、そのメッセージが4時間以内に発生したか、または4時間以内に表示される近隣のメッセージは、スレッドの一部と見なされ、結果にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="37c10-240">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="37c10-241">検索クエリに一致するコンテキストメッセージを返す必要がある場合は、これらのオプションを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="37c10-241">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="37c10-242">すべてのコンテンツを収集するか、または検索の日付範囲を広げて、クエリの結果としてより多くのメッセージが返されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-242">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="37c10-243">レビューセットワークフロー</span><span class="sxs-lookup"><span data-stu-id="37c10-243">Review sets workflow</span></span>

<span data-ttu-id="37c10-244">[ **セットのレビュー** ] タブをクリックして、既存のレビューセットを表示したり、新規作成したりすることができます。レビューセットの詳細については、「 [Advanced eDiscovery でレビューセットを管理](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-244">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="37c10-245">ドキュメントに加えて、メール、チームメッセージ、Yammer メッセージ、その他のコンテンツをレビューセットに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c10-245">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="37c10-246">レビューセット内では、コンテンツの検索やカスタムクエリの作成など、他のコンテキストで実行できる操作の多くも実行できます。</span><span class="sxs-lookup"><span data-stu-id="37c10-246">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="37c10-247">これらの操作は、レビューセットに追加されたアイテムに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-247">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="37c10-248">[ **校閲セットの管理** ] ボタンには、分析、サマリーレポート、いくつのロードセットが追加されたかなどの追加オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-248">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="37c10-249">データの視覚エフェクトやグラフにアクセスするに **Individual results** は、 \> 右上にある [個々の検索結果] の [**プロフィールの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37c10-249">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="37c10-250">これらのグラフの [扇形] をクリックすると、対話形式でクエリするコンテンツの種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="37c10-250">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="37c10-251">たとえば、[チームコンテンツのみをクエリする] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="37c10-251">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="37c10-252">また、手動で作成したクエリを保存する場合と同様に、これらのクエリを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c10-252">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="37c10-253">概要ビュー、テキストビュー、および注釈ビュー</span><span class="sxs-lookup"><span data-stu-id="37c10-253">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="37c10-254">レビューセットで Teams の会話をクリックすると、 **概要ビュー** が表示され、チームの会話全体が、個別に操作できるメッセージの一覧として表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-254">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="37c10-255">メッセージの右側にある下向き矢印をクリックして、メッセージの詳細を表示したり、個別のファイルをダウンロードしたりするためのコンテキストメニューを表示し `.msg` ます。</span><span class="sxs-lookup"><span data-stu-id="37c10-255">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="37c10-256">[メッセージの詳細] をクリックすると、メタデータの概要、またはメッセージの完全なメタデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-256">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="37c10-257">PDF をダウンロードするには、概要ビューの右上にある [ダウンロード] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37c10-257">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="37c10-258">[ **テキストビュー** ] タブをクリックして、チームの会話の抽出されたテキストのテキスト形式のビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="37c10-258">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="37c10-259">このテキスト形式のコンテンツは、エクスポートに適しており、他のソフトウェアツールを使って簡単に作業することができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-259">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="37c10-260">注釈機能にアクセスするには、[ **表示の注釈** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37c10-260">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="37c10-261">このタブには、チームの会話に似た形式でコンテンツが表示されますが、編集のための追加オプションもあります。</span><span class="sxs-lookup"><span data-stu-id="37c10-261">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="37c10-262">鉛筆ツールを使用して、ノートを作成したり、メッセージに描画したり、墨消しの scratching を細かく設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-262">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="37c10-263">領域をブラックアウトする四角形を描画するために使用できる **領域の墨消し** ツールもあり、これを "Redacted" としてマークします。</span><span class="sxs-lookup"><span data-stu-id="37c10-263">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="37c10-264">ユーザー間のスレッド形式の会話用の redacted ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="37c10-264">Here's an example of a redacted file for threaded conversation between users.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37c10-265">![Redacted ファイルのスクリーンショット](media/RedactedFileExample.png)</span><span class="sxs-lookup"><span data-stu-id="37c10-265">![Screenshot of redacted file](media/RedactedFileExample.png)</span></span>

<span data-ttu-id="37c10-266">[ **表示の注釈** ] タブの下部には、[ **タグ付きドキュメント** ] ボタンがあります。このボタンをクリックすると、[タグ付け] パネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c10-266">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="37c10-267">このパネルでは、チームの会話内のすべてのメッセージにタグを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-267">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="37c10-268">会話には、応答性、または応答不可、特権、または権限なしとしてラベルを付けることができます。 "興味のあるアイテム" が含まれているかどうか、エクスポートに含めるかどうか、さらにレビューが必要かどうか。</span><span class="sxs-lookup"><span data-stu-id="37c10-268">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="37c10-269">また、他のカスタマイズ可能なノートシールを管理して適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c10-269">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="37c10-270">[アクション] メニュー</span><span class="sxs-lookup"><span data-stu-id="37c10-270">Action menu</span></span>

<span data-ttu-id="37c10-271">[校閲セット] ウィンドウで、[**アクション** のエクスポート] をクリックしてコンテンツをエクスポートでき \> **Export** ます。</span><span class="sxs-lookup"><span data-stu-id="37c10-271">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="37c10-272">エクスポートするときには、さまざまなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="37c10-272">There are many options available when exporting.</span></span>

<span data-ttu-id="37c10-273">すべての Teams メッセージのすべてのメタデータを含むファイルをエクスポートするには、[ **ファイルの読み込み** ] チェックボックスをクリックして選びます。</span><span class="sxs-lookup"><span data-stu-id="37c10-273">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="37c10-274">コンテンツに適用したタグをファイルに含めるには、[ **ノートシール** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="37c10-274">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="37c10-275">ネイティブ形式でファイルをエクスポートするには、[ **ネイティブファイル** ] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="37c10-275">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="37c10-276">会話を1つのファイルとして、または個々のチャットメッセージに個別のファイルとしてエクスポートすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="37c10-276">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="37c10-277">[ **テキストファイル** ] オプションでは、テキスト形式のコンテンツを保存することができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-277">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="37c10-278">レビューセットでチームの会話のプレーンテキストビューを取得する方法について詳しくは、「 [概要ビュー」、「テキストビュー](#summary-view-text-view-and-annotate-view) 」、「上の注釈ビュー」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="37c10-278">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="37c10-279">上の [ [概要] ビュー、[テキストビュー]、および [注釈ビュー](#summary-view-text-view-and-annotate-view) ] セクションで説明したように、コンテンツに赤のアクションを適用した場合、 **redacted natives** を [変換された pdf で置き換える] オプションを選択して、ネイティブファイルを pdf の変換済みコピーに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-279">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="37c10-280">Microsoft から提供された Azure blob ストレージコンテナーにエクスポートするか、独自の Azure Blob ストレージコンテナーを提供するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="37c10-280">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="37c10-281">エクスポートプロセスを開始する準備ができたら、[ **エクスポート** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37c10-281">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="37c10-282">エクスポートが完了した後で、Azure blob ストレージコンテナーにアクセスし、エクスポートされたコンテンツをダウンロードする方法の詳細については、「 [エクスポートジョブをダウンロード](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c10-282">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="37c10-283">エクスポートには長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="37c10-283">Exporting can take an extended period of time.</span></span> <span data-ttu-id="37c10-284">エクスポートプロセスの状態を追跡するには、[ **セットの校閲** ] タブを閉じて、[ **エクスポート** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37c10-284">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="37c10-285">関連項目</span><span class="sxs-lookup"><span data-stu-id="37c10-285">Related topics</span></span>

- [<span data-ttu-id="37c10-286">Microsoft 365 の電子情報開示</span><span class="sxs-lookup"><span data-stu-id="37c10-286">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="37c10-287">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="37c10-287">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
