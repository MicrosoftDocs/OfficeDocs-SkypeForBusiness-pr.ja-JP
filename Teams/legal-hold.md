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
ms.openlocfilehash: b78fba2a85cd45c07183ebc9df8016f16036dce5
ms.sourcegitcommit: e023c3023f49e196315e176ce346f0dc5825fa56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53275666"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="4469c-103">Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="4469c-103">Place a Microsoft Teams user or team on legal hold</span></span>

<span data-ttu-id="4469c-104">訴訟が適切に期待される場合、組織は電子的に保存された情報 (ESI) (ケースに関連するチャット メッセージTeams含む) を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4469c-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="4469c-105">組織は、特定のトピックまたは特定の個人に関連するメッセージを保持する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4469c-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="4469c-106">この記事では、この記事の法的ホールドについてMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4469c-106">This article will cover legal hold in Microsoft Teams.</span></span> <span data-ttu-id="4469c-107">複数のユーザーにコンテンツをMicrosoft 365、「電子情報開示ホールド[を作成する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds)。</span><span class="sxs-lookup"><span data-stu-id="4469c-107">To hold content across Microsoft 365, see [Create an eDiscovery hold](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds).</span></span>

> [!NOTE]
> <span data-ttu-id="4469c-108">2020 年 2 月に、プライベート チャネルの法的ホールドを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="4469c-108">In February 2020, we turned on legal hold for private channels.</span></span> <span data-ttu-id="4469c-109">プライベート チャネル チャットはユーザーのメールボックスに保存され、通常のチャネル チャットはユーザーのグループ メールボックスTeams保存されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-109">Private channel chats are stored in user mailboxes, while normal channel chats are stored in the Teams’ group mailbox.</span></span> <span data-ttu-id="4469c-110">ユーザー メールボックスに対して既に法的ホールドが設定されている場合、保留ポリシーは、そのメールボックスに保存されているプライベート チャネル メッセージに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-110">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="4469c-111">管理者がこれを有効にするために、これ以上のアクションは必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4469c-111">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="4469c-112">プライベート チャネルで共有されているファイルの法的ホールドもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4469c-112">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="4469c-113">このMicrosoft Teams、チーム全体または選択したユーザーを法的に保留できます。</span><span class="sxs-lookup"><span data-stu-id="4469c-113">Within Microsoft Teams, an entire team or select users can be put on legal hold.</span></span> <span data-ttu-id="4469c-114">これにより、これらのチームで交換されたメッセージ (プライベート チャネルを含む) またはそれらの個人によって交換されたメッセージはすべて、組織のコンプライアンス マネージャーまたは Teams 管理者が検出できます。</span><span class="sxs-lookup"><span data-stu-id="4469c-114">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization's compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="4469c-115">ユーザーをホールドしてもグループは自動的にホールドされません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="4469c-115">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>
> <span data-ttu-id="4469c-116">アクティビティ フィードで送信された通知を保留に設定できない。</span><span class="sxs-lookup"><span data-stu-id="4469c-116">Notifications sent in activity feed can't be placed on hold.</span></span>

<span data-ttu-id="4469c-117">コア電子情報開示ケースでユーザーまたはチームを法的に保留するには:</span><span class="sxs-lookup"><span data-stu-id="4469c-117">To put a user or a team on legal hold in a Core eDiscovery case:</span></span>

1. <span data-ttu-id="4469c-118">[] に移動[Microsoft 365 コンプライアンス センター。](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4469c-118">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="4469c-119">新しいケースを作成すると、メールボックスまたはサイトを保留にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-119">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="4469c-120">[**電子情報開示コア]**  >  **に移動** し、[ケースの作成] をクリック **してケースを作成します**。</span><span class="sxs-lookup"><span data-stu-id="4469c-120">Go to **eDiscovery** > **Core** and create a case by clicking **Create a case**.</span></span> <span data-ttu-id="4469c-121">ケースが作成された後、開きます。</span><span class="sxs-lookup"><span data-stu-id="4469c-121">After the case is created, open it.</span></span>
  
   ![Microsoft Teams] タブが選択され、[ケースの作成] ボタンが表示されます。](media/LegalHold1.png)

   > [!NOTE]
   > <span data-ttu-id="4469c-123">また、ケースに関連付けられているユーザーを保留Advanced eDiscoveryできます。</span><span class="sxs-lookup"><span data-stu-id="4469c-123">You can also place a user on a hold that's associated with an Advanced eDiscovery case.</span></span> <span data-ttu-id="4469c-124">詳細については、「Manage [holds in Advanced eDiscovery 」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)。</span><span class="sxs-lookup"><span data-stu-id="4469c-124">For more information, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

