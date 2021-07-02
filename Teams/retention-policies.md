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
description: Microsoft Teams のアイテム保持ポリシーを使用して、組織の内部ポリシー、業界規制、または法的要件に準拠するために組織が必要とするメッセージを保持し、負債とみなされるメッセージや法的にビジネス価値のないメッセージを削除します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c99fc4bfb185ec291a98a96572167b389b3e6252
ms.sourcegitcommit: 28b83243411b54760875e7fd137549d5d2182c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53252652"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="c4af2-103">Teams のアイテム保持ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="c4af2-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="c4af2-104">チャットまたはメッセージがアイテム保持ポリシーによって削除されたというメッセージが Teams に表示されている場合は、「[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4af2-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="c4af2-105">このページの情報は、これらのアイテム保持ポリシーを管理する IT 管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="c4af2-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="c4af2-106">Microsoft 365 のアイテム保持ポリシーと保持ラベルは、組織内の情報をより効果的に管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="c4af2-107">保持設定を構成して、組織の内部ポリシー、業界規制、または法的要件に準拠する必要のあるデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal requirements.</span></span> <span data-ttu-id="c4af2-108">保持設定を構成して、責任があると見なされたデータ、保持する必要がなくなったデータ、または法的価値やビジネス価値のないデータを削除するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="c4af2-109">Teams では、チャットやチャネルのメッセージ用にアイテム保持ポリシーを設定するサポートを行い、管理者としてデータを保持するか、削除するか、特定の期間保持した後に削除するかを前もって決定できます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="c4af2-110">これらのアクションの保持期間の開始は、常にメッセージが作成されるタイミングに基づきます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-110">The start of the retention period for these actions is always based on when a message is created.</span></span> <span data-ttu-id="c4af2-111">Teams のアイテム保持ポリシーは、組織全体に適用することも、特定のユーザーやチームに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-111">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="c4af2-112">保持ラベルは、Teams ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c4af2-112">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="c4af2-113">Microsoft 365 での保持ソリューションに関する詳細については、「[保持ポリシーと保持ラベルの詳細](/microsoft-365/compliance/retention)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4af2-113">To learn more about retention solutions in Microsoft 365, see [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="c4af2-114">Teams でのアイテム保持ポリシーの対象となるユーザーは、Office 365 E3 や Office 365 A3 などの適切なライセンスを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4af2-114">Users who are subject to a retention policy for Teams must have an appropriate license, such as Office 365 E3 or Office 365 A3.</span></span> <span data-ttu-id="c4af2-115">これらのアイテム保持ポリシーへのその他のライセンス オプションについては、[[セキュリティとコンプライアンス向け Microsoft 365 ライセンス ガイド]](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) で [[情報ガバナンス]](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4af2-115">For other licensing options for these retention policies, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) section from [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance).</span></span> <span data-ttu-id="c4af2-116">Teams のライセンスの詳細については、「[Microsoft Teams サービスのサービスの説明](/office365/servicedescriptions/teams-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4af2-116">To learn more about licensing for Teams, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a><span data-ttu-id="c4af2-117">Teams のアイテム保持ポリシーが保持と削除のアクションをサポートする方法</span><span class="sxs-lookup"><span data-stu-id="c4af2-117">How Teams retention policies support retain and delete actions</span></span>

<span data-ttu-id="c4af2-118">チャットやチャネル メッセージを保持するように Teams のアイテム保持ポリシーを構成した場合でも、ユーザーは Teams アプリでメッセージを編集したり削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-118">If you configure a Teams retention policy to retain chats or channel messages, users can still edit and delete their messages in their Teams app.</span></span> <span data-ttu-id="c4af2-119">ユーザーは、Teams で編集前のメッセージや削除したメッセージを見ることができなくなりますが、これらのメッセージのデータは、コンプライアンス管理者によって電子情報開示検索用に設計された安全な場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-119">Although users no longer see their pre-edited or deleted messages in Teams, data from these messages is stored in a secured location that's designed for eDiscovery searches by compliance administrators.</span></span> <span data-ttu-id="c4af2-120">このデータの完全な削除は、構成された保持期間が終了する前には行われず、このデータを保持するために別のアイテム保持ポリシーが構成されているか、[電子情報開示ホールド](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)の対象となっている場合に行われます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-120">Permanent deletion of this data doesn't happen before the end of the configured retention period, or if another retention policy is configured to retain this data, or it is subject to an [eDiscovery hold](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).</span></span>

<span data-ttu-id="c4af2-121">チャットやチャネルのメッセージを削除するようにアイテム保持ポリシーを構成した場合は、これらのメッセージは自動削除の対象となります。</span><span class="sxs-lookup"><span data-stu-id="c4af2-121">When a retention policy is configured to delete chats and channel messages, these messages become eligible for automatic deletion.</span></span> <span data-ttu-id="c4af2-122">メッセージがまだ Teams アプリに表示されている場合は、底場所から消え、[ユーザーにはアイテム保持ポリシーによりこれらのメッセージが削除されたことが通知されます](#end-user-experience)。</span><span class="sxs-lookup"><span data-stu-id="c4af2-122">If the messages are still displayed in the Teams app, they will disappear from there and [users are informed that a retention policy has deleted these messages](#end-user-experience).</span></span> <span data-ttu-id="c4af2-123">以前、メッセージが保持アクションの対象となり、ユーザーによって編集または削除された場合、これらのメッセージは保護された場所から削除され、電子情報開示の検索で返されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c4af2-123">If the messages were previously subject to a retain action and have been edited or deleted by users, these messages will now be deleted from the secured location and no longer returned in eDiscovery searches.</span></span>

<span data-ttu-id="c4af2-124">ポリシー構成やユーザーの操作によってこれらのポリシーが機能する方法や、Teams のアイテム保持ポリシーに含まれるメッセージ データや含まれないメッセージ データの詳細については、「[Microsoft Teams の保持の詳細](/microsoft-365/compliance/retention-policies-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4af2-124">For detailed information about how these policies work depending on your policy configuration and user actions, and what message data is included and excluded for Teams retention policies, see [Learn about retention for Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).</span></span> <span data-ttu-id="c4af2-125">このページでは、アイテム保持ポリシーでのメッセージを削除する場合に延期される場合がある理由についても説明しています。</span><span class="sxs-lookup"><span data-stu-id="c4af2-125">That page also explains why you might sometimes experience delays when retention policies delete messages.</span></span> <span data-ttu-id="c4af2-126">たとえば、メッセージは、アイテム保持ポリシーで設定した有効期限の 7 日後まで、Teams アプリのユーザーに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-126">For example, messages can be visible to users in the Teams app up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="c4af2-p107">異なる保持設定を持つ複数の Teams アイテム保持ポリシーを設定した場合、保持の原則によって競合が解消されます。例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-p107">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts. For example:</span></span>

- <span data-ttu-id="c4af2-129">同じコンテンツを保持するか削除するかで競合が生じた場合、コンテンツは常にセキュリティで保護された場所に保持されるため、コンプライアンス管理者が電子情報開示で検索可能な状態は維持されます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-129">If there is a conflict between retaining or deleting the same content, the content is always retained in the secured location so that it remains searchable with eDiscovery for compliance administrators.</span></span>
    
    <span data-ttu-id="c4af2-130">この原則は、法律上または調査上の理由で電子情報開示の適用対象となっているメッセージにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-130">This principle also applies to messages that are under eDiscovery holds for legal or investigative reasons.</span></span>

- <span data-ttu-id="c4af2-131">同じコンテンツをどのくらいの期間セキュリティで保護された場所に保持するかで競合する場合は、最も長い保持期間で保持されます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-131">If there is a conflict in how long to retain the same content, it is retained in the secured location for the longest retention period.</span></span>

<span data-ttu-id="c4af2-132">この 2 つの保持の原則は、Teams に複数のアイテム保持ポリシーがある場合に発生する可能性のあるほとんどの矛盾を解決しますが、詳細については「[保持するための原則、または優先順位](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4af2-132">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="c4af2-133">Teams のアイテム保持ポリシーを使用すべき状況</span><span class="sxs-lookup"><span data-stu-id="c4af2-133">When to use retention policies for Teams</span></span>

<span data-ttu-id="c4af2-134">組織は多くの場合、プライベート チャットのデータの方が、一般にプロジェクトとの関連性がより高い会話であるチャネル メッセージよりも負債になりやすいものとみなします。</span><span class="sxs-lookup"><span data-stu-id="c4af2-134">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="c4af2-135">すべてのメッセージに対して 1 つのアイテム保持ポリシーを非常に効率的Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-135">You can very efficiently configure a single retention policy for all Teams messages.</span></span> <span data-ttu-id="c4af2-136">または、よりきめ細かく制御するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c4af2-136">Or, for more fine-grained control, you can:</span></span>

- <span data-ttu-id="c4af2-137">プライベート チャット (1:1 または 1:多のチャット)、標準チャネルからのメッセージ、またはプライベート チャネルからのメッセージに対して個別の保持ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-137">Have separate retention policies for private chats (1:1 or 1:many chats), messages from standard channels, or messages from private channels.</span></span>

- <span data-ttu-id="c4af2-138">ポリシーは、組織内の特定のユーザーまたはチームにのみ適用します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-138">Apply the policies only to specific users or teams in your organization.</span></span> <span data-ttu-id="c4af2-139">チャットTeamsプライベート チャネルの場合は、ポリシーを適用するユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-139">For Teams chats and private channels, you can select which users the policy applies to.</span></span> <span data-ttu-id="c4af2-140">Teams のチャネル メッセージの場合は、ポリシーが適用されるチームを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-140">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="c4af2-141">たとえば、標準チャネル メッセージの場合: 組織内の特定のチームのアイテム保持ポリシーを作成し、1 年後に削除アクションを使用してそのポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-141">For example, for standard channel messages: Create a retention policy for specific teams in your organization and configure that policy with a delete action after 1 year.</span></span> <span data-ttu-id="c4af2-142">その後、他のすべてのチームの標準チャネル メッセージに対して別のアイテム保持ポリシーを作成し、3 年後に削除アクションを使用してそのポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-142">Then create another retention policy for standard channel messages for all other teams and configure that policy with a delete action after 3 years.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="c4af2-143">Teams 向けアイテム保持ポリシーの作成と管理</span><span class="sxs-lookup"><span data-stu-id="c4af2-143">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="c4af2-144">メッセージの保持ポリシーを作成または編集するにはTeamsのアイテム保持ポリシーに関するページの[Teams使用します](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)。</span><span class="sxs-lookup"><span data-stu-id="c4af2-144">To create or edit a retention policy for Teams messages, use the instructions from [Retention policy for Teams locations](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="c4af2-145">このページには、Microsoft 365 の他のワークロードのアイテム保持ポリシーの作成と管理に関する追加情報があります。</span><span class="sxs-lookup"><span data-stu-id="c4af2-145">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="c4af2-146">たとえば、Microsoft 365 グループのアイテム保持ポリシーを作成して、Teams でアクセスし、OneDrive や SharePoint に保存されたファイルを保持または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-146">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="c4af2-147">エンドユーザーのエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="c4af2-147">End-user experience</span></span>

<span data-ttu-id="c4af2-p112">私的なチャット (1:1 のチャット) やグループのチャットの場合、ユーザーにはアイテム保持ポリシーの構成より古いチャットは削除され、"組織のアイテム保持ポリシーにより、古いメッセージを削除しました" という自動生成メッセージがまだ削除されていないメッセージの上に表示されます。例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-p112">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages. For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="Teams アイテム保持ポリシーにより、チャット メッセージが削除されることが Teams でユーザーに通知される":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams のユーザーが説明するメッセージが、Teams のアイテム保持ポリシーの結果として削除される":::

<span data-ttu-id="c4af2-152">チャネル メッセージの場合、ユーザー (チャネル メンバー) には、メッセージの有効期限が切れた後に、削除したメッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c4af2-152">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="c4af2-153">削除されたメッセージがスレッド会話の親メッセージであった場合、親メッセージの代わりに "アイテム保持ポリシーに従い、このメッセージは削除されました。" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-153">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="c4af2-154">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-154">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="保持前のチャネルのスクリーンショット":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="保持後のチャネルのスクリーンショット":::

> [!NOTE]
> <span data-ttu-id="c4af2-157">削除済みメッセージの結果としてユーザーに表示されるメッセージは、この時点では構成できません。</span><span class="sxs-lookup"><span data-stu-id="c4af2-157">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="c4af2-158">これらの表示されたメッセージ内のリンクは、[アイテム保持ポリシーに関する Teams メッセージ](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4af2-158">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="c4af2-159">エンド ユーザー向けのこのドキュメントは、メッセージが削除された理由に関する基本的な質問に答えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c4af2-159">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="c4af2-160">ただし、アイテム保持ポリシーの展開の一環として、構成した設定の影響をユーザーやヘルプ デスクに連絡するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c4af2-160">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c4af2-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4af2-161">Related topics</span></span>

- [<span data-ttu-id="c4af2-162">アイテム保持ポリシーおよび保持ラベルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c4af2-162">Get started with retention policies and retention labels</span></span>](/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="c4af2-163">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="c4af2-163">Learn about retention for Microsoft Teams</span></span>](/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="c4af2-164">アイテム保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="c4af2-164">Create and configure retention policies</span></span>](/microsoft-365/compliance/create-retention-policies)
