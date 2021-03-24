---
title: Microsoft Teams のコンテンツ検索を使用する
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft 365 コンプライアンス センターでコンテンツ検索を使用して、Exchange Online、SharePoint Online、OneDrive for Business、OneNote に保存されている Microsoft Teams のコンテンツを検索する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3758f96dc4755303ce8ccf3cae4443deb2a5cd99
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094287"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="82ae4-103">Microsoft Teams でコンテンツ検索を使用する</span><span class="sxs-lookup"><span data-stu-id="82ae4-103">Use Content search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="82ae4-104">プライベート チャネルでのメッセージやファイルのコンテンツ検索は [、](private-channels.md) 標準チャネルとは異なる動作をします。</span><span class="sxs-lookup"><span data-stu-id="82ae4-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="82ae4-105">詳細については、「プライベート チャネルの [コンテンツ検索」を参照してください](#content-search-of-private-channels)。</span><span class="sxs-lookup"><span data-stu-id="82ae4-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="82ae4-106">コンテンツ検索は、Exchange、SharePoint Online、OneDrive for Business に関する Microsoft Teams の情報を照会する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="82ae4-107">詳細については [、Microsoft 365 のコンテンツ検索を参照してください](/microsoft-365/compliance/content-search)。</span><span class="sxs-lookup"><span data-stu-id="82ae4-107">To learn more, see [Content search in Microsoft 365](/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="82ae4-108">たとえば、製造仕様メールボックスと製造仕様 SharePoint サイトに対してコンテンツ検索を使用すると、Exchange からの Teams の標準チャネルの会話、SharePoint Online からのファイルのアップロードと変更、OneNote の変更を検索できます。</span><span class="sxs-lookup"><span data-stu-id="82ae4-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="82ae4-109">クエリ条件をコンテンツ検索に追加して **、** 返される結果を絞り込む方法もできます。</span><span class="sxs-lookup"><span data-stu-id="82ae4-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="82ae4-110">上記の例では、キーワード **"New Factory Specs"** が使用されたコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="82ae4-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="82ae4-111">検索条件を追加した後、レポートまたは実際のコンテンツを分析のためにコンピューターにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="82ae4-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="82ae4-112">プライベート チャネルのコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="82ae4-112">Content search of private channels</span></span>

<span data-ttu-id="82ae4-113">プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="82ae4-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="82ae4-114">レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="82ae4-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="82ae4-115">各プライベート チャネルには、親チーム サイトとは別の独自の SharePoint サイト コレクションが用意されています。プライベート チャネル内のファイルは、親チームとは独立して管理されます。</span><span class="sxs-lookup"><span data-stu-id="82ae4-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="82ae4-116">Teams は 1 つのチャネルのコンテンツ検索をサポートしないので、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82ae4-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="82ae4-117">プライベート チャネルのコンテンツ検索を実行するには、チーム、プライベート チャネルに関連付けられているサイト コレクション (ファイルを含める)、プライベート チャネル メンバーのメールボックス (メッセージを含める) を検索します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="82ae4-118">コンテンツ検索に含めるプライベート チャネル内のファイルとメッセージを識別するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="82ae4-119">コンテンツ検索にプライベート チャネル ファイルを含める</span><span class="sxs-lookup"><span data-stu-id="82ae4-119">Include private channel files in a content search</span></span>

<span data-ttu-id="82ae4-120">これらの手順を実行する前に、SharePoint Online 管理シェルをインストールし [、SharePoint Online に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="82ae4-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="82ae4-121">チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクションの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="82ae4-122">次の PowerShell スクリプトを実行して、チーム内のプライベート チャネルに関連付けられているすべての SharePoint サイト コレクション URL と親チーム グループ ID の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="82ae4-123">チームまたはグループ ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベート チャネル サイトを識別します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="82ae4-124">コンテンツ検索にプライベート チャネル メッセージを含める</span><span class="sxs-lookup"><span data-stu-id="82ae4-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="82ae4-125">これらの手順を実行する前に、最新バージョンの [Teams PowerShell モジュールがインストールされていることを確認](teams-powershell-overview.md) します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="82ae4-126">チーム内のプライベート チャネルの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="82ae4-127">プライベート チャネル メンバーの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="82ae4-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="82ae4-128">コンテンツ検索クエリの一部として、チームの各プライベート チャネルのすべてのメンバーのメールボックスを含める。</span><span class="sxs-lookup"><span data-stu-id="82ae4-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="82ae4-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="82ae4-129">Related topics</span></span>

- [<span data-ttu-id="82ae4-130">Microsoft 365 コンプライアンス センターの電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="82ae4-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](/Office365/SecurityCompliance/ediscovery-cases)