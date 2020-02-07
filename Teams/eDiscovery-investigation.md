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
description: 訴訟手続きのためにすべての電子保持情報を提出する必要がある場合など、電子情報開示を実施するために必要な手続きについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: d85bef224966d15a6c383163d9ac4a5dd5ed126c
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833797"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="a7075-103">Microsoft Teams のコンテンツに対して電子情報開示の調査を行う</span><span class="sxs-lookup"><span data-stu-id="a7075-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="a7075-104">大企業は、多くの場合、電子的に保存されている情報 (ESI) の申請を要求する高ペナルティ法的手続きにさらされています。</span><span class="sxs-lookup"><span data-stu-id="a7075-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="a7075-105">すべての Teams 1:1 またはグループチャットは、それぞれのユーザーのメールボックスにジャーナリングされ、すべての標準チャネルメッセージは、チームを表すグループメールボックスによってジャーナリングされます。</span><span class="sxs-lookup"><span data-stu-id="a7075-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="a7075-106">標準チャネルにアップロードされたファイルについては、SharePoint Online と OneDrive for business の電子情報開示機能の下に記載されています。</span><span class="sxs-lookup"><span data-stu-id="a7075-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="a7075-107">[プライベートチャネル](private-channels.md)のメッセージやファイルの電子情報開示は、標準チャネルでの動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a7075-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="a7075-108">詳細については、「[プライベートチャネルの電子情報開示](#ediscovery-of-private-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7075-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

1.  <span data-ttu-id="a7075-109">Microsoft Teams のコンテンツで電子情報開示の調査を実施するには、[この](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)リンクの手順1を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a7075-109">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="a7075-110">Microsoft Teams のデータは、Excel eDiscovery のエクスポート出力で IM または会話として表示され、をマウントすることができます。[Outlook の PST からエクスポート後のメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="a7075-110">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="a7075-111">をマウントします。[PST] チームの場合は、すべてのスレッドが [会話履歴] の下にあるチームチャットフォルダーに保存されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a7075-111">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="a7075-112">メッセージのタイトルは、チームとチャネルに揃えて配置されます。</span><span class="sxs-lookup"><span data-stu-id="a7075-112">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="a7075-113">以下の画像を確認すると、製造仕様チームのプロジェクト7標準チャネルを送信先しているボブからのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7075-113">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Outlook のユーザーのメールボックス内のチームチャットフォルダーのスクリーンショット](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="a7075-115">ユーザーのメールボックスにプライベートなチャットを表示するには、[会話履歴] の下にあるチームチャットフォルダー内にもあります。</span><span class="sxs-lookup"><span data-stu-id="a7075-115">To see private chats in a user’s mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="a7075-116">ゲスト間のチャットの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="a7075-116">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="a7075-117">現在、ゲストのみが1:1 または 1: N のチャットに参加しているシナリオでは、これらのチャットメッセージの電子情報開示はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a7075-117">Presently, for a scenario where only guests are participating in 1:1 or 1:N chat, we don't support eDiscovery of those chat messages.</span></span> 

<span data-ttu-id="a7075-118">メールボックスがなくても、ゲスト間のチャット (ホームテナントのユーザーがいない1xN のチャット) にはインデックスが作成されず、結果として電子情報開示に含まれません。</span><span class="sxs-lookup"><span data-stu-id="a7075-118">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="a7075-119">ゲスト間チャットの電子情報開示を容易にするために、クラウドベースのメールボックス (またはファントムのメールボックス) を作成して、1xN データを保存します。</span><span class="sxs-lookup"><span data-stu-id="a7075-119">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="a7075-120">チームチャットデータがクラウドベースのメールボックスに保存された後、電子情報開示およびコンプライアンスコンテンツ検索のインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7075-120">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="a7075-121">次の図は、メールボックスがないゲスト間チャットでの電子情報開示の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="a7075-121">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![ゲスト間-チャット-メールボックスなし](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="a7075-123">プライベートチャネルの電子情報開示</span><span class="sxs-lookup"><span data-stu-id="a7075-123">eDiscovery of private channels</span></span>

<span data-ttu-id="a7075-124">プライベートチャネルで送信されたメッセージのレコードは、グループメールボックスではなく、すべてのプライベートチャネルメンバーのメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="a7075-124">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="a7075-125">レコードのタイトルは、送信元のプライベートチャネルを示すように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="a7075-125">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="a7075-126">各プライベートチャネルには、親チームサイトとは別の SharePoint サイトコレクションがあるため、プライベートチャネルのファイルは親チームとは独立して管理されます。</span><span class="sxs-lookup"><span data-stu-id="a7075-126">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="a7075-127">チームは1つのチャネルの電子情報開示をサポートしていないため、チーム全体を検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7075-127">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="a7075-128">プライベートチャネルのコンテンツの電子情報開示検索を実行するには、チーム全体、プライベートチャネルに関連付けられたサイトコレクション (ファイルを含む)、プライベートチャネルメンバーのメールボックス (メッセージを含む) を検索します。</span><span class="sxs-lookup"><span data-stu-id="a7075-128">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="a7075-129">次の手順を使用して、プライベートチャネル内のファイルとメッセージを特定し、電子情報開示検索に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a7075-129">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="a7075-130">電子情報開示検索でプライベートチャネルファイルを含める</span><span class="sxs-lookup"><span data-stu-id="a7075-130">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="a7075-131">これらの手順を実行する前に、 [Sharepoint Online 管理シェルをインストールして、Sharepoint online に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)します。</span><span class="sxs-lookup"><span data-stu-id="a7075-131">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="a7075-132">チーム内のプライベートチャネルに関連付けられているすべての SharePoint サイトコレクションの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7075-132">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="a7075-133">次の PowerShell スクリプトを実行して、チーム内のプライベートチャネルと親チームグループ ID に関連付けられたすべての SharePoint サイトコレクション Url の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="a7075-133">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="a7075-134">チームまたはグループの ID ごとに、次の PowerShell スクリプトを実行して、関連するすべてのプライベートチャネルサイト ($groupID はチームのグループ ID) を特定します。</span><span class="sxs-lookup"><span data-stu-id="a7075-134">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="a7075-135">電子情報開示検索でプライベートチャネルメッセージを含める</span><span class="sxs-lookup"><span data-stu-id="a7075-135">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="a7075-136">これらの手順を実行する前に、[最新バージョンの Teams PowerShell モジュール](teams-powershell-overview.md)がインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a7075-136">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="a7075-137">チーム内のプライベートチャネルの一覧を取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7075-137">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="a7075-138">プライベートチャネルメンバーの一覧を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7075-138">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="a7075-139">電子情報開示検索クエリの一部として、チーム内の各プライベートチャネルからすべてのメンバーのメールボックスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a7075-139">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a7075-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a7075-140">Related topics</span></span>

- [<span data-ttu-id="a7075-141">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a7075-141">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
