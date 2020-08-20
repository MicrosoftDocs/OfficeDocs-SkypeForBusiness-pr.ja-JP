---
title: コンテンツの電子情報開示調を行う
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
description: 電子情報開示を実行する必要がある場合、たとえば、すべての電子情報開示を正しく処理する必要がある場合などに、電子情報開示を実行する必要がある場合について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4679d8ed59ab8eec0fb856961f646d1f20049ff3
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814113"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="c4954-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="c4954-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="c4954-104">大規模企業は、すべての電子的に保存された情報 (ESI) の送信をデモンダルに進めている、高価な業者に対して発行することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="c4954-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span> <span data-ttu-id="c4954-105">Microsoft Teams のコンテンツは、電子情報開示調査中に検索および使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-105">Microsoft Teams content can be searched and used during eDiscovery investigations.</span></span>

## <a name="overview"></a><span data-ttu-id="c4954-106">概要</span><span class="sxs-lookup"><span data-stu-id="c4954-106">Overview</span></span>

<span data-ttu-id="c4954-107">Microsoft Teams 1:1 またはグループのチャットはそれぞれのユーザーのメールボックスに基してジャーナルされます。</span><span class="sxs-lookup"><span data-stu-id="c4954-107">All Microsoft Teams 1:1 or group chats are journaled through to the respective users' mailboxes.</span></span> <span data-ttu-id="c4954-108">標準チャネル メッセージはすべて、チームを表すグループ メールボックスにジャーナルされます。</span><span class="sxs-lookup"><span data-stu-id="c4954-108">All standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="c4954-109">標準チャネルでアップロードされたファイルは、SharePoint Online と OneDrive for Business の電子情報開示機能に関する説明です。</span><span class="sxs-lookup"><span data-stu-id="c4954-109">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="c4954-110">プライベート チャネル内のメッセージや [ファイル](private-channels.md) の電子情報開示は、標準チャネルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c4954-110">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="c4954-111">詳細については、プライ [ベート チャネルの電子情報開示を参照してください](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="c4954-111">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

<span data-ttu-id="c4954-112">Teams のすべてのコンテンツが電子情報開示可能であるとはありません。</span><span class="sxs-lookup"><span data-stu-id="c4954-112">Not all Teams content is eDiscoverable.</span></span> <span data-ttu-id="c4954-113">次の表は、電子情報開示で見つけるコンテンツ タイプを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4954-113">The following table shows the content types that can be located through eDiscovery.</span></span>

| <span data-ttu-id="c4954-114">コンテンツの種類</span><span class="sxs-lookup"><span data-stu-id="c4954-114">Content type</span></span> | <span data-ttu-id="c4954-115">電子情報開示可能</span><span class="sxs-lookup"><span data-stu-id="c4954-115">eDiscoverable</span></span> | <span data-ttu-id="c4954-116">メモ</span><span class="sxs-lookup"><span data-stu-id="c4954-116">Notes</span></span> |
|:--- | --- |:--- |
| <span data-ttu-id="c4954-117">Teams のチャット メッセージ</span><span class="sxs-lookup"><span data-stu-id="c4954-117">Teams chat messages</span></span> | <span data-ttu-id="c4954-118">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-118">Yes</span></span> |  |
| <span data-ttu-id="c4954-119">プライベート チャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="c4954-119">Private channel messages</span></span> | <span data-ttu-id="c4954-120">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-120">Yes</span></span> | |
| <span data-ttu-id="c4954-121">チャンネルの名前</span><span class="sxs-lookup"><span data-stu-id="c4954-121">Name of channel</span></span> | <span data-ttu-id="c4954-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4954-122">No</span></span> | |
| <span data-ttu-id="c4954-123">会議の IM 会話</span><span class="sxs-lookup"><span data-stu-id="c4954-123">Meeting IM conversations</span></span> | <span data-ttu-id="c4954-124">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-124">Yes</span></span> | |
| <span data-ttu-id="c4954-125">会議メタデータ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c4954-125">Meeting metadata<sup>1</sup></span></span> | <span data-ttu-id="c4954-126">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-126">Yes</span></span> |  |
| <span data-ttu-id="c4954-127">編集済みメッセージ</span><span class="sxs-lookup"><span data-stu-id="c4954-127">Edited messages</span></span> | <span data-ttu-id="c4954-128">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-128">Yes</span></span> | <span data-ttu-id="c4954-129">ユーザーが保留されている場合、編集済みメッセージの以前のバージョンが保持されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-129">If the user is on hold, previous versions of edited messages are preserved.</span></span> |
| <span data-ttu-id="c4954-130">絵文字、GIF、ステッカー</span><span class="sxs-lookup"><span data-stu-id="c4954-130">Emojis, GIFs, stickers</span></span> | <span data-ttu-id="c4954-131">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-131">Yes</span></span> | |
| <span data-ttu-id="c4954-132">コード スニペット</span><span class="sxs-lookup"><span data-stu-id="c4954-132">Code snippets</span></span> | <span data-ttu-id="c4954-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4954-133">No</span></span> | |
| <span data-ttu-id="c4954-134">チャット リンク</span><span class="sxs-lookup"><span data-stu-id="c4954-134">Chat links</span></span> | <span data-ttu-id="c4954-135">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-135">Yes</span></span> | |
| <span data-ttu-id="c4954-136">リアクション (いいね、ハートなど)</span><span class="sxs-lookup"><span data-stu-id="c4954-136">Reactions (likes, hearts, and so on)</span></span> | <span data-ttu-id="c4954-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4954-137">No</span></span> | |
| <span data-ttu-id="c4954-138">インライン画像</span><span class="sxs-lookup"><span data-stu-id="c4954-138">Inline images</span></span> | <span data-ttu-id="c4954-139">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-139">Yes</span></span> | |
| <span data-ttu-id="c4954-140">テーブル</span><span class="sxs-lookup"><span data-stu-id="c4954-140">Tables</span></span> | <span data-ttu-id="c4954-141">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-141">Yes</span></span> | |
| <span data-ttu-id="c4954-142">件名</span><span class="sxs-lookup"><span data-stu-id="c4954-142">Subject</span></span> | <span data-ttu-id="c4954-143">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-143">Yes</span></span> | |
| <span data-ttu-id="c4954-144">見分け</span><span class="sxs-lookup"><span data-stu-id="c4954-144">Quotes</span></span> | <span data-ttu-id="c4954-145">はい</span><span class="sxs-lookup"><span data-stu-id="c4954-145">Yes</span></span> | <span data-ttu-id="c4954-146">クォータコンテンツは検索できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-146">Quoted content is searchable.</span></span> <span data-ttu-id="c4954-147">ただし、検索結果は、コンテンツが引用でクォートされたことを示すものでなく、検索結果には含めません。</span><span class="sxs-lookup"><span data-stu-id="c4954-147">However, search results don't indicate that the content was quoted.</span></span> |
| <span data-ttu-id="c4954-148">オーディオ録音</span><span class="sxs-lookup"><span data-stu-id="c4954-148">Audio recordings</span></span> | <span data-ttu-id="c4954-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="c4954-149">No</span></span> | |

