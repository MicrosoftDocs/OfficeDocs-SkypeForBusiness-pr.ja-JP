---
title: Microsoft Teams のコンテンツに対して電子情報開示の調査を行う
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: 法的な手続きのために電子的に保存された情報をすべて提出する必要がある場合など、電子情報開示を実行する必要がある場合の対処方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 315ec351450224dc8d5b98dc0d974b64573bc0ab
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033271"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="89725-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="89725-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="89725-104">大企業は、多くの場合、電子的に保存されている情報 (ESI) の申請を要求する高ペナルティ法的手続きにさらされています。</span><span class="sxs-lookup"><span data-stu-id="89725-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="89725-105">すべての Teams 1:1 またはグループチャットは、それぞれのユーザーのメールボックスにジャーナリングされ、すべての標準チャネルメッセージは、チームを表すグループメールボックスによってジャーナリングされます。</span><span class="sxs-lookup"><span data-stu-id="89725-105">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="89725-106">標準チャネルにアップロードされたファイルについては、SharePoint Online と OneDrive for business の電子情報開示機能の下に記載されています。</span><span class="sxs-lookup"><span data-stu-id="89725-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="89725-107">[プライベートチャネル](private-channels.md)のメッセージやファイルの電子情報開示は、標準チャネルでの動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="89725-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="89725-108">詳細については、「[プライベートチャネルの電子情報開示](#ediscovery-of-private-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89725-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="89725-109">現時点では、ゲストユーザが1:1 または 1: N のチャットで唯一の参加者であるシナリオでは、チャットメッセージの電子情報開示はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="89725-109">At this time, we don't support eDiscovery of chat messages in scenarios where guest users are the only participants in a 1:1 or 1:N chat.</span></span> <span data-ttu-id="89725-110">これらの種類のチャットは、*ゲスト間*のチャットとも呼ばれます。これは、ホームテナントのユーザーが含まれていないためです。</span><span class="sxs-lookup"><span data-stu-id="89725-110">These types of chats are also called *guest-to-guest* chats because they don't include home tenant users.</span></span>

1. <span data-ttu-id="89725-111">Microsoft Teams のコンテンツで電子情報開示の調査を実施するには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)リンクの手順1を確認してください。</span><span class="sxs-lookup"><span data-stu-id="89725-111">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2. <span data-ttu-id="89725-112">Microsoft Teams のデータは、Excel eDiscovery のエクスポート出力で IM または会話として表示され、Outlook で PST を開いて、エクスポート後のメッセージを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="89725-112">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can open the PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="89725-113">チームの PST を表示している場合は、すべてのスレッドが [会話履歴] の下にあるチームチャットフォルダーに保存されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="89725-113">When viewing the PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="89725-114">メッセージのタイトルは、チームとチャネルに揃えて配置されます。</span><span class="sxs-lookup"><span data-stu-id="89725-114">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="89725-115">以下の画像を確認すると、製造仕様チームのプロジェクト7標準チャネルを送信先しているボブからのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89725-115">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Outlook のユーザーのメールボックス内のチームチャットフォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. <span data-ttu-id="89725-117">ユーザーのメールボックスにプライベートなチャットを表示するには、[会話履歴] の下にあるチームチャットフォルダーにも配置します。</span><span class="sxs-lookup"><span data-stu-id="89725-117">To see private chats in a user's mailbox, they are also located in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="89725-118">プライベートチャネルの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="89725-118">eDiscovery of private channels</span></span>

<span data-ttu-id="89725-119">プライベート チャネルで送信されたメッセージのレコードは、グループのメールボックスではなく、すべてのプライベート チャネル メンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="89725-119">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="89725-120">レコードのタイトルは、送信元のプライベート チャネルが示されるように書式設定されています。</span><span class="sxs-lookup"><span data-stu-id="89725-120">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="89725-121">各プライベートチャネルには、親チームサイトとは別の SharePoint サイトコレクションがあるため、プライベートチャネルのファイルは親チームとは独立して管理されます。</span><span class="sxs-lookup"><span data-stu-id="89725-121">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="89725-122">チームは1つのチャネルの電子情報開示をサポートしていないため、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89725-122">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="89725-123">プライベートチャネルのコンテンツの電子情報開示検索を実行するには、チーム全体、プライベートチャネルに関連付けられたサイトコレクション (ファイルを含む)、プライベートチャネルメンバーのメールボックス (メッセージを含む) を検索します。</span><span class="sxs-lookup"><span data-stu-id="89725-123">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="89725-124">次の手順を使用して、プライベートチャネル内のファイルとメッセージを特定し、電子情報開示検索に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="89725-124">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="89725-125">電子情報開示検索でプライベートチャネルファイルを含める</span><span class="sxs-lookup"><span data-stu-id="89725-125">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="89725-126">これらの手順を実行する前に、 [Sharepoint Online 管理シェルをインストールして、Sharepoint online に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)します。</span><span class="sxs-lookup"><span data-stu-id="89725-126">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="89725-127">チーム内のプライベートチャネルに関連付けられているすべての SharePoint サイトコレクションの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="89725-127">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="89725-128">次の PowerShell スクリプトを実行して、チーム内のプライベートチャネルと親チームグループ ID に関連付けられたすべての SharePoint サイトコレクション Url の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="89725-128">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="89725-129">チームまたはグループの ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベートチャネルサイト ($groupID はチームのグループ ID) を特定します。</span><span class="sxs-lookup"><span data-stu-id="89725-129">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="89725-130">電子情報開示検索でプライベートチャネルメッセージを含める</span><span class="sxs-lookup"><span data-stu-id="89725-130">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="89725-131">これらの手順を実行する前に、[最新バージョンの Teams PowerShell モジュール](teams-powershell-overview.md)がインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="89725-131">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="89725-132">チーム内のプライベートチャネルの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="89725-132">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="89725-133">プライベートチャネルメンバーの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="89725-133">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="89725-134">電子情報開示検索クエリの一部として、チーム内の各プライベートチャネルからすべてのメンバーのメールボックスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="89725-134">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="89725-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="89725-135">Related topics</span></span>

- [<span data-ttu-id="89725-136">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="89725-136">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