3. <span data-ttu-id="4469c-125">上部のメニューの **[保留リスト]** タブに移動し、[ **作成]** をクリックして保留リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="4469c-125">Go to the **Holds** tab on the top menu and click **Create** to create a hold.</span></span> <span data-ttu-id="4469c-126">ユーザーまたはチームを保留にすることで、それらのユーザーまたはメッセージによって交換されたメッセージはすべて保持されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-126">Placing a user or a team on hold preserves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="4469c-127">新しいケースを作成すると、メールボックスまたはサイトを保留にするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-127">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   ![[保留] タブが選択され、その下に [作成] ボタンが表示されている画像。](media/LegalHold2.png)
    
    1. <span data-ttu-id="4469c-129">**保留にという名前を付けします**。</span><span class="sxs-lookup"><span data-stu-id="4469c-129">**Name your hold**.</span></span> <span data-ttu-id="4469c-130">作成する保留リストのわかりやすい一意の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4469c-130">Select a descriptive and unique name for the hold you are going to create.</span></span>
  
       ![このスクリーンショットは、[保留リストに名前を付け] タブを示しています。ここで、作成する保留リストの名前と説明を入力できます。](media/LegalHold3.png)

    1. <span data-ttu-id="4469c-132">**場所を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4469c-132">**Choose location**.</span></span> <span data-ttu-id="4469c-133">保留をユーザーまたはチーム全体に適用するかどうかを選択します (現在のところ、保留は個々のチャネルに適用できません)。</span><span class="sxs-lookup"><span data-stu-id="4469c-133">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="4469c-134">注: ユーザーが保留の場合、1 対 1 のチャット、1 対多またはグループ チャット、チャネル会話 (プライベート チャネルを含む) で送信したメッセージを含め、すべてのメッセージが保留されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-134">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
    <span data-ttu-id="4469c-135">![ここでは、「新しい保留リストを作成する」の「場所の選択」セクションがあります。このセクションでは、保留を適用する Microsoft Teams を含む M365 オプションを決定できます。](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="4469c-135">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    2. <span data-ttu-id="4469c-136">**クエリ を作成します**。</span><span class="sxs-lookup"><span data-stu-id="4469c-136">**Create query**.</span></span> <span data-ttu-id="4469c-137">保留ポリシーの細分性を高くする場合は、保留をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4469c-137">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="4469c-138">たとえば、検索するキーワードを指定したり、保留を有効にするために満たす必要がある条件を追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4469c-138">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    3. <span data-ttu-id="4469c-139">**保留リストを作成する前** に、設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="4469c-139">**Review your settings** before creating the hold.</span></span>

<span data-ttu-id="4469c-140">法的ホールドが作成された後は、任意の保留ポリシーによって保持されているコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="4469c-140">After the legal hold has been created, you can search the content retained by any hold policy.</span></span> <span data-ttu-id="4469c-141">詳細については、「電子情報開示調査[を行う」を参照Teams。](eDiscovery-investigation.md)</span><span class="sxs-lookup"><span data-stu-id="4469c-141">For more information, see [Conduct an eDiscovery investigation in Teams](eDiscovery-investigation.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4469c-142">ユーザーまたはグループが保留に設定されている場合、すべてのメッセージ コピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-142">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="4469c-143">たとえば、ユーザーがチャネルにメッセージを投稿し、メッセージを変更した場合、保留シナリオでは、メッセージの両方のコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-143">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="4469c-144">法的ホールドが設定されることなく、最新のメッセージだけが保持されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-144">Without the legal hold in-place, only the latest message is retained.</span></span>

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a><span data-ttu-id="4469c-145">コンテンツを保持するために法的に保留するコンテンツTeams場所</span><span class="sxs-lookup"><span data-stu-id="4469c-145">Content locations to place on legal hold to preserve Teams content</span></span>

<span data-ttu-id="4469c-146">役に立つガイドとして、次の表を使用して、さまざまな種類のコンテンツを保持するために、どのコンテンツの場所 (メールボックスやサイトなど) を法的に保留にするかTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="4469c-146">As a helpful guide, you can use the following table to understand what content location (such as a mailbox or site) to place on legal hold to preserve different types of Teams content.</span></span>

|<span data-ttu-id="4469c-147">シナリオ</span><span class="sxs-lookup"><span data-stu-id="4469c-147">Scenario</span></span>  |<span data-ttu-id="4469c-148">コンテンツの場所</span><span class="sxs-lookup"><span data-stu-id="4469c-148">Content location</span></span>  |
|---------|---------|
|<span data-ttu-id="4469c-149">Teamsチャット (1 対 1 のチャット、1:N グループ チャット、プライベート チャネルの会話など)</span><span class="sxs-lookup"><span data-stu-id="4469c-149">Teams chats for a user (for example, 1:1 chats, 1:N group chats, and private channel conversations)</span></span>     |<span data-ttu-id="4469c-150">ユーザー メールボックス。</span><span class="sxs-lookup"><span data-stu-id="4469c-150">User mailbox.</span></span>         |
|<span data-ttu-id="4469c-151">Teams チャット (プライベート チャネルを除く)</span><span class="sxs-lookup"><span data-stu-id="4469c-151">Teams channel chats (excluding private channels)</span></span>    |<span data-ttu-id="4469c-152">チームで使用されるグループ メールボックス。</span><span class="sxs-lookup"><span data-stu-id="4469c-152">Group mailbox used for the team.</span></span>         |
|<span data-ttu-id="4469c-153">Teamsコンテンツ (Wiki のコンテンツやファイルなど)</span><span class="sxs-lookup"><span data-stu-id="4469c-153">Teams file content (for example, Wiki content and files)</span></span>     |<span data-ttu-id="4469c-154">SharePointで使用されるサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4469c-154">SharePoint site used by the team.</span></span>         |
|<span data-ttu-id="4469c-155">Teams チャンネル ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="4469c-155">Teams private channel files</span></span>     |<span data-ttu-id="4469c-156">プライベート SharePoint専用のサイト。</span><span class="sxs-lookup"><span data-stu-id="4469c-156">Dedicated SharePoint site for private channels.</span></span>     |
|<span data-ttu-id="4469c-157">ユーザーのプライベート コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4469c-157">User's private content</span></span>     |<span data-ttu-id="4469c-158">ユーザーのアカウントOneDrive for Businessします。</span><span class="sxs-lookup"><span data-stu-id="4469c-158">The user's OneDrive for Business account.</span></span>         |
|<span data-ttu-id="4469c-159">チャット内のカード コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4469c-159">Card content in chats</span></span>|<span data-ttu-id="4469c-160">1 対 1 のチャット、1:N グループ チャット、およびチャネル メッセージ内のカード コンテンツのプライベート チャネル会話またはグループ メールボックスのユーザー メールボックス。</span><span class="sxs-lookup"><span data-stu-id="4469c-160">User mailbox for 1:1 chats, 1:N group chats, and private channel conversations or group mailbox for card content in channel messages.</span></span> <span data-ttu-id="4469c-161">詳細については、「電子情報開示ホールドを作成する」の「カードコンテンツを保持 [する」セクションを参照してください](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。</span><span class="sxs-lookup"><span data-stu-id="4469c-161">For more information, see the "Preserve card content" section in [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).</span></span>
||||

> [!NOTE]
> <span data-ttu-id="4469c-162">プライベート チャネルで通信を維持するには、ユーザー メールボックス (プライベート チャネル ユーザー) を保留にし、電子情報開示ツールを使用して検索する場合は、そのユーザーのメールボックスを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4469c-162">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="4469c-163">前に説明したように、プライベート チャネル チャットは、チームのグループ メールボックスではなく、ユーザー のメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4469c-163">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="4469c-164">Microsoft 365 の Teams 以外の領域に関するこのトピックの詳細については、「電子情報開示ケースの管理: コンテンツの場所を保留する」を[参照してください](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。</span><span class="sxs-lookup"><span data-stu-id="4469c-164">If you want to read further on this topic for non-Teams areas in Microsoft 365, you should review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>