<span data-ttu-id="c4954-150"><sup>1</sup> 会議メタデータには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4954-150"><sup>1</sup> Meeting metadata includes the following:</span></span>

- <span data-ttu-id="c4954-151">会議または通話の開始時刻と終了時刻、期間</span><span class="sxs-lookup"><span data-stu-id="c4954-151">Meeting or call start and end time, and duration</span></span>
- <span data-ttu-id="c4954-152">各参加者の通話/会議の参加、イベントへの参加、およびイベントからの参加、およびイベントの出席を行う</span><span class="sxs-lookup"><span data-stu-id="c4954-152">Call/Meeting join and leave events for each participant</span></span>
- <span data-ttu-id="c4954-153">VOIP 参加/通話</span><span class="sxs-lookup"><span data-stu-id="c4954-153">VOIP join/calls</span></span>
- <span data-ttu-id="c4954-154">Anonymous Join (Anonymous Join)</span><span class="sxs-lookup"><span data-stu-id="c4954-154">Anonymous join</span></span>
- <span data-ttu-id="c4954-155">フェェレート ユーザー結合</span><span class="sxs-lookup"><span data-stu-id="c4954-155">Federated user join</span></span>
- <span data-ttu-id="c4954-156">ゲスト ユーザーの参加</span><span class="sxs-lookup"><span data-stu-id="c4954-156">Guest user join</span></span>

<span data-ttu-id="c4954-157">画像にはメタデータの例が表示されています。</span><span class="sxs-lookup"><span data-stu-id="c4954-157">The image shows an example of the metadata.</span></span>

![画像は、CVR で会議メタデータを記録します。](media/conversationOption3.png)

<span data-ttu-id="c4954-159">会議中に参加者間の IM 会話の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c4954-159">Here's an example of IM conversation between participants during the meeting.</span></span>

![画像は参加者間の会話の 1 つです。](media/MeetingIMConversations.png)

![画像は参加者間の会話の 1 つです。](media/MeetingImConversation2.png)

