---
title: Teams のアイテム保持ポリシーを管理する
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Microsoft Teams のアイテム保持ポリシーを使用して、組織の内部ポリシー、業界規制、または法的ニーズに準拠するために必要なメッセージを保持し、負債とみなされるメッセージや法的にビジネス価値のないメッセージを削除します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d7d998afb47480fa59ce936a93e20af9ac4b2a12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117605"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="186c7-103">Teams のアイテム保持ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="186c7-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="186c7-104">チャットまたはメッセージがアイテム保持ポリシーによって削除されたというメッセージが Teams に表示されている場合は、「[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="186c7-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="186c7-105">このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="186c7-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="186c7-106">Microsoft 365 のアイテム保持ポリシーと保持ラベルは、組織内の情報をより効果的に管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="186c7-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="186c7-107">保持設定を構成して、組織の内部ポリシー、業界規制、または法的ニーズに準拠する必要のあるデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="186c7-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs.</span></span> <span data-ttu-id="186c7-108">保持設定を構成して、責任があると見なされたデータ、保持する必要がなくなったデータ、または法的価値やビジネス価値のないデータを削除するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="186c7-109">Teams では、チャットやチャネルのメッセージ用にアイテム保持ポリシーを設定するサポートを行い、管理者としてデータを保持するか、削除するか、特定の期間保持した後に削除するかを前もって決定できます。</span><span class="sxs-lookup"><span data-stu-id="186c7-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="186c7-110">Teams のアイテム保持ポリシーは、組織全体に適用することも、特定のユーザーやチームに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="186c7-110">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="186c7-111">保持ラベルは、Teams ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="186c7-111">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="186c7-112">保持についての詳細や、Microsoft 365 の他のワークロードにアイテム保持ポリシーや保持ラベルを使用して保持設定を適用する方法については、「[アイテム保持ポリシーと保持ラベルの詳細](/microsoft-365/compliance/retention)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="186c7-112">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="186c7-113">Teams 向けのアイテム保持ポリシーの最小ライセンス要件は、Microsoft 365 E3 です。</span><span class="sxs-lookup"><span data-stu-id="186c7-113">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="186c7-114">Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="186c7-114">To learn more about licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retentiondeletion-policies-work"></a><span data-ttu-id="186c7-115">Teams のアイテム保持/削除ポリシーのしくみ</span><span class="sxs-lookup"><span data-stu-id="186c7-115">How Teams retention/deletion policies work</span></span>

<span data-ttu-id="186c7-116">Teams チャットのメッセージは、2 つの場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-116">Teams chat messages are stored in two locations.</span></span> <span data-ttu-id="186c7-117">プライマリ コピーは Azure に保存され、コンパイル ポリシーに使用されるセカンダリ コピーは、チャットに含まれる各ユーザーの Exchange online メールボックス内の隠しフォルダーに保存されます。また、Teams のチャネル メッセージは、チーム用のグループ メールボックス内の同様の隠しフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-117">Primary copy is stored in Azure, a secondary copy, that is used for compilance policies, is stored in a hidden folder in the Exchange online mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="186c7-118">チャット メッセージの削除ポリシーがユーザーやチームに適用された場合、セカンダリ コピーが最初に削除され、続いてプライマリ コピーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-118">When a chat message deletion policy is applied to a user or Team, secondary copy is deleted first, followed by primary copy.</span></span> <span data-ttu-id="186c7-119">電子情報開示や Teams 検索は、セカンダリ コピーに保存されたメッセージに基づいて行われるため、セカンダリ コピーが削除されるとメッセージを検出できなくなります。</span><span class="sxs-lookup"><span data-stu-id="186c7-119">eDiscovery or Teams search is based off of messages stored in secondary copy and hence messages become non discoverable when secondary copy is deleted.</span></span> 

<span data-ttu-id="186c7-120">チャット メッセージのアイテム保持ポリシーがユーザーまたはチームに適用されている場合、メッセージが削除されると (他の削除ポリシーまたはユーザー自身によって)、プライマリ コピーが削除されるため、Teams クライアントにメッセージが表示されなくなりますが、セカンダリ コピーは自動的に **SubstrateHolds** という名前の隠しフォルダに移動します。これは、Exchange **回復可能なアイテム** フォルダ内のサブフォルダです。</span><span class="sxs-lookup"><span data-stu-id="186c7-120">When a chat message retention poilcy is applied to a user or Team, and if the messages are deleted (either due to another deletion policy or by user themselves), the primary copy is deleted, hence Teams client will see the message disappear, but secondary copy is automatically moved to a hidden folder named **SubstrateHolds** , which is as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="186c7-121">メッセージは SubstituteHolds フォルダ内から完全に削除されるまで、メッセージは電子情報開示ツールで検索できます。</span><span class="sxs-lookup"><span data-stu-id="186c7-121">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="186c7-122">Teams のアイテム保持ポリシーに含まれる内容や含まれない内容、また、ポリシー構成によってこれらのポリシーが機能する方法の詳細については、「[Microsoft Teams の保持の詳細](/microsoft-365/compliance/retention-policies-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="186c7-122">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="186c7-123">このページでは、アイテム保持ポリシーでのメッセージの削除で延期される場合がある理由を説明しています。</span><span class="sxs-lookup"><span data-stu-id="186c7-123">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="186c7-124">たとえば、メッセージは、アイテム保持ポリシーで設定した有効期限の 7 日後まで見ることができます。</span><span class="sxs-lookup"><span data-stu-id="186c7-124">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="186c7-125">異なる保持設定を持つ複数の Teams アイテム保持ポリシーを設定した場合、保持の原則によって競合が解消されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-125">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="186c7-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="186c7-126">For example:</span></span>
- <span data-ttu-id="186c7-127">同じコンテンツを保持するか削除するかで競合する場合、そのコンテンツは常に保持されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-127">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="186c7-128">同じコンテンツをどのくらいの期間保持するかで競合する場合は、最も長い保持期間で保持されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-128">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="186c7-129">この 2 つの保持の原則は、Teams に複数のアイテム保持ポリシーがある場合に発生する可能性のあるほとんどの矛盾を解決しますが、詳細については「[保持するための原則、または優先順位](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="186c7-129">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="186c7-130">Teams のアイテム保持ポリシーを使用すべき状況</span><span class="sxs-lookup"><span data-stu-id="186c7-130">When to use retention policies for Teams</span></span>

<span data-ttu-id="186c7-131">組織は多くの場合、プライベート チャットのデータの方が、一般にプロジェクトとの関連性がより高い会話であるチャネル メッセージよりも負債になりやすいものとみなします。</span><span class="sxs-lookup"><span data-stu-id="186c7-131">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="186c7-132">管理者は、プライベート チャット (1 対 1 または 1 対多数チャット) のアイテム保持ポリシーとチャネル メッセージのアイテム保持ポリシーを別個に設定できます。</span><span class="sxs-lookup"><span data-stu-id="186c7-132">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="186c7-133">さらに、組織内の特定のユーザーやチームに適用される固有のポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="186c7-133">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="186c7-134">Teams のチャットの場合、ポリシーが適用されるユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="186c7-134">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="186c7-135">Teams のチャネル メッセージの場合は、ポリシーが適用されるチームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="186c7-135">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="186c7-136">たとえば、チャネル メッセージの場合、組織内の特定のチームには 1 年間の削除ポリシーを適用し、その他のすべてのチームには 3 年間の削除ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="186c7-136">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="186c7-137">Teams 向けアイテム保持ポリシーの作成と管理</span><span class="sxs-lookup"><span data-stu-id="186c7-137">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="186c7-138">Teams のチャットやチャネル メッセージのアイテム保持ポリシーを作成するには、「[Teams の場所にアイテム保持ポリシーを作成する](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)」での説明を活用してください。</span><span class="sxs-lookup"><span data-stu-id="186c7-138">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="186c7-139">このページには、Microsoft 365 の他のワークロードのアイテム保持ポリシーの作成と管理に関する追加情報があります。</span><span class="sxs-lookup"><span data-stu-id="186c7-139">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="186c7-140">たとえば、Microsoft 365 グループのアイテム保持ポリシーを作成して、Teams でアクセスし、OneDrive や SharePoint に保存されたファイルを保持または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="186c7-140">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="186c7-141">エンド ユーザーのエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="186c7-141">End user experience</span></span>

<span data-ttu-id="186c7-142">私的なチャット (1:1 のチャット) やグループのチャットの場合、ユーザーにはアイテム保持ポリシーの構成より古いチャットは削除され、"組織のアイテム保持ポリシーにより、古いメッセージを削除しました" という自動生成メッセージがまだ削除されていないメッセージの上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-142">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="186c7-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="186c7-143">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="Teams アイテム保持ポリシーにより、チャット メッセージが削除されることが Teams でユーザーに通知される":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams のユーザーが説明するメッセージが、Teams のアイテム保持ポリシーの結果として削除される":::

<span data-ttu-id="186c7-146">チャネル メッセージの場合、ユーザー (チャネル メンバー) には、メッセージの有効期限が切れた後に、削除したメッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="186c7-146">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="186c7-147">削除されたメッセージがスレッド会話の親メッセージであった場合、親メッセージの代わりに "アイテム保持ポリシーに従い、このメッセージは削除されました。" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="186c7-147">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="186c7-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="186c7-148">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保持前のチャネルのスクリーンショット":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保持後のチャネルのスクリーンショット":::

> [!NOTE]
> <span data-ttu-id="186c7-151">削除済みメッセージの結果としてユーザーに表示されるメッセージは、この時点では構成できません。</span><span class="sxs-lookup"><span data-stu-id="186c7-151">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="186c7-152">これらの表示されたメッセージ内のリンクは、[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)に移動します。</span><span class="sxs-lookup"><span data-stu-id="186c7-152">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="186c7-153">エンド ユーザー向けのこのドキュメントは、メッセージが削除された理由に関する基本的な質問に答えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="186c7-153">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="186c7-154">ただし、アイテム保持ポリシーの展開の一環として、構成した設定の影響をユーザーやヘルプ デスクに連絡するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="186c7-154">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="186c7-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="186c7-155">Related topics</span></span>

- [<span data-ttu-id="186c7-156">アイテム保持ポリシーおよび保持ラベルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="186c7-156">Get started with retention policies and retention labels</span></span>](/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="186c7-157">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="186c7-157">Learn about retention for Microsoft Teams</span></span>](/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="186c7-158">アイテム保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="186c7-158">Create and configure retention policies</span></span>](/microsoft-365/compliance/create-retention-policies)