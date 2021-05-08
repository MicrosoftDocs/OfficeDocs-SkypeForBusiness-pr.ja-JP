---
title: Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: セキュリティ/コンプライアンス センターを使用した Microsoft Teams のユーザーまたはチームへの訴訟ホールドの適用と、データ要件に基づいて訴訟ホールドを適用する必要のある項目について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f2f269d75a7bf8bd97165329d2ae6b006b940f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112303"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="e3ac6-103">Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="e3ac6-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="e3ac6-104">訴訟が適切に期待される場合、組織は電子的に保存された情報 (ESI) (ケースに関連するチャット メッセージTeams含む) を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="e3ac6-105">組織は、特定のトピックまたは特定の個人に関連するメッセージを保持する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="e3ac6-106">この記事では、Microsoft Teams での法的ホールドについて説明します (M365 スペース全体での保留の実装に対処するには、「電子情報開示ケースの管理[:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)コンテンツの場所を保留にしてください」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-106">This article will cover legal hold in Microsoft Teams (To address hold implementation across the M365 space, please review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).</span></span>

> [!NOTE]
> <span data-ttu-id="e3ac6-107">2020 年 2 月に、プライベート チャネルの法的ホールドまたはケース ホールドを有効にしました (プライベート チャネル チャットはユーザー のメールボックスに保存され、通常のチャネル チャットはチームのグループ メールボックスに保存されます)。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-107">In February 2020, we enabled legal hold or case hold on private channels (private channel chats are stored in user mailboxes, normal channel chats are stored in a Team's group mailbox).</span></span> <span data-ttu-id="e3ac6-108">ユーザー メールボックスに対して既に法的ホールドが設定されている場合、保留ポリシーは、そのメールボックスに保存されているプライベート チャネル メッセージに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-108">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="e3ac6-109">管理者がこれを有効にするために、これ以上のアクションは必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-109">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="e3ac6-110">プライベート チャネルで共有されているファイルの法的ホールドもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-110">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="e3ac6-111">このMicrosoft Teams、チーム全体または一部のユーザーを保留にしたり、法的に保留にしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-111">Within Microsoft Teams, an entire team or select users can be put on hold or legal hold.</span></span> <span data-ttu-id="e3ac6-112">これにより、これらのチームで交換されたメッセージ (プライベート チャネルを含む) またはそれらの個人によって交換されたメッセージはすべて、組織のコンプライアンス マネージャーまたは Teams 管理者が検出できます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-112">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization’s compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="e3ac6-113">ユーザーをホールドしてもグループは自動的にホールドされません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-113">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

<span data-ttu-id="e3ac6-114">ユーザーまたはチームを法的に保留するには:</span><span class="sxs-lookup"><span data-stu-id="e3ac6-114">To put a user or a team on legal hold:</span></span>

1. <span data-ttu-id="e3ac6-115">[Security [& Compliance Center] に移動します](https://go.microsoft.com/fwlink/?linkid=854628)。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-115">Navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="e3ac6-116">新しいケースを作成すると、メールボックスまたはサイトを保留にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-116">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="e3ac6-117">[電子情報開示] または [Advanced eDiscoveryに移動し、[ケースの作成] をクリックしてケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-117">Go to eDiscovery or Advanced eDiscovery and create a case by clicking "Create a case".</span></span> <span data-ttu-id="e3ac6-118">ケースが作成された後、開きます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-118">Once the case is created, open it.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3ac6-119">![Microsoft Teams] タブが選択され、[ケースの作成] ボタンが表示されます。](media/LegalHold1.png)</span><span class="sxs-lookup"><span data-stu-id="e3ac6-119">![Microsoft Teams eDiscovery tab is selected, showing the Create a case button.](media/LegalHold1.png)</span></span>

3. <span data-ttu-id="e3ac6-120">上部のメニューから [保留リスト] セクションに移動し、[+ 作成] をクリックして保留リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-120">Go to the "Holds" section from the top menu and click "+ Create" to create a hold.</span></span> <span data-ttu-id="e3ac6-121">ユーザーまたはチームを保留すると、それらのユーザーまたはメッセージによって交換されたメッセージはすべて保存されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-121">Putting a user or a team on hold saves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="e3ac6-122">新しいケースを作成すると、メールボックスまたはサイトを保留にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-122">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3ac6-123">![[保留] タブが選択され、その下に [作成] ボタンが表示されている画像。](media/LegalHold2.png)</span><span class="sxs-lookup"><span data-stu-id="e3ac6-123">![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)</span></span>

   1. <span data-ttu-id="e3ac6-124">**保留にという名前を付けします**。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-124">**Name your hold**.</span></span> <span data-ttu-id="e3ac6-125">作成する保留リストのわかりやすい一意の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-125">Select a descriptive and unique name for the hold you are going to create.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="e3ac6-126">![このスクリーンショットは、[保留リストに名前を付け] タブを示しています。ここで、作成する保留リストの名前と説明を入力できます。](media/LegalHold3.png)</span><span class="sxs-lookup"><span data-stu-id="e3ac6-126">![This screenshot shows the Name your hold tab, where you can enter in a name and description for the hold you are creating.](media/LegalHold3.png)</span></span>

    2. <span data-ttu-id="e3ac6-127">**場所を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-127">**Choose location**.</span></span> <span data-ttu-id="e3ac6-128">保留をユーザーまたはチーム全体に適用するかどうかを選択します (現在のところ、保留は個々のチャネルに適用できません)。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-128">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="e3ac6-129">注: ユーザーが保留の場合、1 対 1 のチャット、1 対多またはグループ チャット、チャネル会話 (プライベート チャネルを含む) で送信したメッセージを含め、すべてのメッセージが保留されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-129">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
  
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="e3ac6-130">![ここでは、「新しい保留リストを作成する」の「場所の選択」セクションがあります。このセクションでは、保留を適用する Microsoft Teams を含む M365 オプションを決定できます。](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="e3ac6-130">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    3. <span data-ttu-id="e3ac6-131">**クエリ を作成します**。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-131">**Create Query**.</span></span> <span data-ttu-id="e3ac6-132">保留ポリシーの細分性を高くする場合は、保留をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-132">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="e3ac6-133">たとえば、検索するキーワードを指定したり、保留を有効にするために満たす必要がある条件を追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-133">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    4. <span data-ttu-id="e3ac6-134">**組織に公開する** 前に、設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-134">**Review your settings** before publishing it to your organization.</span></span>

<span data-ttu-id="e3ac6-135">法的ホールドが設定された後は、電子情報開示に関する記事に従って、保留ポリシーによって保持Teams[を検出](eDiscovery-investigation.md)できます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-135">After the legal hold has been set, you can discover all the content retained by any hold policy following the [Teams eDiscovery](eDiscovery-investigation.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3ac6-136">ユーザーまたはグループが保留に設定されている場合、すべてのメッセージ コピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-136">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="e3ac6-137">たとえば、ユーザーがチャネルにメッセージを投稿し、メッセージを変更した場合、保留シナリオでは、メッセージの両方のコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-137">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="e3ac6-138">法的ホールドが設定されることなく、最新のメッセージだけが保持されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-138">Without the legal hold in-place, only the latest message is retained.</span></span>

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a><span data-ttu-id="e3ac6-139">コンテンツを保持するために法的に保留するコンテンツTeams場所</span><span class="sxs-lookup"><span data-stu-id="e3ac6-139">Content locations to place on legal hold to preserve Teams content</span></span>

<span data-ttu-id="e3ac6-140">役に立つガイドとして、次の表を使用して、さまざまな種類のコンテンツを保持するために、どのコンテンツの場所 (メールボックスやサイトなど) を法的に保留にするかTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-140">As a helpful guide, you can use the following table to understand what content location (such as a mailbox or site) to place on legal hold to preserve different types of Teams content.</span></span>

|<span data-ttu-id="e3ac6-141">シナリオ</span><span class="sxs-lookup"><span data-stu-id="e3ac6-141">Scenario</span></span>  |<span data-ttu-id="e3ac6-142">コンテンツの場所</span><span class="sxs-lookup"><span data-stu-id="e3ac6-142">Content location</span></span>  |
|---------|---------|
|<span data-ttu-id="e3ac6-143">Teamsチャット (1 対 1 のチャット、1:N グループ チャット、プライベート チャネルの会話など)</span><span class="sxs-lookup"><span data-stu-id="e3ac6-143">Teams chats for a user (for example, 1:1 chats, 1:N group chats, and private channel conversations)</span></span>     |<span data-ttu-id="e3ac6-144">ユーザー メールボックス。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-144">User mailbox.</span></span>         |
|<span data-ttu-id="e3ac6-145">Teams チャット (プライベート チャネルを除く)</span><span class="sxs-lookup"><span data-stu-id="e3ac6-145">Teams channel chats (excluding private channels)</span></span>    |<span data-ttu-id="e3ac6-146">チームで使用されるグループ メールボックス。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-146">Group mailbox used for the team.</span></span>         |
|<span data-ttu-id="e3ac6-147">Teamsコンテンツ (Wiki のコンテンツやファイルなど)</span><span class="sxs-lookup"><span data-stu-id="e3ac6-147">Teams file content (for example, Wiki content and files)</span></span>     |<span data-ttu-id="e3ac6-148">SharePointで使用されるサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-148">SharePoint site used by the team.</span></span>         |
|<span data-ttu-id="e3ac6-149">Teams チャンネル ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="e3ac6-149">Teams private channel files</span></span>     |<span data-ttu-id="e3ac6-150">プライベート SharePoint専用のサイト。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-150">Dedicated SharePoint site for private channels.</span></span>     |
|<span data-ttu-id="e3ac6-151">ユーザーのプライベート コンテンツ</span><span class="sxs-lookup"><span data-stu-id="e3ac6-151">User's private content</span></span>     |<span data-ttu-id="e3ac6-152">ユーザーのアカウントOneDrive for Businessします。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-152">The user's OneDrive for Business account.</span></span>         |
|<span data-ttu-id="e3ac6-153">チャット内のカード コンテンツ</span><span class="sxs-lookup"><span data-stu-id="e3ac6-153">Card content in chats</span></span>|<span data-ttu-id="e3ac6-154">1 対 1 のチャット、1:N グループ チャット、およびチャネル メッセージ内のカード コンテンツのプライベート チャネル会話またはグループ メールボックスのユーザー メールボックス。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-154">User mailbox for 1:1 chats, 1:N group chats, and private channel conversations or group mailbox for card content in channel messages.</span></span> <span data-ttu-id="e3ac6-155">詳細については、「電子情報開示ホールドを作成する」の「カードコンテンツを保持 [する」セクションを参照してください](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-155">For more information, see the "Preserve card content" section in [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).</span></span>
||||

> [!NOTE]
> <span data-ttu-id="e3ac6-156">プライベート チャネルで通信を維持するには、ユーザー メールボックス (プライベート チャネル ユーザー) を保留にし、電子情報開示ツールを使用して検索する場合は、そのユーザーのメールボックスを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-156">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="e3ac6-157">前に説明したように、プライベート チャネル チャットは、チームのグループ メールボックスではなく、ユーザー のメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-157">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="e3ac6-158">Microsoft 365 の Teams 以外の領域に関するこのトピックの詳細については、「電子情報開示ケースの管理: コンテンツの場所を保留する」を[参照してください](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。</span><span class="sxs-lookup"><span data-stu-id="e3ac6-158">If you want to read further on this topic for non-Teams areas in Microsoft 365, you should review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>