<span data-ttu-id="c4954-162">電子情報開示の調査を行うには、コア電子情報開示の使用を開始する手順 1 [を参照してください](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="c4954-162">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [Get started with Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).</span></span>

<span data-ttu-id="c4954-163">Excel 電子情報開示エクスポート出力では、Microsoft Teams データが IM または会話として表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-163">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output.</span></span> <span data-ttu-id="c4954-164">エクスポート後 `.pst` 、Outlook でファイルを開いてそれらのメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-164">You can open the `.pst` file in Outlook to view those messages after export.</span></span>

<span data-ttu-id="c4954-165">チームの .pst ファイルを表示すると、すべての会話は [会話履歴] の [チーム チャット] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-165">When viewing the .pst file for the team, all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="c4954-166">メッセージのタイトルには、チーム名とチャネル名が含まれている。</span><span class="sxs-lookup"><span data-stu-id="c4954-166">The title of the message contains the team name and channel name.</span></span> <span data-ttu-id="c4954-167">たとえば、次の図は、製造スピーカー チームの Project 7 標準チャネルにメッセージをした Bob からのメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4954-167">For example, the image below shows a message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

![Outlook でユーザーのメールボックスの [チーム チャット] フォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

<span data-ttu-id="c4954-169">ユーザーのメールボックスのプライベート チャットは、[会話履歴] の [チーム チャット] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-169">Private chats in a user's mailbox are stored in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="c4954-170">プライベート チャネルの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="c4954-170">eDiscovery of private channels</span></span>

<span data-ttu-id="c4954-171">プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-171">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="c4954-172">レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="c4954-172">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="c4954-173">各プライベート チャネルには、親チーム サイトとは別に独自の SharePoint サイト コレクションがあるため、プライベート チャネル内のファイルは親チームとは別に管理されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-173">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="c4954-174">Teams では、チーム内の 1 つのチャネルの電子情報開示検索をサポートしていないため、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4954-174">Teams doesn't support eDiscovery search of a single channel within a team, so the whole team must be searched.</span></span> <span data-ttu-id="c4954-175">プライベート チャネルでコンテンツの電子情報開示検索を実行するには、チーム内で検索し、プライベート チャネルに関連付けられたサイト コレクション (ファイルを含めるため)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。</span><span class="sxs-lookup"><span data-stu-id="c4954-175">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="c4954-176">電子情報開示の検索に含めるプライベート チャネル内のファイルやメッセージを識別するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4954-176">Use the following steps to identify files and messages in a private channel to include in your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="c4954-177">電子情報開示検索にプライベート チャネル ファイルを含める</span><span class="sxs-lookup"><span data-stu-id="c4954-177">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="c4954-178">次の手順を実行する前に [、SharePoint Online Management Shell をインストールして、SharePoint Online に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="c4954-178">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="c4954-179">次を実行して、チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c4954-179">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="c4954-180">次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルと親チーム グループ ID に関連付けられているすべての SharePoint サイト コレクションの URI の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c4954-180">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. <span data-ttu-id="c4954-181">チームまたはグループ ID について、次の PowerShell スクリプトを実行して、すべてのプライベート チャネル サイト ($groupID がチームのグループ ID です) を特定します。</span><span class="sxs-lookup"><span data-stu-id="c4954-181">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="c4954-182">電子情報開示検索にプライベート チャネル メッセージを含める</span><span class="sxs-lookup"><span data-stu-id="c4954-182">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="c4954-183">これらの手順を実行する前に、最新バージョンの Teams PowerShell モジュールが [インストールされていることを確認](teams-powershell-overview.md) します。</span><span class="sxs-lookup"><span data-stu-id="c4954-183">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="c4954-184">次を実行して、チームのプライベート チャネルのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="c4954-184">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="c4954-185">プライベート チャネル メンバーのリストを取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4954-185">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="c4954-186">電子情報開示検索クエリの一部として、チーム内の各プライベート チャネルからのすべてのメンバーのメールボックスを含めます。</span><span class="sxs-lookup"><span data-stu-id="c4954-186">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="advanced-ediscovery"></a><span data-ttu-id="c4954-187">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c4954-187">Advanced eDiscovery</span></span>

<span data-ttu-id="c4954-188">一部の Microsoft Teams コンテンツは [、Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)ワークフローを使用して検索および保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-188">Some Microsoft Teams content can also be searched and preserved using the [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span> <span data-ttu-id="c4954-189">電子情報開示では、検索、保留、およびエクスポートの機能が提供されますが、Advanced eDiscovery では、データ ソースを識別し、コンテンツを分析するためのよりコンプライアンス管理者が提供します。</span><span class="sxs-lookup"><span data-stu-id="c4954-189">While eDiscovery provides a range of search, hold, and export functionality, advanced eDiscovery gives compliance administrators more tools to identify data sources and analyze their contents.</span></span>

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a><span data-ttu-id="c4954-190">Teams コンテンツの高度な電子情報開示のカストディアン ワークフロー</span><span class="sxs-lookup"><span data-stu-id="c4954-190">Advanced eDiscovery custodian workflow for Teams content</span></span>

<span data-ttu-id="c4954-191">カストディアンは、さまざまなチームのメンバーになりすます。</span><span class="sxs-lookup"><span data-stu-id="c4954-191">Custodians might be a member of various teams.</span></span> <span data-ttu-id="c4954-192">これらのカストディアンに関する Teams のコンテンツをキャプチャすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-192">You can capture Teams content that is relevant to these custodians.</span></span> <span data-ttu-id="c4954-193">カストディアン ワークフローの背景と手順については [、Advanced eDiscovery ワークフローを参照してください](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="c4954-193">For background and instructions on the custodian workflow, see [Advanced eDiscovery workflow](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).</span></span>

<span data-ttu-id="c4954-194">カストディアンを追加したら、[次へ] ボ **タン、[追加** ] ボタンの順に **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="c4954-194">After adding a custodian, click the **Next** button, then the **Add** button.</span></span> <span data-ttu-id="c4954-195">次に、追加の場所を選択するように求めるウィンドウが表示され、カストディアンのメンバーシップと、それらのデータに対応する SharePoint サイトの場所がすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-195">A window then displays that prompts you to select additional locations, which will show you all of the custodian's memberships and the corresponding SharePoint site locations for their data.</span></span> <span data-ttu-id="c4954-196">これらのすべてのデータ ソースとチームから、電子情報開示に使用するコンテンツを選択し、そのユーザーと、保留にしたすべてのデータ ソースを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-196">From all of these data sources and teams, you can choose the content you want to use for eDiscovery, then place that user and all the data sources that you've identified on hold.</span></span>

<span data-ttu-id="c4954-197">Exchange コンテンツ、OneDrive コンテンツ、またはその両方を含めるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-197">You can select whether to include their Exchange content, their OneDrive content, or both.</span></span> <span data-ttu-id="c4954-198">Exchange コンテンツには、ユーザーのメールボックスに含まれるすべてのアプリケーション コンテンツ (メール、メールボックスに保存されている Teams コンテンツなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4954-198">Exchange content includes all of the application content in the user's mailboxes, such as their email, the Teams content that is stored in their mailbox, and so on.</span></span> <span data-ttu-id="c4954-199">OneDrive コンテンツにはユーザーのコンテンツだけでなく、1 対 1 のチャット、1:N チャット、チャットで共有されているファイルなど、OneDrive に保存されているすべての Teams コンテンツが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4954-199">The OneDrive content includes not only the user's content, but also all of the Teams content that is stored in OneDrive, such as 1:1 chats, 1:N chats, and files shared in chats.</span></span>

<span data-ttu-id="c4954-200">また、チームにカストディアンを関連付けるオプションを使用して、チャネル チャット メッセージとカストディアンにアクセス権を持つファイルが含まれるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-200">You also have the option to associate any team the custodian is a member of so that channel chat messages and files the custodian has access to are included.</span></span> <span data-ttu-id="c4954-201">さらに、他のチームをカストディアンに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-201">Additionally, any other team can be associated with a custodian.</span></span> <span data-ttu-id="c4954-202">詳細については、「 [アドバンスト電子情報開示ケースにカストディアンを追加する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)。</span><span class="sxs-lookup"><span data-stu-id="c4954-202">For more information, see [Add custodians to an Advanced eDiscovery case](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).</span></span>

> [!NOTE]
> <span data-ttu-id="c4954-203">プライベート チャネル内のメッセージや [ファイル](private-channels.md) の電子情報開示は、標準チャネルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c4954-203">eDiscovery of messages and files in [private channels](private-channels.md) works differently than in standard channels.</span></span> <span data-ttu-id="c4954-204">詳細については、プライ [ベート チャネルの電子情報開示を参照してください](#ediscovery-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="c4954-204">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

### <a name="placing-a-data-source-on-hold"></a><span data-ttu-id="c4954-205">データ ソースを保留にする</span><span class="sxs-lookup"><span data-stu-id="c4954-205">Placing a data source on hold</span></span>

<span data-ttu-id="c4954-206">カストディアンとして指定する特定のユーザーがない場合は、データ ソース全体を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-206">If there is no specific user to designate as a custodian, you can place an entire data source on hold.</span></span> <span data-ttu-id="c4954-207">保留の詳細については [、Advanced eDiscovery で保留を管理する方法に関するページを参照してください](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。</span><span class="sxs-lookup"><span data-stu-id="c4954-207">For more information on holds, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

<span data-ttu-id="c4954-208">Teams コンテンツの保留リストを作成するときに、保留に含めるすべての場所を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-208">When creating a hold for Teams content, you can choose all of the locations you wish to include in your hold.</span></span> <span data-ttu-id="c4954-209">ユーザーがコンテンツを削除または変更していても、保留にはそのコンテンツの以前のすべてのバージョンのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-209">Even if users are deleting or changing content, the hold will maintain copies of all previous versions of that content.</span></span>

<span data-ttu-id="c4954-210">また、追加のクエリを使用して、キーワード、日付範囲、作成者、その他の多くの条件に基づいて保留リストの条件を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-210">You can also use an optional query to set conditions for the hold based on keywords, date range, author, and many other criteria.</span></span> <span data-ttu-id="c4954-211">キーワードを指定しない場合、そのデータ ソースのすべての内容が保留にされます。</span><span class="sxs-lookup"><span data-stu-id="c4954-211">If you specify no keywords, then everything from that data source will be subject to the hold.</span></span>

### <a name="advanced-ediscovery-searches"></a><span data-ttu-id="c4954-212">Advanced eDiscovery の検索</span><span class="sxs-lookup"><span data-stu-id="c4954-212">Advanced eDiscovery searches</span></span>

<span data-ttu-id="c4954-213">Teams のコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-213">Teams content can also be searched.</span></span> <span data-ttu-id="c4954-214">検索の詳細については [、Advanced eDiscovery でケースのデータを収集する方法を参照してください](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="c4954-214">For more information on searches, see [Collect data for a case in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery).</span></span> <span data-ttu-id="c4954-215">検索は、1 つのメッセージが検索クエリと一致する場合、スレッド全体を返します。</span><span class="sxs-lookup"><span data-stu-id="c4954-215">A search will return an entire conversation if even one message matches the search query.</span></span>

<span data-ttu-id="c4954-216">検索クエリを作成するときに、選ぶすべてのソースが検索されるように、カストディアンを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-216">When creating a search query, you can choose custodians so that all the sources that you've already selected will be searched.</span></span> <span data-ttu-id="c4954-217">ユーザーにマップされていない Teams サイトなどのカストラダフト以外のソースを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-217">You can also search non-custodial sources such as a Teams site that is not mapped to a user.</span></span> <span data-ttu-id="c4954-218">オプションのクエリを使用して、Teams コンテンツ内で検索を絞り込むことも可能です。</span><span class="sxs-lookup"><span data-stu-id="c4954-218">Optional queries are also available to narrow your search within the Teams content.</span></span>

<span data-ttu-id="c4954-219">検索を作成して選択すると、選択した検索で実行できる追加の詳細とアクションを含むウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-219">After you've created a search and selected it, a window displays with additional details and actions that you can take on the selected search.</span></span> <span data-ttu-id="c4954-220">[ **統** 計情報] ボタンをクリックすると、場所の種類、コンテンツの元のソース、コンテンツの元のソース、コンテンツがグループ メールボックス、個別のユーザー メールボックス、SharePoint サイトにあるかどうかに基数の内部にあるかどうかに基って、検索に関する統計情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-220">If you click the **Statistics** button, you can view statistics about your search, including breakdowns according to location types, the original source for the content, and whether the content is located in a group mailbox, the individual user mailbox, or a SharePoint site.</span></span> <span data-ttu-id="c4954-221">したがって、検索結果に投稿しているソースの内部を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-221">Thus, you can see a breakdown of what sources are contributing to your search results.</span></span> <span data-ttu-id="c4954-222">また、クエリ **ビューも** 利用できるため、どの個々のキーワードが結果に投稿されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-222">There is also a **Queries** view available so you can see which individual keywords are contributing to your results.</span></span>

<span data-ttu-id="c4954-223">検索を最後に、検索を確認するボタンを **クリックしてレ** ビュー セット ボタンに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-223">After you finalize your search, you can click the **Add results to review set** button and add it to a review set.</span></span> <span data-ttu-id="c4954-224">レビュー セットの詳細については、この記事の後半の [「Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) および [レビュー](#review-sets-workflow) セット」のワークフローでレビュー セットを管理する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4954-224">For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) and [Review Sets workflow](#review-sets-workflow) later in this article.</span></span>

#### <a name="normal-review-sets-and-conversation-review-sets"></a><span data-ttu-id="c4954-225">通常のレビュー セットと会話レビュー セット</span><span class="sxs-lookup"><span data-stu-id="c4954-225">Normal review sets and conversation review sets</span></span>

<span data-ttu-id="c4954-226">レビュー セットに検索を追加する場合、通常のレビュー セットまたはスレッド レビュー セットから選択できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-226">When adding a search to a review set, you can choose from a normal review set or a conversation review set.</span></span>

<span data-ttu-id="c4954-227">通常のレビュー セットはエクスポートにおいています。Teams コンテンツ用の個々のファイル `.msg` を提供し、基本ビューでコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-227">A normal review set is similar to an export; it provides the individual `.msg` files for the Teams content and presents the content in a basic view.</span></span> <span data-ttu-id="c4954-228">他のソフトウェア ツールを使用して後でファイルを再処理する予定の場合、通常は、通常確認セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4954-228">You would typically use a normal review set when you plan to use other software tools to reprocess the files later.</span></span>

<span data-ttu-id="c4954-229">会話のレビュー セットでは、よりシード、会話のスレッド ビューが提供されます。関連するメッセージが適切な順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-229">A conversation review set provides a more intuitive, threaded view of the conversations; it displays related messages together in the proper order.</span></span>

![会話レビュー セットのスクリーンショット](media/conversationOptions2.png)

<span data-ttu-id="c4954-231">再アクションなどの機能はどちらの種類のレビュー セットで利用できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-231">Functionality such as redaction is available in both types of review sets.</span></span> <span data-ttu-id="c4954-232">レビュー セットの詳細については、Advanced [eDiscovery での会話の確認を参照してください](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="c4954-232">For more information about review sets, see [Review conversations in advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).</span></span>

#### <a name="collection-options"></a><span data-ttu-id="c4954-233">コレクションのオプション</span><span class="sxs-lookup"><span data-stu-id="c4954-233">Collection options</span></span>

<span data-ttu-id="c4954-234">レビュー セットに追加するときに、ウィンドウの [コレクションのオプション] セクションの下**Collection Options**に、会話の制限オプションや**Conversation Retrieval Options**Teams 会話など、チェックボックスとして**利用できるオプションがいくつかあります**。</span><span class="sxs-lookup"><span data-stu-id="c4954-234">When adding to a review set, there are several options available as checkboxes under the **Collection Options** section of the window, including **Conversation Retrieval Options** and **Teams Conversations**.</span></span> <span data-ttu-id="c4954-235">これらのオプションを有効にすると、レビュー セットの一部になっている Teams メッセージにも、コンテキストのためにその他のメッセージとともに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-235">If you enable these options, any individual Teams messages that are part of your review set will also be shown with additional messages surrounding them for context.</span></span> <span data-ttu-id="c4954-236">たとえば、クエリが非常に固有で、結果として返されるメッセージが 1 つだけである場合、これらのオプションを有効にすると、クエリに一致したメッセージをたどり、次のメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-236">For example, if your query is very specific and only one message is returned as a result, enabling these options will also return several messages leading up to and following the message that matched your query.</span></span>

<span data-ttu-id="c4954-237">多くの論理的基基基基となり、クエリに一致するメッセージに対して追加のメッセージでコンテキストを提供するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c4954-237">Many logical criteria are used to determine whether additional messages provide context to messages that match your query.</span></span> <span data-ttu-id="c4954-238">たとえば、Teams コンテンツの場合、これらのオプションを有効にすると、メッセージのスレッド化の方法から、親メッセージと子メッセージをすべて取得できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-238">For example, for Teams content, enabling these options will retrieve the parent message and all the child messages because of the way the messages are threaded.</span></span>

<span data-ttu-id="c4954-239">メッセージタイム スタンプもチェックされます。</span><span class="sxs-lookup"><span data-stu-id="c4954-239">Message time stamps are also checked.</span></span> <span data-ttu-id="c4954-240">メッセージがクエリと一致する場合、4 時間前に続くメッセージ、または 4 時間の範囲内に続くメッセージがスレッドの一部と見なされ、結果にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4954-240">If a message matches your query, neighboring messages that precede it within a span of 4 hours or that follow it within a span of 4 hours are considered to be part of the conversation and are also included in the results.</span></span>

<span data-ttu-id="c4954-241">検索クエリと一致するコンテキスト メッセージが返されることを特定する必要がある場合は、これらのオプションを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c4954-241">If you must be certain about which contextual messages will be returned with matches to your search query, you do not need to use these options.</span></span> <span data-ttu-id="c4954-242">すべてのコンテンツを収集することも、より多くのメッセージがクエリの結果として返されるように、検索の日付範囲を広くすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-242">You can either collect all content, or you can widen the date range of your search so that more messages are returned as a result of your query.</span></span>

### <a name="review-sets-workflow"></a><span data-ttu-id="c4954-243">レビュー セット ワークフロー</span><span class="sxs-lookup"><span data-stu-id="c4954-243">Review sets workflow</span></span>

<span data-ttu-id="c4954-244">[レビュー セット] タブをクリックすると、既存のレビュー セットを表示したり、新 **しいレビュー セットを作成** したりすることができます。レビュー セットの詳細については [、Advanced eDiscovery でレビュー セットを管理する方法について説明します](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)。</span><span class="sxs-lookup"><span data-stu-id="c4954-244">You can view existing review sets or create new ones by clicking the **Review Sets** tab. For more information about review sets, see [Manage review sets in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).</span></span>

<span data-ttu-id="c4954-245">ドキュメントにも、メール、Teams メッセージ、Yammer メッセージ、その他のコンテンツをレビュー セットに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-245">In addition to documents, you can add emails, Teams messages, Yammer messages, and other content to your review set.</span></span> <span data-ttu-id="c4954-246">レビュー セット内で、コンテンツの検索やカスタム クエリの作成など、他のコンテキストで実行できる操作の多くを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-246">Within a review set, you can also perform many of the same operations that you can perform in other contexts, such as searching content and creating custom queries.</span></span> <span data-ttu-id="c4954-247">これらの操作は、レビュー セットに追加されたアイテムにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-247">These operations only apply to items that have been added to the review set.</span></span>

<span data-ttu-id="c4954-248">[ **レビュー セットの管理** ] ボタンには、分析、サマリー レポート、追加されたロード セットの数など、その他のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c4954-248">The **Manage Review Sets** button provides additional options such as analytics, summary reporting, how many load sets have been added, and so on.</span></span>

<span data-ttu-id="c4954-249">視覚エフェクトやグラフにアクセスするには、右上にある**個**々の検索プロファイル \> **Search profile view**ビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4954-249">To access visualizations and charts of your data, click **Individual results** \> **Search profile view** in the upper right.</span></span> <span data-ttu-id="c4954-250">これらのグラフ内のウェェイをクリックすると、クエリを実行するコンテンツの種類を対話的に選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-250">You can click on wedges in these charts to interactively select the type of content you want to query.</span></span> <span data-ttu-id="c4954-251">たとえば、Teams のコンテンツのみをクエリすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-251">For example, you can choose to query only Teams content.</span></span> <span data-ttu-id="c4954-252">手動で作成したクエリを保存する場合と同様に、これらのクエリを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-252">You can also save these queries just as you would save queries that you write manually.</span></span>

#### <a name="summary-view-text-view-and-annotate-view"></a><span data-ttu-id="c4954-253">概要ビュー、テキスト ビュー、およびそのビュー</span><span class="sxs-lookup"><span data-stu-id="c4954-253">Summary view, text view, and annotate view</span></span>

<span data-ttu-id="c4954-254">レビュー セットで Teams の会話をクリックすると、概要ビュー**Summary view**が表示され、個別にやり取りできるメッセージの一覧として Teams の会話全体が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-254">If you click on a Teams conversation in the review set, it displays the **Summary view**, which displays an entire Teams conversation as a list of messages that you can interact with individually.</span></span> <span data-ttu-id="c4954-255">メッセージの右にある下向き矢印をクリックしてコンテキスト メニューを表示し、メッセージの詳細を表示したり個々のファイルをダウンロードしたり `.msg` できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-255">Click the downward arrow to the right of a message to display a context menu that allows you to view message details or download the individual `.msg` file.</span></span> <span data-ttu-id="c4954-256">メッセージの詳細をクリックすると、メタデータの概要またはメッセージの完全なメタデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-256">Clicking message details will show you a summary of metadata or the full metadata of the message.</span></span>

<span data-ttu-id="c4954-257">PDF をダウンロードするには、概要ビューの右上にあるダウンロード ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4954-257">To download a PDF, click the download button at the upper right of the summary view.</span></span>

<span data-ttu-id="c4954-258">[テキスト **ビュー]** タブをクリックして、Teams の会話のテキスト形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="c4954-258">Click the **Text view** tab to display a plain text view of the extracted text of the Teams conversation.</span></span> <span data-ttu-id="c4954-259">このプレーン テキストの内容はエクスポートにも当てはまるため、他のソフトウェア ツールを使うと簡単に操作できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-259">This plain text content is suitable for export and you can easily work with it using other software tools.</span></span>

<span data-ttu-id="c4954-260">[表示] **タブをクリック** して、その機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c4954-260">Click on the **Annotate view** tab to access annotation features.</span></span> <span data-ttu-id="c4954-261">このタブには、Teams の会話に近い形式でコンテンツが表示されますが、編集オプションもあります。</span><span class="sxs-lookup"><span data-stu-id="c4954-261">This tab displays the content in a format that resembles a Teams conversation, but there are also additional options for editing.</span></span> <span data-ttu-id="c4954-262">メモの作成、メッセージへの描画、再ディクションの目的で最もきれいなスクラッチを行うために使用できる、ペンシル ツールがあります。</span><span class="sxs-lookup"><span data-stu-id="c4954-262">There is a pencil tool that you can use to make notes, draw on the message, or do fine-grained scratching out for redaction purposes.</span></span> <span data-ttu-id="c4954-263">また、 **領域を囲** み、"レドパクト" とマークする四角形を描画する領域の四角形を描画する領域のリクエストルも用いたします。</span><span class="sxs-lookup"><span data-stu-id="c4954-263">There is also an **Area redaction** tool that you can use to draw a rectangle that blacks out the area and marks it as "Redacted".</span></span>

<span data-ttu-id="c4954-264">以下は、ユーザー間のスレッド化のためのレド化されたファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="c4954-264">Here's an example of a redacted file for threaded conversation between users.</span></span>

![レイド ファイルのスクリーンショット](media/RedactedFileExample.png)

<span data-ttu-id="c4954-266">[表示] タブの**下部には**、[タグ付**Tag documents**け] ボタンが表示され、この [タグ付け] パネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4954-266">At the bottom of the **Annotate view** tab is the **Tag documents** button, which displays the tagging panel.</span></span> <span data-ttu-id="c4954-267">このパネル内で、Teams の会話内のすべてのメッセージにタグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-267">Within this panel, you can apply a tag to all messages within the Teams conversation.</span></span> <span data-ttu-id="c4954-268">スレッドは応答性の高いか、応答性がないか、アクセス可能でないか、"関知的なアイテム" のどこに含まれているか、エクスポートに含めるべきかどうか、さらにレビューが必要かどうかにかかわらず、スレッドにラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-268">You can label a conversation as responsive or non-responsive, privileged or not privileged, whether it contains "Interesting items", whether it should be included in export, and whether it needs further review.</span></span> <span data-ttu-id="c4954-269">他のカスタマイズ可能なタグを管理および適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-269">You can also manage and apply other customizable tags.</span></span>

#### <a name="action-menu"></a><span data-ttu-id="c4954-270">[操作] メニュー</span><span class="sxs-lookup"><span data-stu-id="c4954-270">Action menu</span></span>

<span data-ttu-id="c4954-271">レビュー セット ウィンドウ内で、[アクション エクスポート] をクリックしてコンテンツ **を** \> **エクスポートできます**。</span><span class="sxs-lookup"><span data-stu-id="c4954-271">Within the review sets window, you can export the content by clicking **Action** \> **Export**.</span></span> <span data-ttu-id="c4954-272">エクスポート時に利用できるオプションは数多くあります。</span><span class="sxs-lookup"><span data-stu-id="c4954-272">There are many options available when exporting.</span></span>

<span data-ttu-id="c4954-273">すべての Teams メッセージのすべてのメタデータを含むファイルをエクスポートするには、[ファイルの読み込み] **チェック ボックスをオンに** します。</span><span class="sxs-lookup"><span data-stu-id="c4954-273">To export a file that contains all the metadata for all Teams messages, click to select the **Load file** checkbox.</span></span> <span data-ttu-id="c4954-274">ファイルにコンテンツに適用したノート シールを含めるには、[ノート シール] チェック ボックス **をクリックして選択** します。</span><span class="sxs-lookup"><span data-stu-id="c4954-274">To include in your file any tags that you have applied to the content, click to select the **Tags** checkbox.</span></span>

<span data-ttu-id="c4954-275">ネイ **ティブ ファイルオプションを使用して** 、ファイルをネイティブ形式でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="c4954-275">Use the **Native files** option to export files in their native format.</span></span> <span data-ttu-id="c4954-276">会話を 1 つのファイルとしてエクスポートすることも、個別の個別のファイルにすべてのチャット メッセージをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c4954-276">You can choose to export a conversation as one file or all individual chat messages in their own separate files.</span></span>

<span data-ttu-id="c4954-277">テキスト **ファイル オプション** では、テキスト形式のコンテンツを保存できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-277">The **Text files** option allows you to save plain text versions of content.</span></span> <span data-ttu-id="c4954-278">レビュー セット内の Teams の会話のプレーン テキスト ビューを入れる方法の詳細については、上の概要ビュー、テキスト ビュー、注注を [参照](#summary-view-text-view-and-annotate-view) してください。</span><span class="sxs-lookup"><span data-stu-id="c4954-278">For more information about how to obtain a plain text view of Teams conversations in the review set, see [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) above.</span></span>

<span data-ttu-id="c4954-279">上記の概要ビュー、テキスト ビュー、注目表示セクションで説明されているようにコンテンツに再ダッシュボードを適用 [した](#summary-view-text-view-and-annotate-view) 場合は、置換後のネイティブ **を [保存する PDF]** オプションで選び、変換された PDF でネイティブ ファイルを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="c4954-279">If you applied any redactions to the content as described in the [Summary view, text view, and annotate view](#summary-view-text-view-and-annotate-view) section above, you can select the **Replace redacted natives with converted PDFs** option to replace the native files with converted copies in PDF.</span></span>

<span data-ttu-id="c4954-280">Microsoft が提供する Azure BLOB ストレージ コンテナーにエクスポートするか、独自の Azure BLOB ストレージ コンテナーを提供するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c4954-280">You can choose to export to a Microsoft-provided Azure blob storage container or you can provide your own Azure Blob storage container.</span></span>

<span data-ttu-id="c4954-281">エクスポート プロセスを開始する準備ができたら、[エクスポート] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="c4954-281">When you are ready to begin the export process, click the **Export** button.</span></span> <span data-ttu-id="c4954-282">Azure [BLOB ストレージ](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) コンテナーにアクセスし、エクスポートが完了したらエクスポートされたコンテンツをダウンロードする方法の詳細については、「エクスポート ジョブをダウンロードする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4954-282">See [Download export jobs](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) for more information about how you can access the Azure blob storage container and download your exported content after export is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="c4954-283">エクスポートには、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4954-283">Exporting can take an extended period of time.</span></span> <span data-ttu-id="c4954-284">エクスポート プロセスの状態を追跡するには、[校閲セット] タブ **を終了し** 、[エクスポート] タブ **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="c4954-284">To track the status of the export process, exit the **Review sets** tab and click the **Exports** tab.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c4954-285">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4954-285">Related topics</span></span>

- [<span data-ttu-id="c4954-286">Microsoft 365 の電子情報開示</span><span class="sxs-lookup"><span data-stu-id="c4954-286">eDiscovery in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [<span data-ttu-id="c4954-287">Teams PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="c4954-287">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
