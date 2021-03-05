---
title: Microsoft Teams のアイテム保持ポリシーを管理する
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Microsoft Teams のアイテム保持ポリシーを使用して、内部ポリシー、業界の規制、または法的なニーズに準拠するために必要なメッセージを保持し、責任と見なされたメッセージまたは法的なビジネス価値がないメッセージを削除します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9422fd2b47ac3d460ee10e8933c45964d78282c1
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460657"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="43376-103">Microsoft Teams のアイテム保持ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="43376-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="43376-104">アイテム保持ポリシーによってチャットまたはメッセージが削除されたというメッセージが Teams に表示される場合は、アイテム保持ポリシーに関する Teams メッセージ [を参照してください](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="43376-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="43376-105">このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="43376-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="43376-106">Microsoft 365 のアイテム保持ポリシーと保持ラベルは、組織内の情報を効果的に管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43376-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="43376-107">保持設定を構成して、組織の内部ポリシー、業界の規制、または法的なニーズに準拠するために必要なデータを保持できます。</span><span class="sxs-lookup"><span data-stu-id="43376-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs.</span></span> <span data-ttu-id="43376-108">また、責任と見なされるデータ、保持する必要がなくなったデータ、法的価値またはビジネス価値がないデータを削除する保持設定を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="43376-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="43376-109">Teams はチャットおよびチャネル メッセージのアイテム保持ポリシーをサポートし、管理者は、このデータを保持するか、削除するか、特定の期間保持してから削除するかどうかを積極的に決定できます。</span><span class="sxs-lookup"><span data-stu-id="43376-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="43376-110">Teams のアイテム保持ポリシーは、組織全体に適用することも、特定のユーザーやチームに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="43376-110">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="43376-111">保持ラベルは、Teams ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="43376-111">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="43376-112">Microsoft 365 で他のワークロードのアイテム保持ポリシーまたはアイテム保持ラベルを使用して保持設定を適用する方法の詳細については、「アイテム[](https://docs.microsoft.com/microsoft-365/compliance/retention)保持ポリシーとアイテム保持ラベルについて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43376-112">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](https://docs.microsoft.com/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="43376-113">Teams のアイテム保持ポリシーの最小ライセンス要件は、Microsoft 365 E3 です。</span><span class="sxs-lookup"><span data-stu-id="43376-113">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="43376-114">Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43376-114">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retentiondeletion-policies-work"></a><span data-ttu-id="43376-115">Teams のアイテム保持/削除ポリシーの動作</span><span class="sxs-lookup"><span data-stu-id="43376-115">How Teams retention/deletion policies work</span></span>

<span data-ttu-id="43376-116">Teams チャット メッセージは 2 つの場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="43376-116">Teams chat messages are stored in two locations.</span></span> <span data-ttu-id="43376-117">プライマリ コピーは Azure に保存され、コンパイル ポリシーに使用されるセカンダリ コピーは、チャットに含まれる各ユーザーの Exchange オンライン メールボックスの非表示フォルダーに保存され、Teams チャネル メッセージはチームのグループ メールボックス内の同様の非表示フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="43376-117">Primary copy is stored in Azure, a secondary copy, that is used for compilance policies, is stored in a hidden folder in the Exchange online mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="43376-118">ユーザーまたはチームにチャット メッセージ削除ポリシーを適用すると、最初にセカンダリ コピーが削除され、その後にプライマリ コピーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="43376-118">When a chat message deletion policy is applied to a user or Team, secondary copy is deleted first, followed by primary copy.</span></span> <span data-ttu-id="43376-119">電子情報開示または Teams の検索は、セカンダリ コピーに保存されているメッセージに基づくため、セカンダリ コピーが削除された場合、メッセージは検出できません。</span><span class="sxs-lookup"><span data-stu-id="43376-119">eDiscovery or Teams search is based off of messages stored in secondary copy and hence messages become non discoverable when secondary copy is deleted.</span></span> 

<span data-ttu-id="43376-120">チャット メッセージの保持ポアシーがユーザーまたはチームに適用されている場合、およびメッセージが削除された場合 (別の削除ポリシーまたはユーザー自身が削除された場合)、プライマリ コピーが削除されると、Teams クライアントはメッセージが消えますが、セカンダリ コピーは自動的に、Exchange の回復可能なアイテム フォルダーのサブフォルダーである **、SubfolderHolds** という名前の非表示のフォルダーに移動されます。 </span><span class="sxs-lookup"><span data-stu-id="43376-120">When a chat message retention poilcy is applied to a user or Team, and if the messages are deleted (either due to another deletion policy or by user themselves), the primary copy is deleted, hence Teams client will see the message disappear, but secondary copy is automatically moved to a hidden folder named **SubstrateHolds** , which is as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="43376-121">これらのメッセージが、電子情報開示ツールで検索可能なままになるまで、そのメッセージは、電子情報開示ツールで検索可能なままです。</span><span class="sxs-lookup"><span data-stu-id="43376-121">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="43376-122">Teams アイテム保持ポリシーに含まれる内容と除外される内容、およびポリシーの構成に応じてこれらのポリシーがどのように動作するのかの詳細については [、「Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)の保持について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43376-122">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="43376-123">このページでは、アイテム保持ポリシーでメッセージを削除するときに遅延が発生する場合がある理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="43376-123">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="43376-124">たとえば、メッセージは、アイテム保持ポリシーで構成した有効期限の 7 日後まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="43376-124">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="43376-125">異なる保持設定で複数の Teams アイテム保持ポリシーを設定した場合、保持の原則は競合を解決します。</span><span class="sxs-lookup"><span data-stu-id="43376-125">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="43376-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="43376-126">For example:</span></span>
- <span data-ttu-id="43376-127">同じコンテンツの保持と削除の間に競合がある場合、コンテンツは常に保持されます。</span><span class="sxs-lookup"><span data-stu-id="43376-127">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="43376-128">同じコンテンツを保持する期間に競合がある場合、最長の保持期間は保持されます。</span><span class="sxs-lookup"><span data-stu-id="43376-128">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="43376-129">これら 2 つの保持原則は、Teams に複数のアイテム保持ポリシーがある場合に発生する可能性のあるほとんどの競合に対処しますが、詳細については、「保持の原則」または「優先されるルール」を参照してください [。](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="43376-129">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="43376-130">Teams のアイテム保持ポリシーを使用すべき状況</span><span class="sxs-lookup"><span data-stu-id="43376-130">When to use retention policies for Teams</span></span>

<span data-ttu-id="43376-131">組織は多くの場合、プライベート チャットのデータの方が、一般にプロジェクトとの関連性がより高い会話であるチャネル メッセージよりも負債になりやすいものとみなします。</span><span class="sxs-lookup"><span data-stu-id="43376-131">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="43376-132">管理者は、プライベート チャット (1 対 1 または 1 対多数チャット) のアイテム保持ポリシーとチャネル メッセージのアイテム保持ポリシーを別個に設定できます。</span><span class="sxs-lookup"><span data-stu-id="43376-132">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="43376-133">さらに、組織内の特定のユーザーやチームに適用される固有のポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="43376-133">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="43376-134">Teams のチャットの場合、ポリシーが適用されるユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="43376-134">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="43376-135">Teams のチャネル メッセージの場合は、ポリシーが適用されるチームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="43376-135">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="43376-136">たとえば、チャネル メッセージの場合、組織内の特定のチームには 1 年間の削除ポリシーを適用し、その他のすべてのチームには 3 年間の削除ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="43376-136">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="43376-137">Teams のアイテム保持ポリシーを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="43376-137">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="43376-138">Teams チャットおよびチャネル メッセージのアイテム保持ポリシーを作成するには、Teams の場所のアイテム保持 [ポリシーの手順を使用します](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="43376-138">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="43376-139">このページには、Microsoft 365 の他のワークロードのアイテム保持ポリシーの作成と管理に関する追加情報があります。</span><span class="sxs-lookup"><span data-stu-id="43376-139">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="43376-140">たとえば、Microsoft 365 グループのアイテム保持ポリシーを作成して、Teams にアクセスし、OneDrive または SharePoint に保存されているファイルを保持および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="43376-140">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="43376-141">エンド ユーザーのエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="43376-141">End user experience</span></span>

<span data-ttu-id="43376-142">プライベート チャット (1 対 1 のチャット) またはグループ チャットの場合、ユーザーには、アイテム保持ポリシーの構成よりも古いチャットが削除され、まだ削除されていないメッセージの上に "組織のアイテム保持ポリシーにより古いメッセージが削除されました" というメッセージが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="43376-142">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="43376-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="43376-143">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="Teams のアイテム保持ポリシーのためにチャット メッセージが削除されたという通知を受け取ったユーザー":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams アイテム保持ポリシーの結果としてメッセージが削除されたと説明する Teams のユーザー":::

<span data-ttu-id="43376-146">チャネル メッセージの場合、ユーザー (チャネル メンバー) は、メッセージの有効期限が切れると、削除されたメッセージがビューから消えます。</span><span class="sxs-lookup"><span data-stu-id="43376-146">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="43376-147">削除されたメッセージがスレッド会話の親メッセージであった場合、親メッセージの代わりに "アイテム保持ポリシーに従い、このメッセージは削除されました。" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43376-147">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="43376-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="43376-148">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保持前のチャネルのスクリーンショット":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保持後のチャネルのスクリーンショット":::

> [!NOTE]
> <span data-ttu-id="43376-151">削除されたメッセージの結果としてユーザーに表示されるメッセージは、現時点では構成できません。</span><span class="sxs-lookup"><span data-stu-id="43376-151">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="43376-152">表示されるメッセージ内のリンクは、 [アイテム保持ポリシーに関する Teams メッセージに移動します](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。</span><span class="sxs-lookup"><span data-stu-id="43376-152">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="43376-153">エンド ユーザー向けこのドキュメントは、メッセージが削除された理由に関する基本的な質問に答えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43376-153">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="43376-154">ただし、アイテム保持ポリシーの展開の一環として、設定した設定の影響をユーザーとヘルプ デスクに伝えます。</span><span class="sxs-lookup"><span data-stu-id="43376-154">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43376-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="43376-155">Related topics</span></span>

- [<span data-ttu-id="43376-156">アイテム保持ポリシーとアイテム保持ラベルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="43376-156">Get started with retention policies and retention labels</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="43376-157">Microsoft Teams の保持について</span><span class="sxs-lookup"><span data-stu-id="43376-157">Learn about retention for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="43376-158">アイテム保持ポリシーを作成および構成する</span><span class="sxs-lookup"><span data-stu-id="43376-158">Create and configure retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)
