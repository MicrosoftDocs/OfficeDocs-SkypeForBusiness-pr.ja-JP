---
title: Teams でのガバナンスを計画する - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Teams でガバナンスを実施するための計画を立てる方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87f52eae4b99a76fc1eddf60fbdfd876efa8da05
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754811"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="70653-103">Teams でのガバナンスを計画する</span><span class="sxs-lookup"><span data-stu-id="70653-103">Plan for governance in Teams</span></span>

<span data-ttu-id="70653-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span><span class="sxs-lookup"><span data-stu-id="70653-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="70653-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span><span class="sxs-lookup"><span data-stu-id="70653-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="70653-106">Microsoft Teams でのガバナンスの詳細については、次のセッションをご覧ください。[Governance, management and lifecycle in Microsoft Teams (Microsoft Teams でのガバナンス、管理、およびライフサイクル)](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="70653-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="70653-107">グループおよびチームの作成、名前付け、分類、およびゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="70653-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="70653-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span><span class="sxs-lookup"><span data-stu-id="70653-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="70653-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="70653-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="70653-110">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="70653-110">Decision points</span></span>|<ul><li><span data-ttu-id="70653-111">自分の組織において、チームについての特定の名前付け規則はありますか?</span><span class="sxs-lookup"><span data-stu-id="70653-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="70653-112">チーム作成者は組織固有の分類をチームに割り当てる機能を必要としていますか?</span><span class="sxs-lookup"><span data-stu-id="70653-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="70653-113">チームにゲストを追加する機能を、チーム単位で制限する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="70653-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="70653-114">自分の組織において、チームを作成可能なユーザーを制限する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="70653-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="70653-115">次の手順</span><span class="sxs-lookup"><span data-stu-id="70653-115">Next steps</span></span>|<ul><li><span data-ttu-id="70653-116">チームの作成、名前付け、分類、およびゲスト アクセスについて、自分の組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="70653-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="70653-117">Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="70653-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="70653-118">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="70653-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="70653-119">次の表を使用して、組織の要件を把握します。</span><span class="sxs-lookup"><span data-stu-id="70653-119">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="70653-120">機能</span><span class="sxs-lookup"><span data-stu-id="70653-120">Capability</span></span> |<span data-ttu-id="70653-121">詳細</span><span class="sxs-lookup"><span data-stu-id="70653-121">Details</span></span> |<span data-ttu-id="70653-122">Azure AD プレミアム</span><span class="sxs-lookup"><span data-stu-id="70653-122">Azure AD Premium</span></span> <br> <span data-ttu-id="70653-123">ライセンス必要</span><span class="sxs-lookup"><span data-stu-id="70653-123">license required</span></span> |<span data-ttu-id="70653-124">Decision</span><span class="sxs-lookup"><span data-stu-id="70653-124">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="70653-125">Team の名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="70653-125">Team naming policy</span></span> | <span data-ttu-id="70653-126">プレフィックス サフィックスに基づくカスタム ブロックの単語を使用します。</span><span class="sxs-lookup"><span data-stu-id="70653-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="70653-127">P1</span><span class="sxs-lookup"><span data-stu-id="70653-127">P1</span></span> |<span data-ttu-id="70653-128">TBD</span><span class="sxs-lookup"><span data-stu-id="70653-128">TBD</span></span> |
|<span data-ttu-id="70653-129">チーム分類</span><span class="sxs-lookup"><span data-stu-id="70653-129">Team classification</span></span> |<span data-ttu-id="70653-130">チームに分類を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="70653-130">Assign classifications to teams.</span></span> |<span data-ttu-id="70653-131">P1</span><span class="sxs-lookup"><span data-stu-id="70653-131">P1</span></span> |<span data-ttu-id="70653-132">TBD</span><span class="sxs-lookup"><span data-stu-id="70653-132">TBD</span></span> |
|<span data-ttu-id="70653-133">チームのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="70653-133">Team guest access</span></span> |<span data-ttu-id="70653-134">ゲストがチームに追加されるのを許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="70653-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="70653-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="70653-135">No</span></span> |<span data-ttu-id="70653-136">TBD</span><span class="sxs-lookup"><span data-stu-id="70653-136">TBD</span></span> |
|<span data-ttu-id="70653-137">チームの作成</span><span class="sxs-lookup"><span data-stu-id="70653-137">Team creation</span></span> |<span data-ttu-id="70653-138">チームの作成を管理者に限定します。</span><span class="sxs-lookup"><span data-stu-id="70653-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="70653-139">不要</span><span class="sxs-lookup"><span data-stu-id="70653-139">No</span></span> |<span data-ttu-id="70653-140">TBD</span><span class="sxs-lookup"><span data-stu-id="70653-140">TBD</span></span>|
|<span data-ttu-id="70653-141">チームの作成</span><span class="sxs-lookup"><span data-stu-id="70653-141">Team creation</span></span> |<span data-ttu-id="70653-142">チームの作成をセキュリティ グループのメンバーに限定します。</span><span class="sxs-lookup"><span data-stu-id="70653-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="70653-143">P1</span><span class="sxs-lookup"><span data-stu-id="70653-143">P1</span></span> |<span data-ttu-id="70653-144">TBD</span><span class="sxs-lookup"><span data-stu-id="70653-144">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="70653-145">事前に計画を立てやすくなるために、[これらのポリシーの設定について、およびどのライセンスが必要とされるかについて確認してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="70653-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="70653-146">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function.</span><span class="sxs-lookup"><span data-stu-id="70653-146">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="70653-147">For additional information, navigate to and expand [Why control who creates Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span><span class="sxs-lookup"><span data-stu-id="70653-147">For additional information, navigate to and expand [Why control who creates Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="70653-148">追加情報</span><span class="sxs-lookup"><span data-stu-id="70653-148">Additional information</span></span>

<span data-ttu-id="70653-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span><span class="sxs-lookup"><span data-stu-id="70653-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="70653-150">For technical guidance on how to implement these settings, see:</span><span class="sxs-lookup"><span data-stu-id="70653-150">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="70653-151">[グループ設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="70653-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

-   <span data-ttu-id="70653-152">[Azure Active Directory での Office 365 グループの名前付けポリシーの強制](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="70653-152">[Enforce a naming policy for Office 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

-   <span data-ttu-id="70653-153">[Office 365 グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="70653-153">[Office 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="70653-154">グループとチームの有効期限、保持、およびアーカイブ化</span><span class="sxs-lookup"><span data-stu-id="70653-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="70653-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span><span class="sxs-lookup"><span data-stu-id="70653-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="70653-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span><span class="sxs-lookup"><span data-stu-id="70653-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="70653-157">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="70653-157">Decision points</span></span>|<ul><li><span data-ttu-id="70653-158">組織はチームに有効期限日を指定することを必要としていますか?</span><span class="sxs-lookup"><span data-stu-id="70653-158">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="70653-159">自分の組織でチームに特定のデータ保持ポリシーを適用する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="70653-159">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="70653-160">自分の組織で、コンテンツを読み取り専用の状態で保存するために、非アクティブなチームをアーカイブ化する機能が必要となる見込みはありますか?</span><span class="sxs-lookup"><span data-stu-id="70653-160">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="70653-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="70653-161">Next steps</span></span>|<ul><li><span data-ttu-id="70653-162">有効期限、データ保持、アーカイブ化についての組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="70653-162">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="70653-163">Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="70653-163">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="70653-164">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="70653-164">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="70653-165">次の表を使用して、組織の要件を把握します。</span><span class="sxs-lookup"><span data-stu-id="70653-165">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="70653-166">機能</span><span class="sxs-lookup"><span data-stu-id="70653-166">Capability</span></span> |<span data-ttu-id="70653-167">詳細</span><span class="sxs-lookup"><span data-stu-id="70653-167">Details</span></span> |<span data-ttu-id="70653-168">Azure AD Premium ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="70653-168">Azure AD Premium license required</span></span> |<span data-ttu-id="70653-169">Decision</span><span class="sxs-lookup"><span data-stu-id="70653-169">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="70653-170">有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="70653-170">Expiration policy</span></span> |<span data-ttu-id="70653-171">有効期限ポリシーを設定することにより、Office 365 グループのライフ サイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="70653-171">Manage the lifecycle of Office 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="70653-172">P1</span><span class="sxs-lookup"><span data-stu-id="70653-172">P1</span></span> |<span data-ttu-id="70653-173">TBD</span><span class="sxs-lookup"><span data-stu-id="70653-173">TBD</span></span>|
|<span data-ttu-id="70653-174">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="70653-174">Retention policy</span></span> |<span data-ttu-id="70653-175">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span><span class="sxs-lookup"><span data-stu-id="70653-175">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="70653-176">**Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span><span class="sxs-lookup"><span data-stu-id="70653-176">**Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="70653-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="70653-177">No</span></span> |<span data-ttu-id="70653-178">TBD</span><span class="sxs-lookup"><span data-stu-id="70653-178">TBD</span></span> |
|<span data-ttu-id="70653-179">アーカイブと復元</span><span class="sxs-lookup"><span data-stu-id="70653-179">Archive and restore</span></span> |<span data-ttu-id="70653-180">チームがアクティブでなくなったときにチームをアーカイブして、参照用または将来再アクティブ化するために保持します。</span><span class="sxs-lookup"><span data-stu-id="70653-180">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="70653-181">不要</span><span class="sxs-lookup"><span data-stu-id="70653-181">No</span></span> |<span data-ttu-id="70653-182">TBD</span><span class="sxs-lookup"><span data-stu-id="70653-182">TBD</span></span> |

> [!Note]
> <span data-ttu-id="70653-183">Group expiration is an Azure AD Premium feature.</span><span class="sxs-lookup"><span data-stu-id="70653-183">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="70653-184">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span><span class="sxs-lookup"><span data-stu-id="70653-184">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="70653-185">追加情報</span><span class="sxs-lookup"><span data-stu-id="70653-185">Additional information</span></span>

<span data-ttu-id="70653-186">これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="70653-186">For technical guidance on how to implement these settings, see:</span></span>

-   <span data-ttu-id="70653-187">[Office 365 グループの有効期限をセットアップする](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)</span><span class="sxs-lookup"><span data-stu-id="70653-187">[Set up Office 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

-   <span data-ttu-id="70653-188">[Teams の保持ポリシーをセットアップする](retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="70653-188">[Set up Teams retention policies](retention-policies.md).</span></span>

-   <span data-ttu-id="70653-189">[チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="70653-189">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>


## <a name="teams-feature-management"></a><span data-ttu-id="70653-190">Teams 機能の管理</span><span class="sxs-lookup"><span data-stu-id="70653-190">Teams feature management</span></span>

<span data-ttu-id="70653-191">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span><span class="sxs-lookup"><span data-stu-id="70653-191">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="70653-192">You can manage messaging, meeting, and calling features, either at the Office 365 tenant level or per-user.</span><span class="sxs-lookup"><span data-stu-id="70653-192">You can manage messaging, meeting, and calling features, either at the Office 365 tenant level or per-user.</span></span> 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="70653-193">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="70653-193">Decision points</span></span>|<ul><li><span data-ttu-id="70653-194">自分の組織で、テナント全体に対して Teams 機能を制限することが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="70653-194">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="70653-195">自分の組織で、特定のユーザーに対して Teams 機能を制限することが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="70653-195">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="70653-196">次の手順</span><span class="sxs-lookup"><span data-stu-id="70653-196">Next steps</span></span>|<ul><li><span data-ttu-id="70653-197">テナントおよびユーザー レベルで Teams の機能を制限するための組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="70653-197">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="70653-198">Teams のロールアウトの一部として、特定の要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="70653-198">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="70653-199">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="70653-199">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="70653-200">Teams の機能管理での重点領域</span><span class="sxs-lookup"><span data-stu-id="70653-200">Teams feature management focus areas</span></span>

<span data-ttu-id="70653-201">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span><span class="sxs-lookup"><span data-stu-id="70653-201">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="70653-202">Different policies can be applied to all users by default or per user as required by your organization.</span><span class="sxs-lookup"><span data-stu-id="70653-202">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="70653-203">自分の組織での各設定の実行についての技術的なガイダンスを含む、すべての設定の詳細なリストについては、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70653-203">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

-   [<span data-ttu-id="70653-204">Office 365 の組織で Microsoft Teams の機能を管理する</span><span class="sxs-lookup"><span data-stu-id="70653-204">Manage Microsoft Teams features in your Office 365 organization</span></span>](enable-features-office-365.md)
-   [<span data-ttu-id="70653-205">新しい Microsoft Teams 管理センターへの移行中に Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="70653-205">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
-   [<span data-ttu-id="70653-206">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="70653-206">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a><span data-ttu-id="70653-207">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="70653-207">Security and compliance</span></span>

<span data-ttu-id="70653-208">Teams は Office 365 の高度なセキュリティおよびコンプライアンス機能に基づいて構築されており、監査および報告、コンプライアンスのコンテンツ検索、電子情報開示、訴訟ホールド、および保持ポリシーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="70653-208">Teams is built on the advanced security and compliance capabilities of Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span> 

> [!Important]
> <span data-ttu-id="70653-209">自分の組織でコンプライアンスおよびセキュリティに関する要件がある場合は、「[Microsoft Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」の記事で、このトピックについての掘り下げた内容を確認してください。</span><span class="sxs-lookup"><span data-stu-id="70653-209">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
