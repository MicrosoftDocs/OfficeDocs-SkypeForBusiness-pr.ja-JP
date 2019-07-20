---
title: Teams でのガバナンスを計画する - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
description: Teams でガバナンスを実施するための計画を立てる方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7022c700d2b7448625bb9ab627d1b77d780b50e
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2019
ms.locfileid: "35804866"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="882f4-103">Teams でのガバナンスを計画する</span><span class="sxs-lookup"><span data-stu-id="882f4-103">Plan for governance in Teams</span></span>

<span data-ttu-id="882f4-p101">Teams には組織が必要とする可能性のあるガバナンス機能を実装するための豊富なツールセットが用意されています。この記事では、IT プロフェッショナルが、ガバナンスに関する組織の要件と、その要件を満たす方法を判断する際に適切な質問をするためのガイドを示します。</span><span class="sxs-lookup"><span data-stu-id="882f4-p101">Teams provides a rich set of tools to implement any governance capabilities your organization might require. This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="882f4-106">Microsoft Teams でのガバナンスの詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="882f4-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="882f4-107">グループおよびチームの作成、名前付け、分類、およびゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="882f4-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="882f4-p102">自分の組織において、チームの命名や分類について、ゲストがチーム メンバーとして追加することができるかどうかについて、チームを作成できるユーザーが誰であるかについて、厳密な制御の実施が必要な場合があります。この各領域は Azure Active Directory (Azure AD) を使って設定できます。</span><span class="sxs-lookup"><span data-stu-id="882f4-p102">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams. You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="882f4-110">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="882f4-110">Decision points</span></span>|<ul><li><span data-ttu-id="882f4-111">自分の組織において、チームについての特定の名前付け規則はありますか?</span><span class="sxs-lookup"><span data-stu-id="882f4-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="882f4-112">チーム作成者は組織固有の分類をチームに割り当てる機能を必要としていますか?</span><span class="sxs-lookup"><span data-stu-id="882f4-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="882f4-113">チームにゲストを追加する機能を、チーム単位で制限する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="882f4-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="882f4-114">自分の組織において、チームを作成可能なユーザーを制限する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="882f4-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="882f4-115">次のステップ</span><span class="sxs-lookup"><span data-stu-id="882f4-115">Next steps</span></span>|<ul><li><span data-ttu-id="882f4-116">チームの作成、名前付け、分類、およびゲスト アクセスについて、自分の組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="882f4-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="882f4-117">Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="882f4-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="882f4-118">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="882f4-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="882f4-119">次の表を使用して、組織の要件を把握します。</span><span class="sxs-lookup"><span data-stu-id="882f4-119">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="882f4-120">機能</span><span class="sxs-lookup"><span data-stu-id="882f4-120">Capability</span></span> |<span data-ttu-id="882f4-121">詳細</span><span class="sxs-lookup"><span data-stu-id="882f4-121">Details</span></span> |<span data-ttu-id="882f4-122">Azure AD プレミアム</span><span class="sxs-lookup"><span data-stu-id="882f4-122">Azure AD Premium</span></span> <br> <span data-ttu-id="882f4-123">ライセンス必要</span><span class="sxs-lookup"><span data-stu-id="882f4-123">license required</span></span> |<span data-ttu-id="882f4-124">Decision</span><span class="sxs-lookup"><span data-stu-id="882f4-124">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="882f4-125">Team の名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="882f4-125">Team naming policy</span></span> | <span data-ttu-id="882f4-126">プレフィックス サフィックスに基づくカスタム ブロックの単語を使用します。</span><span class="sxs-lookup"><span data-stu-id="882f4-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="882f4-127">P1</span><span class="sxs-lookup"><span data-stu-id="882f4-127">P1</span></span> |<span data-ttu-id="882f4-128">TBD</span><span class="sxs-lookup"><span data-stu-id="882f4-128">TBD</span></span> |
|<span data-ttu-id="882f4-129">チーム分類</span><span class="sxs-lookup"><span data-stu-id="882f4-129">Team classification</span></span> |<span data-ttu-id="882f4-130">チームに分類を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="882f4-130">Assign classifications to teams.</span></span> |<span data-ttu-id="882f4-131">P1</span><span class="sxs-lookup"><span data-stu-id="882f4-131">P1</span></span> |<span data-ttu-id="882f4-132">TBD</span><span class="sxs-lookup"><span data-stu-id="882f4-132">TBD</span></span> |
|<span data-ttu-id="882f4-133">チームのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="882f4-133">Team guest access</span></span> |<span data-ttu-id="882f4-134">ゲストがチームに追加されるのを許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="882f4-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="882f4-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="882f4-135">No</span></span> |<span data-ttu-id="882f4-136">TBD</span><span class="sxs-lookup"><span data-stu-id="882f4-136">TBD</span></span> |
|<span data-ttu-id="882f4-137">チームの作成</span><span class="sxs-lookup"><span data-stu-id="882f4-137">Team creation</span></span> |<span data-ttu-id="882f4-138">チームの作成を管理者に限定します。</span><span class="sxs-lookup"><span data-stu-id="882f4-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="882f4-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="882f4-139">No</span></span> |<span data-ttu-id="882f4-140">TBD</span><span class="sxs-lookup"><span data-stu-id="882f4-140">TBD</span></span>|
|<span data-ttu-id="882f4-141">チームの作成</span><span class="sxs-lookup"><span data-stu-id="882f4-141">Team creation</span></span> |<span data-ttu-id="882f4-142">チームの作成をセキュリティ グループのメンバーに限定します。</span><span class="sxs-lookup"><span data-stu-id="882f4-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="882f4-143">P1</span><span class="sxs-lookup"><span data-stu-id="882f4-143">P1</span></span> |<span data-ttu-id="882f4-144">TBD</span><span class="sxs-lookup"><span data-stu-id="882f4-144">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="882f4-145">事前に計画を立てやすくなるために、[これらのポリシーの設定について、およびどのライセンスが必要とされるかについて確認してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="882f4-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="882f4-p103">グループおよびチームの作成を制限すると、多くの Office 365 サービスは、そのサービスが機能するためのグループの作成が必要になり、ユーザーの生産性が低下することがあります。詳細については、「[Office 365 グループの作成ユーザーを制御する理由](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)」に移動して参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="882f4-p103">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function. For additional information, navigate to and expand [Why control who creates Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="882f4-148">追加情報</span><span class="sxs-lookup"><span data-stu-id="882f4-148">Additional information</span></span>

<span data-ttu-id="882f4-p104">要件の決定後、Azure AD のコントロールを使用してその要件を実装できます。これらの設定を実装する方法に関する技術面のガイダンスは、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="882f4-p104">After you’ve determined your requirements, you can implement them by using Azure AD controls. For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="882f4-151">[グループ設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="882f4-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

- <span data-ttu-id="882f4-152">[Azure Active Directory での Office 365 グループの名前付けポリシーの強制](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="882f4-152">[Enforce a naming policy for Office 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

- <span data-ttu-id="882f4-153">[Office 365 グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="882f4-153">[Office 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="882f4-154">グループとチームの有効期限、保持、およびアーカイブ化</span><span class="sxs-lookup"><span data-stu-id="882f4-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="882f4-p105">組織には、有効期限、保持、チームとチームデータ (チャネル メッセージとチャネル ファイル) のアーカイブに関するポリシーの設定に追加の要件がある場合があります。グループの有効期限ポリシーを設定すると、自動でグループポリシーと保持ポリシーを管理して、必要に応じて情報を保存または削除できます。チーム (読み取り専用モードに設定) をアーカイブし、アクティブでなくなったチームのその時のビューを保存します。</span><span class="sxs-lookup"><span data-stu-id="882f4-p105">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files). You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="882f4-158">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="882f4-158">Decision points</span></span>|<ul><li><span data-ttu-id="882f4-159">組織はチームに有効期限日を指定することを必要としていますか?</span><span class="sxs-lookup"><span data-stu-id="882f4-159">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="882f4-160">自分の組織でチームに特定のデータ保持ポリシーを適用する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="882f4-160">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="882f4-161">自分の組織で、コンテンツを読み取り専用の状態で保存するために、非アクティブなチームをアーカイブ化する機能が必要となる見込みはありますか?</span><span class="sxs-lookup"><span data-stu-id="882f4-161">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="882f4-163">次のステップ</span><span class="sxs-lookup"><span data-stu-id="882f4-163">Next steps</span></span>|<ul><li><span data-ttu-id="882f4-164">有効期限、データ保持、アーカイブ化についての組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="882f4-164">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="882f4-165">Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="882f4-165">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="882f4-166">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="882f4-166">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="882f4-167">次の表を使用して、組織の要件を把握します。</span><span class="sxs-lookup"><span data-stu-id="882f4-167">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="882f4-168">機能</span><span class="sxs-lookup"><span data-stu-id="882f4-168">Capability</span></span> |<span data-ttu-id="882f4-169">詳細</span><span class="sxs-lookup"><span data-stu-id="882f4-169">Details</span></span> |<span data-ttu-id="882f4-170">Azure AD Premium ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="882f4-170">Azure AD Premium license required</span></span> |<span data-ttu-id="882f4-171">Decision</span><span class="sxs-lookup"><span data-stu-id="882f4-171">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="882f4-172">有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="882f4-172">Expiration policy</span></span> |<span data-ttu-id="882f4-173">有効期限ポリシーを設定することにより、Office 365 グループのライフ サイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="882f4-173">Manage the lifecycle of Office 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="882f4-174">P1</span><span class="sxs-lookup"><span data-stu-id="882f4-174">P1</span></span> |<span data-ttu-id="882f4-175">TBD</span><span class="sxs-lookup"><span data-stu-id="882f4-175">TBD</span></span>|
|<span data-ttu-id="882f4-176">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="882f4-176">Retention policy</span></span> |<span data-ttu-id="882f4-p106">セキュリティ/コンプライアンス センターで Teams の保持ポリシーを設定して、特定の期間内のデータを保持または削除します。**注:** この機能を使用するには、Office 365 Enterprise E3 以上のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="882f4-p106">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center. **Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="882f4-179">いいえ</span><span class="sxs-lookup"><span data-stu-id="882f4-179">No</span></span> |<span data-ttu-id="882f4-180">TBD</span><span class="sxs-lookup"><span data-stu-id="882f4-180">TBD</span></span> |
|<span data-ttu-id="882f4-181">アーカイブと復元</span><span class="sxs-lookup"><span data-stu-id="882f4-181">Archive and restore</span></span> |<span data-ttu-id="882f4-182">チームがアクティブでなくなったときにチームをアーカイブして、参照用または将来再アクティブ化するために保持します。</span><span class="sxs-lookup"><span data-stu-id="882f4-182">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="882f4-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="882f4-183">No</span></span> |<span data-ttu-id="882f4-184">TBD</span><span class="sxs-lookup"><span data-stu-id="882f4-184">TBD</span></span> |

> [!Note]
> <span data-ttu-id="882f4-p107">グループの有効期限は、Azure AD Premium の機能です。この機能を使えるようにするには、お使いのテナントに、設定と影響を受けるグループのメンバーを構成する管理者の Azure AD Premium とライセンスへのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="882f4-p107">Group expiration is an Azure AD Premium feature. For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="882f4-187">追加情報</span><span class="sxs-lookup"><span data-stu-id="882f4-187">Additional information</span></span>

<span data-ttu-id="882f4-188">これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="882f4-188">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="882f4-189">[Office 365 グループの有効期限をセットアップする](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)</span><span class="sxs-lookup"><span data-stu-id="882f4-189">[Set up Office 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

- <span data-ttu-id="882f4-190">[Teams の保持ポリシーをセットアップする](retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="882f4-190">[Set up Teams retention policies](retention-policies.md).</span></span>

- <span data-ttu-id="882f4-191">[チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="882f4-191">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>


## <a name="teams-feature-management"></a><span data-ttu-id="882f4-192">Teams 機能の管理</span><span class="sxs-lookup"><span data-stu-id="882f4-192">Teams feature management</span></span>

<span data-ttu-id="882f4-p108">Teams のガバナンスとライフ サイクル管理における別の重要な側面は、ユーザーがアクセスできる機能の制御が可能なことです。メッセージング、会議、通話の機能、Office 365 のテナント レベルまたはユーザーごとのいずれかの機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="882f4-p108">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to. You can manage messaging, meeting, and calling features, either at the Office 365 tenant level or per-user.</span></span> 


|         |         |
|---------|---------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="882f4-196">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="882f4-196">Decision points</span></span>|<ul><li><span data-ttu-id="882f4-197">自分の組織で、テナント全体に対して Teams 機能を制限することが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="882f4-197">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="882f4-198">自分の組織で、特定のユーザーに対して Teams 機能を制限することが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="882f4-198">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="882f4-200">次のステップ</span><span class="sxs-lookup"><span data-stu-id="882f4-200">Next steps</span></span>|<ul><li><span data-ttu-id="882f4-201">テナントおよびユーザー レベルで Teams の機能を制限するための組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="882f4-201">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="882f4-202">Teams のロールアウトの一部として、特定の要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="882f4-202">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="882f4-203">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="882f4-203">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="882f4-204">Teams の機能管理での重点領域</span><span class="sxs-lookup"><span data-stu-id="882f4-204">Teams feature management focus areas</span></span>

<span data-ttu-id="882f4-p109">Teams にはポリシーを介して、メッセージング、会議、通話、ライブ イベントの機能などを制御するための詳細な機能が用意されています。既定ではすべてのユーザー、または組織で必要となるユーザーそれぞれに異なるポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="882f4-p109">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies. Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="882f4-207">自分の組織での各設定の実行についての技術的なガイダンスを含む、すべての設定の詳細なリストについては、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="882f4-207">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

- [<span data-ttu-id="882f4-208">組織のMicrosoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="882f4-208">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="882f4-209">新しい Microsoft Teams 管理センターへの移行中に Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="882f4-209">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="882f4-210">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="882f4-210">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="882f4-211">Teams のメッセージング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="882f4-211">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)

<span data-ttu-id="882f4-212">さらに、チャネルのモデレーションを設定し、特定のユーザーに対してモデレーター機能を提供して、チャネルの投稿を作成したり、それらに返信したりできるユーザーを制御できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="882f4-212">Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them.</span></span> <span data-ttu-id="882f4-213">詳細については[、「Microsoft Teams でチャネルのモデレーションを設定および管理](manage-channel-moderation-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="882f4-213">See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) for more information.</span></span>

## <a name="security-and-compliance"></a><span data-ttu-id="882f4-214">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="882f4-214">Security and compliance</span></span>

<span data-ttu-id="882f4-215">Teams は Office 365 の高度なセキュリティおよびコンプライアンス機能に基づいて構築されており、監査および報告、コンプライアンスのコンテンツ検索、電子情報開示、訴訟ホールド、および保持ポリシーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="882f4-215">Teams is built on the advanced security and compliance capabilities of Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span> 

> [!Important]
> <span data-ttu-id="882f4-216">自分の組織でコンプライアンスおよびセキュリティに関する要件がある場合は、「[Microsoft Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」の記事で、このトピックについての掘り下げた内容を確認してください。</span><span class="sxs-lookup"><span data-stu-id="882f4-216">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
