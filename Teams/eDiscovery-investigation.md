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
ms.openlocfilehash: 25729dea68d2d8ea75fae894387316dfbcd1975a
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49661912"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="48732-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="48732-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="48732-104">大企業は、電子的に保存された情報 (ESI) の提出を要求する高いペナルティ法的手続きにさらされる場合が多いです。</span><span class="sxs-lookup"><span data-stu-id="48732-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="48732-105">Microsoft Teams のコンテンツは、電子情報開示の調査中に検索して使用できます。</span><span class="sxs-lookup"><span data-stu-id="48732-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="48732-106">概要</span><span class="sxs-lookup"><span data-stu-id="48732-106">Overview</span></span>

<span data-ttu-id="48732-107">すべての Microsoft Teams 1 対 1 またはグループ チャットは、各ユーザーのメールボックスにジャーナル処理されます。</span><span class="sxs-lookup"><span data-stu-id="48732-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="48732-108">すべての標準チャネル メッセージは、チームを表すグループ メールボックスにジャーナリングされます。</span><span class="sxs-lookup"><span data-stu-id="48732-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="48732-109">標準チャネルでアップロードされたファイルは、SharePoint Online と OneDrive for Business の電子情報開示機能の下で扱います。</span><span class="sxs-lookup"><span data-stu-id="48732-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="48732-110">プライベート チャネル内のメッセージとファイルの電子情報開示は [、](private-channels.md) 標準チャネルとは異なる方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="48732-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="48732-111">詳細については、プライベート チャネル [の電子情報開示を参照してください](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="48732-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="48732-112">すべての Teams コンテンツが eDiscoverable という訳ではありません。</span><span class="sxs-lookup"><span data-stu-id="48732-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="48732-113">次の表は、電子情報開示を介して検索できるコンテンツ タイプを示しています。</span><span class="sxs-lookup"><span data-stu-id="48732-113">The following table shows the content types that can be located through eDiscovery.</span></span>

| <span data-ttu-id="48732-114">コンテンツの種類</span><span class="sxs-lookup"><span data-stu-id="48732-114">Content type</span></span> | <span data-ttu-id="48732-115">eDiscoverable</span><span class="sxs-lookup"><span data-stu-id="48732-115">eDiscoverable</span></span> | <span data-ttu-id="48732-116">メモ</span><span class="sxs-lookup"><span data-stu-id="48732-116">Notes</span></span> |
|:--- | --- |:--- |
| <span data-ttu-id="48732-117">Teams のチャット メッセージ</span><span class="sxs-lookup"><span data-stu-id="48732-117">Teams chat messages</span></span> | <span data-ttu-id="48732-118">はい</span><span class="sxs-lookup"><span data-stu-id="48732-118">Yes</span></span> |  |
| <span data-ttu-id="48732-119">プライベート チャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="48732-119">Private channel messages</span></span> | <span data-ttu-id="48732-120">はい</span><span class="sxs-lookup"><span data-stu-id="48732-120">Yes</span></span> | |
| <span data-ttu-id="48732-121">チャネルの名前</span><span class="sxs-lookup"><span data-stu-id="48732-121">Name of channel</span></span> | <span data-ttu-id="48732-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="48732-122">No</span></span> | |
| <span data-ttu-id="48732-123">会議の IM 会話</span><span class="sxs-lookup"><span data-stu-id="48732-123">Meeting IM conversations</span></span> | <span data-ttu-id="48732-124">はい</span><span class="sxs-lookup"><span data-stu-id="48732-124">Yes</span></span> | |
| <span data-ttu-id="48732-125">会議のメタデータ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="48732-125">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="48732-126">はい</span><span class="sxs-lookup"><span data-stu-id="48732-126">Yes</span></span> |  |
| <span data-ttu-id="48732-127">編集したメッセージ</span><span class="sxs-lookup"><span data-stu-id="48732-127">Edited messages</span></span> | <span data-ttu-id="48732-128">はい</span><span class="sxs-lookup"><span data-stu-id="48732-128">Yes</span></span> | <span data-ttu-id="48732-129">ユーザーが保留されている場合、以前のバージョンの編集されたメッセージは保持されます。</span><span class="sxs-lookup"><span data-stu-id="48732-129">If the user is on hold, previous versions of edited messages are preserved.</span></span> |
| <span data-ttu-id="48732-130">絵文字、GIF、ステッカー</span><span class="sxs-lookup"><span data-stu-id="48732-130">Emojis, GIFs, stickers</span></span> | <span data-ttu-id="48732-131">はい</span><span class="sxs-lookup"><span data-stu-id="48732-131">Yes</span></span> | |
| <span data-ttu-id="48732-132">コード スニペット</span><span class="sxs-lookup"><span data-stu-id="48732-132">Code snippets</span></span> | <span data-ttu-id="48732-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="48732-133">No</span></span> | |
| <span data-ttu-id="48732-134">チャット リンク</span><span class="sxs-lookup"><span data-stu-id="48732-134">Chat links</span></span> | <span data-ttu-id="48732-135">はい</span><span class="sxs-lookup"><span data-stu-id="48732-135">Yes</span></span> | |
| <span data-ttu-id="48732-136">リアクション (「良いね!」や「ハート」など)</span><span class="sxs-lookup"><span data-stu-id="48732-136">Reactions (likes, hearts, and so on)</span></span> | <span data-ttu-id="48732-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="48732-137">No</span></span> | |
| <span data-ttu-id="48732-138">インライン画像</span><span class="sxs-lookup"><span data-stu-id="48732-138">Inline images</span></span> | <span data-ttu-id="48732-139">はい</span><span class="sxs-lookup"><span data-stu-id="48732-139">Yes</span></span> | |
| <span data-ttu-id="48732-140">テーブル</span><span class="sxs-lookup"><span data-stu-id="48732-140">Tables</span></span> | <span data-ttu-id="48732-141">はい</span><span class="sxs-lookup"><span data-stu-id="48732-141">Yes</span></span> | |
| <span data-ttu-id="48732-142">件名</span><span class="sxs-lookup"><span data-stu-id="48732-142">Subject</span></span> | <span data-ttu-id="48732-143">はい</span><span class="sxs-lookup"><span data-stu-id="48732-143">Yes</span></span> | |
| <span data-ttu-id="48732-144">見積もり</span><span class="sxs-lookup"><span data-stu-id="48732-144">Quotes</span></span> | <span data-ttu-id="48732-145">はい</span><span class="sxs-lookup"><span data-stu-id="48732-145">Yes</span></span> | <span data-ttu-id="48732-146">引用符で囲まれたコンテンツは検索可能です。</span><span class="sxs-lookup"><span data-stu-id="48732-146">Quoted content is searchable.</span></span> <span data-ttu-id="48732-147">ただし、検索結果は、コンテンツが引用されたというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="48732-147">However, search results don't indicate that the content was quoted.</span></span> |
| <span data-ttu-id="48732-148">オーディオ録音</span><span class="sxs-lookup"><span data-stu-id="48732-148">Audio recordings</span></span> | <span data-ttu-id="48732-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="48732-149">No</span></span> | |

<span data-ttu-id="48732-150"><sup>1 つの</sup> 会議 (および通話) メタデータには、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48732-150"><sup>1</sup> Meeting (and call) metadata includes the following:</span></span>

- <span data-ttu-id="48732-151">会議の開始時刻と終了時刻、および期間</span><span class="sxs-lookup"><span data-stu-id="48732-151">Meeting start and end time, and duration</span></span>
- <span data-ttu-id="48732-152">各参加者の会議参加イベントと退出イベント</span><span class="sxs-lookup"><span data-stu-id="48732-152">Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="48732-153">VOIP の参加/通話</span><span class="sxs-lookup"><span data-stu-id="48732-153">VOIP join/calls</span></span>
- <span data-ttu-id="48732-154">匿名参加</span><span class="sxs-lookup"><span data-stu-id="48732-154">Anonymous join</span></span>
- <span data-ttu-id="48732-155">フェデレーション ユーザーの参加</span><span class="sxs-lookup"><span data-stu-id="48732-155">Federated user join</span></span>
- <span data-ttu-id="48732-156">ゲスト ユーザーの参加</span><span class="sxs-lookup"><span data-stu-id="48732-156">Guest user join</span></span>

<span data-ttu-id="48732-157">画像はメタデータの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="48732-157">The image shows an example of the metadata.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="48732-158">![画像は、CVR レコードの会議メタデータの画像です。](media/conversationOption3.png)</span><span class="sxs-lookup"><span data-stu-id="48732-158">![Image is of the CVR records meeting metadata.](media/conversationOption3.png)</span></span>

<span data-ttu-id="48732-159">会議中の参加者間の IM 会話の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="48732-159">Here's an example of IM conversation between participants during the meeting.</span></span>

![Teams の参加者間の会話。](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> <span data-ttu-id="48732-161">![電子情報開示検索結果の参加者間の会話。](media/MeetingImConversation2.png)</span><span class="sxs-lookup"><span data-stu-id="48732-161">![Conversation between participants in eDiscovery search results.](media/MeetingImConversation2.png)</span></span>

<span data-ttu-id="48732-162">電子情報開示調査の実施の詳細については、「コア電子情報開示の使用を開始する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="48732-162">For more information about conducting an eDiscovery investigation, see [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="48732-163">Microsoft Teams のデータは、Excel の電子情報開示エクスポート出力に IM またはスレッドとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-163">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="48732-164">Outlook でファイルを `.pst` 開き、エクスポート後にそれらのメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="48732-164">You can open the `.pst` file in Outlook to view those messages after export.</span></span>

<span data-ttu-id="48732-165">チームの .pst ファイルを表示すると、すべての会話が [会話履歴] の [チーム チャット] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="48732-165">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="48732-166">メッセージのタイトルには、チーム名とチャネル名が含まれている。</span><span class="sxs-lookup"><span data-stu-id="48732-166">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="48732-167">たとえば、次の画像は、製造仕様チームの Project 7 標準チャネルにメッセージを送信した Bob からのメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="48732-167">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook のユーザーのメールボックス内のチーム チャット フォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="48732-169">ユーザーのメールボックス内のプライベート チャットは、[会話履歴] の下の [チーム チャット] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="48732-169">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="48732-170">プライベート チャネルの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="48732-170">eDiscovery of private channels</span></span>

<span data-ttu-id="48732-171">プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="48732-171">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="48732-172">レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="48732-172">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="48732-173">各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイトが用意されています。プライベート チャネル内のファイルは、親チームとは独立して管理されます。</span><span class="sxs-lookup"><span data-stu-id="48732-173">Because each private channel has its own SharePoint site that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="48732-174">Teams は、チーム内の 1 つのチャネルの電子情報開示検索をサポートしないので、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48732-174">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="48732-175">プライベート チャネル内のコンテンツの電子情報開示検索を実行するには、チーム、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含める)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。</span><span class="sxs-lookup"><span data-stu-id="48732-175">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="48732-176">次の手順を使用して、電子情報開示検索に含めるプライベート チャネル内のファイルとメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="48732-176">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="48732-177">電子情報開示検索にプライベート チャネル ファイルを含める</span><span class="sxs-lookup"><span data-stu-id="48732-177">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="48732-178">これらの手順を実行する前に、SharePoint Online 管理シェルをインストールし [、SharePoint Online に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="48732-178">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

1. <span data-ttu-id="48732-179">チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="48732-179">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="48732-180">次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクション URL と親チーム グループ ID の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="48732-180">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="48732-181">チームまたはグループ ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベート チャネル サイトを特定します。$groupID はチームのグループ ID です。</span><span class="sxs-lookup"><span data-stu-id="48732-181">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="48732-182">電子情報開示検索にプライベート チャネル メッセージを含める</span><span class="sxs-lookup"><span data-stu-id="48732-182">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="48732-183">これらの手順を実行する前に、最新バージョンの [Teams PowerShell モジュールがインストールされていることを確認](teams-powershell-overview.md) します。</span><span class="sxs-lookup"><span data-stu-id="48732-183">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="48732-184">次のコマンドを実行して、チーム内のプライベート チャネルの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="48732-184">Run the following command to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="48732-185">次のコマンドを実行して、プライベート チャネル メンバーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="48732-185">Run the following command to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="48732-186">電子情報開示検索クエリの一部として、チームの各プライベート チャネルのすべてのメンバーの [メールボックスを含める](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="48732-186">Include the mailboxes of all members from each private channel in the team as part of your [eDiscovery search query](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery).</span></span>

## <a name="search-for-content-for-guest-users"></a><span data-ttu-id="48732-187">ゲスト ユーザーのコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="48732-187">Search for content for guest users</span></span>

<span data-ttu-id="48732-188">電子情報開示ツールを使用して、組織内のゲスト ユーザーに関連する Teams コンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="48732-188">You can use eDiscovery tools to search for Teams content related to guest users in your organization.</span></span> <span data-ttu-id="48732-189">ゲスト ユーザーに関連付けられている Teams チャット コンテンツは、クラウドベースの保存場所に保持され、電子情報開示を使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="48732-189">Teams chat content that's associated with a guest user is preserved in a cloud-based storage location and can be searched for using eDiscovery.</span></span> <span data-ttu-id="48732-190">これには、ゲスト ユーザーが組織内の他のユーザーとの参加者である 1 対 1 と 1:N のチャット会話のコンテンツの検索が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48732-190">This includes searching for content in 1:1 and 1:N chat conversations in which a guest user is a participant with other users in your organization.</span></span> <span data-ttu-id="48732-191">ゲスト ユーザーが参加者であるプライベート チャネル メッセージを検索し、ゲスト *と* ゲスト チャットの会話のコンテンツを検索することもできます。ゲスト ユーザーはゲスト ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="48732-191">You can also search for private channel messages in which a guest user is a participant and search for content in *guest:guest* chat conversations where the only participants are guest users.</span></span>

<span data-ttu-id="48732-192">ゲスト ユーザーのコンテンツを検索するには:</span><span class="sxs-lookup"><span data-stu-id="48732-192">To search for content for guest users:</span></span>

1. <span data-ttu-id="48732-193">Azure AD PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="48732-193">Connect to Azure AD PowerShell.</span></span> <span data-ttu-id="48732-194">手順については、「PowerShell を使用して Microsoft 365 に接続する」の「Azure Active Directory PowerShell で接続する [」セクションを参照してください](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="48732-194">For instructions, see the "Connect with the Azure Active Directory PowerShell" section in [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="48732-195">前のトピックの手順 1 と手順 2 を必ず完了してください。</span><span class="sxs-lookup"><span data-stu-id="48732-195">Be sure to complete Step 1 and Step 2 in the previous topic.</span></span>

2. <span data-ttu-id="48732-196">Azure AD PowerShell に正常に接続したら、次のコマンドを実行して、組織内のすべてのゲスト ユーザーのユーザー プリンシパル名 (UPN) を表示します。</span><span class="sxs-lookup"><span data-stu-id="48732-196">After you successfully connect to Azure AD PowerShell, run the following command to display the user principal name (UPN) for all guest users in your organization.</span></span> <span data-ttu-id="48732-197">手順 4 で検索を作成する場合は、ゲスト ユーザーの UPN を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48732-197">You have to use the UPN of the guest user when you create the search in step 4.</span></span>

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > <span data-ttu-id="48732-198">コンピューター画面にユーザー プリンシパル名のリストを表示する代わりに、コマンドの出力をテキスト ファイルにリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="48732-198">Instead of displaying a list of user principal names on the computer screen, you can redirect the output of the command to a text file.</span></span> <span data-ttu-id="48732-199">この操作を行うには、前の `> filename.txt` コマンドに追加します。</span><span class="sxs-lookup"><span data-stu-id="48732-199">You can do this by appending `> filename.txt` to the previous command.</span></span> <span data-ttu-id="48732-200">ユーザー プリンシパル名を含むテキスト ファイルは、現在のフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="48732-200">The text file with the user principal names will be saved to the current folder.</span></span>

3. <span data-ttu-id="48732-201">別のウィンドウWindows PowerShell、セキュリティ/コンプライアンス センターの PowerShell &接続します。</span><span class="sxs-lookup"><span data-stu-id="48732-201">In a different Windows PowerShell window, connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="48732-202">手順については、「セキュリティ/コンプライアンス [センター PowerShell への&を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="48732-202">For instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="48732-203">多要素認証を使用するか、または使用せずに接続できます。</span><span class="sxs-lookup"><span data-stu-id="48732-203">You can connect with or without using multi-factor authentication.</span></span>

4. <span data-ttu-id="48732-204">次のコマンドを実行して、指定したゲスト ユーザーが参加者だったすべてのコンテンツ (チャット メッセージやメール メッセージなど) を検索するコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="48732-204">Create a content search that searches for all content (such as chat messages and email messages) in which the specified guest user was a participant by running the following command.</span></span>

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   <span data-ttu-id="48732-205">たとえば、ゲスト ユーザー Sara Davis に関連付けられているコンテンツを検索するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="48732-205">For example, to search for content associated with the guest user Sara Davis, you would run the following command.</span></span>

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    <span data-ttu-id="48732-206">PowerShell を使用してコンテンツ検索を作成する方法の詳細については [、「New-ComplianceSearch」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)。</span><span class="sxs-lookup"><span data-stu-id="48732-206">For more information about using PowerShell to create content searches, see [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch).</span></span>

5. <span data-ttu-id="48732-207">次のコマンドを実行して、手順 4 で作成したコンテンツ検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="48732-207">Run the following command to start the content search that you created in step 4:</span></span>

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. <span data-ttu-id="48732-208">[すべてのコンテンツ [https://compliance.microsoft.com](https://compliance.microsoft.com) 検索を表示] に  >  **移動し、[すべてのコンテンツ検索を表示] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="48732-208">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Show all** > **Content search**.</span></span>

7. <span data-ttu-id="48732-209">検索の一覧で、手順 4 で作成した検索を選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="48732-209">In the list of searches, select the search that you created in step 4 to display the flyout page.</span></span>

8. <span data-ttu-id="48732-210">フライアウト ページでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48732-210">On the flyout page, you can do the following things:</span></span>

   - <span data-ttu-id="48732-211">[ **結果の表示]** をクリックして検索結果を表示し、コンテンツをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="48732-211">Click **View results** to view the search results and preview the content.</span></span>

   - <span data-ttu-id="48732-212">[クエリ] **フィールドの横** にある [編集] を **クリック** して編集し、検索を再実行します。</span><span class="sxs-lookup"><span data-stu-id="48732-212">Next to the **Query** field, click **Edit** to edit and then rerun the search.</span></span> <span data-ttu-id="48732-213">たとえば、検索クエリを追加して結果を絞り込むなどです。</span><span class="sxs-lookup"><span data-stu-id="48732-213">For example, you can add a search query to narrow the results.</span></span>

   - <span data-ttu-id="48732-214">[ **結果のエクスポート] を** クリックして、検索結果をエクスポートしてダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="48732-214">Click **Export results** to export and download the search results.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="48732-215">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="48732-215">Advanced eDiscovery</span></span>

<span data-ttu-id="48732-216">一部の Microsoft Teams コンテンツは、Advanced eDiscovery ワークフローを使用して検索 [および保持できます](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="48732-216">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="48732-217">電子情報開示にはさまざまな検索、保留、およびエクスポート機能が含まれていますが、Advanced eDiscovery では、コンプライアンス管理者がデータ ソースを特定し、その内容を分析するためのより多くのツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="48732-217">While eDiscovery provides a range of search, hold, and export functionality, advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="48732-218">Teams コンテンツの高度な電子情報開示カストディアン ワークフロー</span><span class="sxs-lookup"><span data-stu-id="48732-218">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="48732-219">カストディアンは、さまざまなチームのメンバーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48732-219">Custodians might be a member of various teams.</span></span> <span data-ttu-id="48732-220">これらのカストディアンに関連する Teams コンテンツをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="48732-220">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="48732-221">カストディアン ワークフローの手順については、「Advanced eDiscovery ケースにカストディアンを追加する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="48732-221">For instructions on the custodian workflow, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

<span data-ttu-id="48732-222">カストディアンを追加したら、[次へ] ボタン **をクリック** し、[追加] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="48732-222">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="48732-223">ウィンドウが表示され、追加の場所を選択するように求めるメッセージが表示されます。このウィンドウには、カストディアンのすべてのメンバーシップとそのデータに対応する SharePoint サイトの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-223">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="48732-224">これらのすべてのデータ ソースとチームから、電子情報開示に使用するコンテンツを選び、そのユーザーと、特定したすべてのデータ ソースを保留にできます。</span><span class="sxs-lookup"><span data-stu-id="48732-224">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="48732-225">Exchange コンテンツ、OneDrive コンテンツ、または両方を含めるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="48732-225">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="48732-226">Exchange コンテンツには、ユーザーのメールボックス内のすべてのアプリケーション コンテンツ (メール、メールボックスに保存されている Teams コンテンツなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48732-226">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="48732-227">OneDrive のコンテンツには、ユーザーのコンテンツだけでなく、1 対 1 のチャット、1:N チャット、チャットで共有されているファイルなど、OneDrive に保存されている Teams のすべてのコンテンツも含まれます。</span><span class="sxs-lookup"><span data-stu-id="48732-227">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="48732-228">また、カストディアンがメンバーであるチームを関連付け、カストディアンがアクセスできるチャネル チャット メッセージとファイルを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="48732-228">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="48732-229">さらに、他のすべてのチームをカストディアンと関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="48732-229">Additionally, any other team can be associated with a custodian.</span></span>

> [!NOTE]
> <span data-ttu-id="48732-230">プライベート チャネル内のメッセージとファイルの電子情報開示は [、](private-channels.md) 標準チャネルとは異なる方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="48732-230">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="48732-231">詳細については、プライベート チャネル [の電子情報開示を参照してください](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="48732-231">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="48732-232">データ ソースを保留する</span><span class="sxs-lookup"><span data-stu-id="48732-232">Placing a data source on hold</span></span>

<span data-ttu-id="48732-233">カストディアンとして指定する特定のユーザーがない場合は、データ ソース全体を保留にできます。</span><span class="sxs-lookup"><span data-stu-id="48732-233">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="48732-234">保留の詳細については、「Advanced eDiscovery で保留を管理する [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。</span><span class="sxs-lookup"><span data-stu-id="48732-234">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="48732-235">Teams コンテンツの保留リストを作成する場合は、保留に含めるすべての場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="48732-235">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="48732-236">ユーザーがコンテンツを削除または変更している場合でも、保留すると、そのコンテンツのすべての以前のバージョンのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="48732-236">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="48732-237">オプションのクエリを使用して、キーワード、日付範囲、作成者、その他の多くの条件に基づいて保留の条件を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="48732-237">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="48732-238">キーワードを指定しない場合、そのデータ ソースのすべての内容が保留の対象と見なされます。</span><span class="sxs-lookup"><span data-stu-id="48732-238">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="48732-239">高度な電子情報開示検索</span><span class="sxs-lookup"><span data-stu-id="48732-239">Advanced eDiscovery searches</span></span>

<span data-ttu-id="48732-240">Teams のコンテンツも検索できます。</span><span class="sxs-lookup"><span data-stu-id="48732-240">Teams content can also be searched.</span></span> <span data-ttu-id="48732-241">検索の詳細については [、「Advanced eDiscovery でケースのデータを収集する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="48732-241">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="48732-242">1 つのメッセージが検索クエリと一致する場合でも、検索は会話全体を返します。</span><span class="sxs-lookup"><span data-stu-id="48732-242">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="48732-243">検索クエリを作成するときに、既に選択しているすべてのソースが検索されるカストディアンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="48732-243">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="48732-244">また、ユーザーにマップされていない Teams サイトなど、管理者以外のソースを検索できます。</span><span class="sxs-lookup"><span data-stu-id="48732-244">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="48732-245">Teams コンテンツ内の検索を絞り込むには、オプションのクエリも使用できます。</span><span class="sxs-lookup"><span data-stu-id="48732-245">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="48732-246">検索を作成して選択すると、ウィンドウが表示され、選択した検索に対して実行できる追加の詳細とアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-246">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="48732-247">[統計情報]ボタンをクリックすると、場所の種類、コンテンツの元のソースに応じて内訳が表示され、コンテンツがグループ メールボックス、個々のユーザー メールボックス、または SharePoint サイトにあるかどうかなど、検索に関する統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="48732-247">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="48732-248">したがって、どのソースが検索結果に貢献しているのかの内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="48732-248">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="48732-249">また、クエリ ビュー **も** 利用できます。クエリ ビューでは、結果にどのキーワードが関連付けられているのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="48732-249">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="48732-250">検索を完了した後、[結果をレビュー セットに追加] ボタンをクリックし、レビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="48732-250">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="48732-251">レビュー セットの詳細については、この記事の後半にある [「Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) ワークフローと [レビュー](#review-sets-workflow) セット ワークフローでレビュー セットを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48732-251">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="48732-252">標準レビュー セットとスレッド レビュー セット</span><span class="sxs-lookup"><span data-stu-id="48732-252">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="48732-253">レビュー セットに検索を追加する場合は、通常のレビュー セットまたは会話レビュー セットから選択できます。</span><span class="sxs-lookup"><span data-stu-id="48732-253">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="48732-254">通常のレビュー セットはエクスポートに似ています。Teams コンテンツの `.msg` 個々のファイルを提供し、基本的なビューでコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="48732-254">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="48732-255">通常、他のソフトウェア ツールを使用して後でファイルを再処理する場合は、通常のレビュー セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="48732-255">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="48732-256">会話レビュー セットは、会話のより直感的でスレッド化されたビューを提供します。関連するメッセージが適切な順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-256">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="48732-257">![会話レビュー セットのスクリーンショット](media/conversationOptions2.png)</span><span class="sxs-lookup"><span data-stu-id="48732-257">![Screenshot of conversation review set](media/conversationOptions2.png)</span></span>

<span data-ttu-id="48732-258">やり直しなどの機能は、両方の種類のレビュー セットで使用できます。</span><span class="sxs-lookup"><span data-stu-id="48732-258">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="48732-259">レビュー セットの詳細については、「Advanced eDiscovery での会話 [のレビュー」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="48732-259">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="48732-260">コレクション のオプション</span><span class="sxs-lookup"><span data-stu-id="48732-260">Collection options</span></span>

<span data-ttu-id="48732-261">レビュー セットに追加する場合、ウィンドウの [コレクション オプション]セクションのチェック ボックスとして、[会話の取得オプション] や [Teams の会話] など、いくつかの **オプションを\*\*\*\*使用できます**。</span><span class="sxs-lookup"><span data-stu-id="48732-261">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="48732-262">これらのオプションを有効にした場合、レビュー セットの一部である個々の Teams メッセージも、コンテキストのためにそれらを囲む追加のメッセージと一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-262">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="48732-263">たとえば、クエリが特定であり、結果として 1 つのメッセージだけが返される場合、これらのオプションを有効にすると、クエリに一致したメッセージの後に続く複数のメッセージも返されます。</span><span class="sxs-lookup"><span data-stu-id="48732-263">For example, if your query is specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="48732-264">多くの論理的な条件は、追加のメッセージがクエリに一致するメッセージにコンテキストを提供するかどうかを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="48732-264">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="48732-265">たとえば、Teams コンテンツの場合、これらのオプションを有効にすると、メッセージのスレッド化方法のために、親メッセージとすべての子メッセージが取得されます。</span><span class="sxs-lookup"><span data-stu-id="48732-265">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="48732-266">メッセージのタイム スタンプもチェックされます。</span><span class="sxs-lookup"><span data-stu-id="48732-266">Message time stamps are also checked.</span></span> <span data-ttu-id="48732-267">メッセージがクエリと一致する場合、メッセージの前に 4 時間の範囲にあるか、4 時間以内に続く隣接するメッセージは会話の一部であると見なされ、結果にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="48732-267">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="48732-268">検索クエリに一致するコンテキスト メッセージを確実に返す必要がある場合は、これらのオプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48732-268">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="48732-269">すべてのコンテンツを収集するか、検索の日付範囲を広くして、クエリの結果として返されるメッセージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="48732-269">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="48732-270">レビュー セットワークフロー</span><span class="sxs-lookup"><span data-stu-id="48732-270">Review sets workflow</span></span>

<span data-ttu-id="48732-271">既存のレビュー セットを表示したり、[レビュー セット] タブをクリックして新しいレビュー セット **を作成** することができます。レビュー セットの詳細については、「Advanced eDiscovery でレビュー セット [を管理する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="48732-271">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="48732-272">ドキュメントに加えて、メール、Teams メッセージ、Yammer、その他のコンテンツをレビュー セットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="48732-272">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="48732-273">レビュー セット内では、コンテンツの検索やカスタム クエリの作成など、他のコンテキストで実行できる操作の多くを実行できます。</span><span class="sxs-lookup"><span data-stu-id="48732-273">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="48732-274">これらの操作は、レビュー セットに追加されたアイテムにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="48732-274">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="48732-275">[ **レビュー セットの管理** ] ボタンには、分析、サマリー レポート、追加されたロード セットの数などの追加オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-275">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="48732-276">データの視覚エフェクトやグラフにアクセスするには、右上にある [個々の **結果** の検索 \> ] プロファイル ビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48732-276">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="48732-277">これらのグラフのくさび形をクリックすると、クエリを実行するコンテンツの種類を対話的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="48732-277">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="48732-278">たとえば、Teams のコンテンツにのみクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="48732-278">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="48732-279">手動で作成したクエリを保存するのと同じ方法で、これらのクエリを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="48732-279">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="48732-280">概要ビュー、テキスト ビュー、注釈ビュー</span><span class="sxs-lookup"><span data-stu-id="48732-280">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="48732-281">レビュー セットで Teams の会話をクリックすると、[概要]ビューが表示され、Teams の会話全体が個別にやり取りできるメッセージの一覧として表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-281">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="48732-282">メッセージの右側にある下向き矢印をクリックすると、メッセージの詳細を表示したり、個々のファイルをダウンロードしたりできるコンテキスト メニューが表示 `.msg` されます。</span><span class="sxs-lookup"><span data-stu-id="48732-282">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="48732-283">メッセージの詳細をクリックすると、メタデータの概要またはメッセージの完全なメタデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-283">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="48732-284">PDF をダウンロードするには、概要ビューの右上にあるダウンロード ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48732-284">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="48732-285">[テキスト **ビュー] タブを** クリックすると、Teams の会話の抽出されたテキストのプレーン テキスト ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-285">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="48732-286">このテキスト形式のコンテンツはエクスポートに適しています。他のソフトウェア ツールを使用して簡単に作業できます。</span><span class="sxs-lookup"><span data-stu-id="48732-286">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="48732-287">コメント機能にアクセス **するには、[注釈ビュー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48732-287">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="48732-288">このタブには、Teams の会話に似た形式でコンテンツが表示されますが、編集するためのその他のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="48732-288">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="48732-289">鉛筆ツールを使用して、メモを作成したり、メッセージに描画したり、やり直しのために細かいスクラッチを行う場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="48732-289">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="48732-290">領域を黒くして "赤くながった" とマークする四角形を描画するために使用できる領域の再編集ツールもあります。</span><span class="sxs-lookup"><span data-stu-id="48732-290">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="48732-291">次に、ユーザー間のスレッド化された会話に対して、破損したファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="48732-291">Here's an example of a redacted file for threaded conversation between users.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="48732-292">![破損したファイルのスクリーンショット](media/RedactedFileExample.png)</span><span class="sxs-lookup"><span data-stu-id="48732-292">![Screenshot of redacted file](media/RedactedFileExample.png)</span></span>

<span data-ttu-id="48732-293">[注釈ビュー] **タブの** 下部には、[タグ **付** けドキュメント] ボタンが表示され、タグ付けパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48732-293">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="48732-294">このパネル内で、Teams の会話内のすべてのメッセージにタグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="48732-294">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="48732-295">会話に "興味を持つアイテム" が含まれているかどうか、エクスポートに含める必要があるかどうか、さらにレビューが必要かどうかなど、応答型または非応答型、特権付き、または特権ではない会話としてラベルを付けできます。</span><span class="sxs-lookup"><span data-stu-id="48732-295">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="48732-296">その他のカスタマイズ可能なタグを管理して適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="48732-296">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="48732-297">アクション メニュー</span><span class="sxs-lookup"><span data-stu-id="48732-297">Action menu</span></span>

<span data-ttu-id="48732-298">[レビュー セット] ウィンドウ内で、[アクション エクスポート] をクリックしてコンテンツ **をエクスポート** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="48732-298">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="48732-299">エクスポート時には、多くのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="48732-299">There are many options available when exporting.</span></span>

<span data-ttu-id="48732-300">すべての Teams メッセージのすべてのメタデータを含むファイルをエクスポートするには、[ファイルの読み込み] チェック ボックス **をオンにします** 。</span><span class="sxs-lookup"><span data-stu-id="48732-300">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="48732-301">コンテンツに適用したタグをファイルに含めるには、[タグ] チェック ボックスを **オン** にします。</span><span class="sxs-lookup"><span data-stu-id="48732-301">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="48732-302">[ネイティブ ファイル **] オプションを使用** して、ネイティブ形式でファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="48732-302">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="48732-303">1 つの会話を 1 つのファイルとしてエクスポートするか、個別のファイル内のすべてのチャット メッセージとしてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="48732-303">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="48732-304">[ **テキスト ファイル]** オプションでは、テキスト形式のコンテンツを保存できます。</span><span class="sxs-lookup"><span data-stu-id="48732-304">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="48732-305">レビュー セットで Teams の会話のプレーン テキスト ビューを取得する方法の詳細については、上記の概要ビュー、テキスト ビュー、注釈 [ビューを参照](#summary-view-text-view-and-annotate-view) してください。</span><span class="sxs-lookup"><span data-stu-id="48732-305">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="48732-306">上の概要ビュー、テキスト ビュー、注釈ビューセクションで説明[](#summary-view-text-view-and-annotate-view)したように、コンテンツにやり直しを適用した場合は、[変換された PDFで編集したネイティブを置き換える] オプションを選択して、ネイティブ ファイルを PDF 内の変換されたコピーに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="48732-306">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="48732-307">Microsoft が提供する Azure BLOB ストレージ コンテナーにエクスポートするか、独自の Azure BLOB ストレージ コンテナーを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="48732-307">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="48732-308">エクスポート プロセスを開始する準備ができたら、[エクスポート] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="48732-308">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="48732-309">エクスポート [が完了したら、Azure](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) BLOB ストレージ コンテナーにアクセスし、エクスポートしたコンテンツをダウンロードする方法の詳細については、エクスポート ジョブのダウンロードに関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48732-309">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="48732-310">エクスポートには、長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="48732-310">Exporting can take an extended period of time.</span></span> <span data-ttu-id="48732-311">エクスポート プロセスの状態を追跡するには、[レビューセット] タブを終了し、[エクスポート] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="48732-311">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="48732-312">関連項目</span><span class="sxs-lookup"><span data-stu-id="48732-312">Related topics</span></span>

- [<span data-ttu-id="48732-313">Microsoft 365 の電子情報開示</span><span class="sxs-lookup"><span data-stu-id="48732-313">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="48732-314">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="48732-314">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
