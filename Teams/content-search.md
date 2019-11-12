---
title: Microsoft Teams のコンテンツ検索を使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: Microsoft Teams のコンテンツ検索について説明し、Exchange からのチャネル会話の検索方法、SharePoint からのファイルのアップロードと変更、OneNote の変更について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3042a39d30ca14ff4eda9be6a1042bfca3484bd2
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231158"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="c73c4-103">Microsoft Teams のコンテンツ検索を使用する</span><span class="sxs-lookup"><span data-stu-id="c73c4-103">Use Content Search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="c73c4-104">[プライベートチャネル](private-channels.md)でのメッセージやファイルのコンテンツ検索の動作は、標準チャネルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c73c4-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="c73c4-105">詳細については、「[プライベートチャネルのコンテンツ検索](#content-search-of-private-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73c4-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="c73c4-106">コンテンツ検索を使用すると、Exchange、SharePoint Online、OneDrive for Business にわたる Microsoft Teams の情報を照会することができます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-106">Content Search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="c73c4-107">詳細については、「 [Office 365 でコンテンツ検索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)を読む」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c73c4-107">To learn more, read [Content Search in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span></span>

<span data-ttu-id="c73c4-108">たとえば、製造仕様のメールボックスと製造仕様の SharePoint サイトに対して**コンテンツ検索**を使用すると、Exchange からの Teams 標準チャネルの会話、sharepoint Online からのファイルのアップロードと変更、OneNote の変更を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-108">For example, using **Content Search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="c73c4-109">**コンテンツ検索**にクエリ条件を追加して、返される結果を絞り込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="c73c4-110">上の例では、"**新しいファクトリの仕様"** というキーワードが使用されているコンテンツを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-110">In the above example, you can look for content where the keywords “**New Factory Specs”** were used.</span></span>

> [!TIP]
> <span data-ttu-id="c73c4-111">検索条件を追加した後は、レポートまたはデータをコンピューターにエクスポートして分析することができます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-111">After adding search conditions, you can export a report or the data to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="c73c4-112">プライベートチャネルのコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="c73c4-112">Content search of private channels</span></span>

<span data-ttu-id="c73c4-113">プライベートチャネルで送信されたメッセージのレコードは、グループメールボックスではなく、すべてのプライベートチャネルメンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="c73c4-114">レコードのタイトルは、送信元のプライベートチャネルを示すように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="c73c4-115">各プライベートチャネルには、親チームサイトとは別の SharePoint サイトコレクションがあるため、プライベートチャネルのファイルは親チームとは独立して管理されます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="c73c4-116">チームは1つのチャネルのコンテンツ検索をサポートしていないため、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c73c4-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="c73c4-117">プライベートチャネルのコンテンツ検索を実行するには、チーム、プライベートチャネルに関連付けられたサイトコレクション (ファイルを含む)、プライベートチャネルメンバーのメールボックス (メッセージを含む) を検索します。</span><span class="sxs-lookup"><span data-stu-id="c73c4-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="c73c4-118">次の手順を使用して、コンテンツ検索に含めるファイルとプライベートチャネル内のメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="c73c4-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="c73c4-119">コンテンツ検索にプライベートチャネルファイルを含める</span><span class="sxs-lookup"><span data-stu-id="c73c4-119">Include private channel files in a content search</span></span>

<span data-ttu-id="c73c4-120">これらの手順を実行する前に、 [Sharepoint Online 管理シェルをインストールして、Sharepoint online に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)します。</span><span class="sxs-lookup"><span data-stu-id="c73c4-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="c73c4-121">チーム内のプライベートチャネルに関連付けられているすべての SharePoint サイトコレクションの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c73c4-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```
    Get-SPOSite
    ```
2. <span data-ttu-id="c73c4-122">次の PowerShell スクリプトを実行して、チーム内のプライベートチャネルと親チームグループ ID に関連付けられたすべての SharePoint サイトコレクション Url の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c73c4-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="c73c4-123">各チームまたはグループ ID について、次の PowerShell スクリプトを実行して、関連するすべてのプライベートチャネルサイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="c73c4-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="c73c4-124">コンテンツ検索にプライベートチャネルメッセージを含める</span><span class="sxs-lookup"><span data-stu-id="c73c4-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="c73c4-125">これらの手順を実行する前に、[最新バージョンの Teams PowerShell モジュール](teams-powershell-overview.md)がインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c73c4-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="c73c4-126">チーム内のプライベートチャネルの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c73c4-126">Run the following to get a list of private channels in the team.</span></span>

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="c73c4-127">プライベートチャネルメンバーの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c73c4-127">Run the following to get a list of private channel members.</span></span>

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="c73c4-128">コンテンツ検索クエリの一部として、チーム内の各プライベートチャネルからすべてのメンバーのメールボックスを含めます。</span><span class="sxs-lookup"><span data-stu-id="c73c4-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c73c4-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c73c4-129">Related topics</span></span>

- [<span data-ttu-id="c73c4-130">Office 365 セキュリティ & コンプライアンスセンターの電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="c73c4-130">eDiscovery cases in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 