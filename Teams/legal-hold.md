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
ms.openlocfilehash: 63d862cbdf8d31fc00a48849c85994bd878f0bbc
ms.sourcegitcommit: b6aeaa3d98c29bdc120db8ccfcb7ff2c11d246af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570836"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="313a7-103">Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="313a7-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="313a7-104">訴訟が妥当であると予想される場合、組織は、ケースに関連するチームチャットメッセージなど、電子的に保存された情報 (ESI) を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="313a7-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="313a7-105">組織によっては、特定のトピックまたは特定の個人に関連するすべてのメッセージを保持する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="313a7-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="313a7-106">この記事では、Microsoft Teams で法的な保留をカバーします (M365 スペースでの保留実装に対処するには、 [「電子情報開示ケースの管理](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)」を参照してください。コンテンツの場所を保留にする)。</span><span class="sxs-lookup"><span data-stu-id="313a7-106">This article will cover legal hold in Microsoft Teams (To address hold implementation across the M365 space, please review [Manage eDiscovery cases: Place content locations on hold](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).</span></span>

> [!NOTE]
> <span data-ttu-id="313a7-107">2020年2月に、法的保存機能を有効にしました (プライベートチャネルチャットはユーザーのメールボックスに保存されています。標準チャネルチャットは、そのチームのグループメールボックスに保存されています)。</span><span class="sxs-lookup"><span data-stu-id="313a7-107">In Feb 2020, we turned on legal hold or case hold on private channels (private channel chats are stored in user mailboxes, normal channel chats are stored in that Teams’ group mailboxes).</span></span> <span data-ttu-id="313a7-108">ユーザーのメールボックスに対して既に法的保持が有効になっている場合は、保留ポリシーがそのメールボックスに保存されているプライベートチャネルメッセージに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="313a7-108">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="313a7-109">管理者がこれを有効にするために必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="313a7-109">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="313a7-110">プライベートチャネルで共有されているファイルの法的ホールドもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="313a7-110">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="313a7-111">Microsoft Teams では、チーム全体または [ユーザーの選択] を保留または法的保持に入れることができます。</span><span class="sxs-lookup"><span data-stu-id="313a7-111">Within Microsoft Teams, an entire team or select users can be put on hold or legal hold.</span></span> <span data-ttu-id="313a7-112">この操作を行うと、それらのチームで交換されたすべてのメッセージ (プライベートチャネルを含む)、またはそれらのユーザーが交換したメッセージは、組織のコンプライアンスマネージャーまたは Teams の管理者によって検出可能になります。</span><span class="sxs-lookup"><span data-stu-id="313a7-112">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization’s compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="313a7-113">ユーザーをホールドしてもグループは自動的にホールドされません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="313a7-113">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

<span data-ttu-id="313a7-114">ユーザーまたはチームに法的保持を設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="313a7-114">To put a user or a team on Legal Hold:</span></span>

1. <span data-ttu-id="313a7-115">[セキュリティ & コンプライアンスセンター](https://go.microsoft.com/fwlink/?linkid=854628)に移動します。</span><span class="sxs-lookup"><span data-stu-id="313a7-115">Navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="313a7-116">新しいケースを作成すると、メールボックスまたはサイトを保留にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="313a7-116">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="313a7-117">電子情報開示またはアドバンスト eDiscovery に移動し、[ケースの作成] をクリックしてケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="313a7-117">Go to eDiscovery or Advanced eDiscovery and create a case by clicking "Create a case".</span></span> <span data-ttu-id="313a7-118">ケースが作成されたら、それを開きます。</span><span class="sxs-lookup"><span data-stu-id="313a7-118">Once the case is created, open it.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="313a7-119">![[ケースの作成] ボタンが表示された、Microsoft Teams の [電子情報開示] タブが選択されています。](media/LegalHold1.png)</span><span class="sxs-lookup"><span data-stu-id="313a7-119">![Microsoft Teams eDiscovery tab is selected, showing the Create a case button.](media/LegalHold1.png)</span></span>

3. <span data-ttu-id="313a7-120">上部のメニューから「保留」セクションに移動し、「+ 作成」をクリックして保留リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="313a7-120">Go to the "Holds" section from the top menu and click "+ Create" to create a hold.</span></span> <span data-ttu-id="313a7-121">ユーザーまたはチームを保留にすると、それらのユーザーまたはメッセージによって交換されるすべてのメッセージが保存されます。</span><span class="sxs-lookup"><span data-stu-id="313a7-121">Putting a user or a team on hold saves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="313a7-122">新しいケースを作成すると、メールボックスまたはサイトを保留にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="313a7-122">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="313a7-123">![選択された [保留] タブとその下の [作成] ボタンを示す画像。](media/LegalHold2.png)</span><span class="sxs-lookup"><span data-stu-id="313a7-123">![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)</span></span>

   1. <span data-ttu-id="313a7-124">**保留リストに名前** を指定します。</span><span class="sxs-lookup"><span data-stu-id="313a7-124">**Name your hold**.</span></span> <span data-ttu-id="313a7-125">作成する保留リストのわかりやすい一意の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="313a7-125">Select a descriptive and unique name for the hold you are going to create.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="313a7-126">![このスクリーンショットは [保留] タブの名前を示します。ここでは、作成している保留の名前と説明を入力できます。](media/LegalHold3.png)</span><span class="sxs-lookup"><span data-stu-id="313a7-126">![This screenshot shows the Name your hold tab, where you can enter in a name and description for the hold you are creating.](media/LegalHold3.png)</span></span>

    2. <span data-ttu-id="313a7-127">**[場所] を選び** ます。</span><span class="sxs-lookup"><span data-stu-id="313a7-127">**Choose location**.</span></span> <span data-ttu-id="313a7-128">保留をユーザーまたはチーム全体のどちらに適用するかを選択します (保留は、現時点では個々のチャネルに適用できません)。</span><span class="sxs-lookup"><span data-stu-id="313a7-128">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="313a7-129">注: ユーザーが保留になっている場合は、1:1 チャットで送信されたすべてのメッセージが保留になります。 1: 多またはグループチャット、またはチャネルの会話 (プライベートチャネルを含む) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="313a7-129">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
  
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="313a7-130">![ここでは、[新しい保留を作成する] の [場所の選択] セクションがあります。ここでは、Microsoft Teams など、保留を適用する M365 オプションを決定することができます。](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="313a7-130">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    3. <span data-ttu-id="313a7-131">**クエリを作成** します。</span><span class="sxs-lookup"><span data-stu-id="313a7-131">**Create Query**.</span></span> <span data-ttu-id="313a7-132">保留ポリシーのより細かい設定が必要な場合は、保留をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="313a7-132">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="313a7-133">たとえば、検索するキーワードを指定したり、保留を有効にするために満たす必要がある条件を追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="313a7-133">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    4. <span data-ttu-id="313a7-134">組織に公開する前に **、設定を確認** します。</span><span class="sxs-lookup"><span data-stu-id="313a7-134">**Review your settings** before publishing it to your organization.</span></span>

<span data-ttu-id="313a7-135">法的保持が設定された後、 [Teams の電子情報開示](eDiscovery-investigation.md) の記事に従って、保留ポリシーによって保持されているすべてのコンテンツを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="313a7-135">After the legal hold has been set, you can discover all the content retained by any hold policy following the [Teams eDiscovery](eDiscovery-investigation.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="313a7-136">ユーザーまたはグループを保留にすると、すべてのメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="313a7-136">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="313a7-137">たとえば、ユーザーがチャネルでメッセージを投稿した後にそのメッセージを変更した場合、保留シナリオでは、メッセージの両方のコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="313a7-137">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="313a7-138">インプレースの法的保持がない場合は、最新のメッセージのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="313a7-138">Without the legal hold in-place, only the latest message is retained.</span></span>

<span data-ttu-id="313a7-139">役に立つガイドとして、次の表を使用して、データ要件に基づいて法的保持に含める必要があるものを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="313a7-139">As a helpful guide, you can use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="313a7-140">シナリオ</span><span class="sxs-lookup"><span data-stu-id="313a7-140">Scenario</span></span>  |<span data-ttu-id="313a7-141">ホールドを適用する項目</span><span class="sxs-lookup"><span data-stu-id="313a7-141">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="313a7-142">**Microsoft Teams のチャットコンテンツ (1:1 のチャット、1: 複数またはグループチャット、プライベートチャネルの会話など)**</span><span class="sxs-lookup"><span data-stu-id="313a7-142">**Microsoft Teams chat content by a user (on 1:1 chats, 1:many or group chats, private channel conversations, etc.)**</span></span>     |<span data-ttu-id="313a7-143">ユーザーのメールボックス</span><span class="sxs-lookup"><span data-stu-id="313a7-143">User mailbox</span></span>         |
|<span data-ttu-id="313a7-144">**Microsoft Teams チャネルチャット (プライベートチャネルを除く)**</span><span class="sxs-lookup"><span data-stu-id="313a7-144">**Microsoft Teams Channel chats (excluding private channels)**</span></span>    |<span data-ttu-id="313a7-145">チームで使用するグループ メールボックス</span><span class="sxs-lookup"><span data-stu-id="313a7-145">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="313a7-146">**Microsoft Teams のコンテンツ (Wiki、Files など)**</span><span class="sxs-lookup"><span data-stu-id="313a7-146">**Microsoft Teams content (for example, Wiki, Files)**</span></span>     |<span data-ttu-id="313a7-147">チームが使用する SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="313a7-147">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="313a7-148">**Microsoft Teams のプライベートチャネルファイル**</span><span class="sxs-lookup"><span data-stu-id="313a7-148">**Microsoft Teams Private Channel files**</span></span>     |<span data-ttu-id="313a7-149">個人用専用の SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="313a7-149">Dedicated SharePoint site for private</span></span>     |
|<span data-ttu-id="313a7-150">**ユーザーのプライベートコンテンツ**</span><span class="sxs-lookup"><span data-stu-id="313a7-150">**User's private content**</span></span>     |<span data-ttu-id="313a7-151">ユーザーの OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="313a7-151">OneDrive for Business site of the user</span></span>         |
||||

> [!NOTE]
> <span data-ttu-id="313a7-152">プライベートチャネルでの通信を維持するには、ユーザーのメールボックスを保留にしておく必要があります。また、電子情報開示ツールを使用して検索する場合は、そのユーザーのメールボックスを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="313a7-152">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="313a7-153">前に説明したように、プライベートチャネルチャットは、チームのグループメールボックスではなく、ユーザーのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="313a7-153">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="313a7-154">M365 のチーム以外の領域に関するこのトピックについて詳しくは、「電子情報開示ケースを管理する」を参照してください。 [コンテンツの場所を保留に](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="313a7-154">If you want to read further on this topic for non-Teams areas in M365, you should review [Manage eDiscovery cases: Place content locations on hold](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>
