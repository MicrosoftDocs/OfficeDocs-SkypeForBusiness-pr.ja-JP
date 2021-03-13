---
title: Teams でのガバナンスを計画する - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: この記事では、Teams でのガバナンス機能の実装を計画する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38e51b85e7ecf8efc61c6ca78ca16e4366372885
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756233"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="13b29-103">Teams でのガバナンスを計画する</span><span class="sxs-lookup"><span data-stu-id="13b29-103">Plan for governance in Teams</span></span>

<span data-ttu-id="13b29-p101">Teams には組織が必要とする可能性のあるガバナンス機能を実装するための豊富なツールセットが用意されています。この記事では、IT プロフェッショナルが、ガバナンスに関する組織の要件と、その要件を満たす方法を判断する際に適切な質問をするためのガイドを示します。</span><span class="sxs-lookup"><span data-stu-id="13b29-p101">Teams provides a rich set of tools to implement any governance capabilities your organization might require. This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="13b29-106">Microsoft Teams でのガバナンスの詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="13b29-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="13b29-107">グループおよびチームの作成、名前付け、分類、およびゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="13b29-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="13b29-108">自分の組織において、チームの命名や分類について、ゲストがチーム メンバーとして追加することができるかどうかについて、およびチームを作成することができるユーザーが誰であるかについて、厳密な制御を実施する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13b29-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="13b29-109">これらの領域を構成するには、Azure Active Directory (Azure AD) と感度ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="13b29-109">You can configure these areas by using Azure Active Directory (Azure AD) and sensitivity labels.</span></span> 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="13b29-110">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="13b29-110">Decision points</span></span>|<ul><li><span data-ttu-id="13b29-111">自分の組織において、チームについての特定の名前付け規則はありますか?</span><span class="sxs-lookup"><span data-stu-id="13b29-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="13b29-112">チーム作成者は組織固有の分類をチームに割り当てる機能を必要としていますか?</span><span class="sxs-lookup"><span data-stu-id="13b29-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="13b29-113">チームにゲストを追加する機能を、チーム単位で制限する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="13b29-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="13b29-114">自分の組織において、チームを作成可能なユーザーを制限する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="13b29-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="13b29-115">次の手順</span><span class="sxs-lookup"><span data-stu-id="13b29-115">Next steps</span></span>|<ul><li><span data-ttu-id="13b29-116">チームの作成、名前付け、分類、およびゲスト アクセスについて、自分の組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="13b29-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="13b29-117">Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="13b29-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="13b29-118">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="13b29-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!NOTE]
> <span data-ttu-id="13b29-119">事前に計画を立てやすくなるために、[これらのポリシーの設定について、およびどのライセンスが必要とされるかについて確認してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="13b29-119">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="13b29-120">多くの Microsoft 365 および Office 365 サービスでは、サービスを機能するためにグループを作成する必要があるため、グループとチームの作成を制限すると、ユーザーの生産性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13b29-120">Limiting group and team creation can slow your users’ productivity, because many Microsoft 365 and Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="13b29-121">詳細については [、Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)グループを作成するユーザーを制御する理由に移動して展開します。</span><span class="sxs-lookup"><span data-stu-id="13b29-121">For additional information, navigate to and expand [Why control who creates Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="13b29-122">追加情報</span><span class="sxs-lookup"><span data-stu-id="13b29-122">Additional information</span></span>

<span data-ttu-id="13b29-p104">要件の決定後、Azure AD のコントロールを使用してその要件を実装できます。これらの設定を実装する方法に関する技術面のガイダンスは、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13b29-p104">After you’ve determined your requirements, you can implement them by using Azure AD controls. For technical guidance on how to implement these settings, see:</span></span>

- [<span data-ttu-id="13b29-125">グループ設定を構成するための Azure Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="13b29-125">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [<span data-ttu-id="13b29-126">Azure Active Directory で Microsoft 365 グループに名前付けポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="13b29-126">Enforce a naming policy for Microsoft 365 groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [<span data-ttu-id="13b29-127">Microsoft 365 グループの名前付けポリシー</span><span class="sxs-lookup"><span data-stu-id="13b29-127">Microsoft 365 Groups naming policy</span></span>](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [<span data-ttu-id="13b29-128">Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護するために感度ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="13b29-128">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [<span data-ttu-id="13b29-129">グループ、チーム、およびグループのライフサイクルのYammer</span><span class="sxs-lookup"><span data-stu-id="13b29-129">End of lifecycle options for groups, teams, and Yammer</span></span>](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="13b29-130">グループとチームの有効期限、保持、およびアーカイブ化</span><span class="sxs-lookup"><span data-stu-id="13b29-130">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="13b29-131">自分の組織で、有効期限、保持、チームおよびチームのデータ (チャネルのメッセージとチャネルのファイル) をアーカイブ化することについてのポリシーを設定するための追加の要件がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13b29-131">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="13b29-132">グループの有効期限ポリシーを構成して、グループのライフサイクルや、必要に応じて情報の保存や削除を行うための保持ポリシーを自動的に管理することができます。また、チームをアーカイブ化して (読み取り専用モードに設定して)、アクティブでなくなったチームについて特定の時点の表示を保存することができます。</span><span class="sxs-lookup"><span data-stu-id="13b29-132">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span> <span data-ttu-id="13b29-133">アーカイブされたチームには引き続き有効期限ポリシーが適用され、除外または更新されていない限り削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13b29-133">Note that teams that are archived continue to have the expiration policy applied and may be deleted unless excluded or renewed.</span></span>

|-          |-           |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="13b29-135">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="13b29-135">Decision points</span></span>|<ul><li><span data-ttu-id="13b29-136">組織はチームに有効期限日を指定することを必要としていますか?</span><span class="sxs-lookup"><span data-stu-id="13b29-136">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="13b29-137">自分の組織でチームに特定のデータ保持ポリシーを適用する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="13b29-137">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="13b29-138">自分の組織で、コンテンツを読み取り専用の状態で保存するために、非アクティブなチームをアーカイブ化する機能が必要となる見込みはありますか?</span><span class="sxs-lookup"><span data-stu-id="13b29-138">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="13b29-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="13b29-140">Next steps</span></span>|<ul><li><span data-ttu-id="13b29-141">有効期限、データ保持、アーカイブ化についての組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="13b29-141">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="13b29-142">Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="13b29-142">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="13b29-143">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="13b29-143">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="13b29-144">次の表を使用して、組織の要件を把握します。</span><span class="sxs-lookup"><span data-stu-id="13b29-144">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="13b29-145">機能</span><span class="sxs-lookup"><span data-stu-id="13b29-145">Capability</span></span> |<span data-ttu-id="13b29-146">詳細</span><span class="sxs-lookup"><span data-stu-id="13b29-146">Details</span></span> |<span data-ttu-id="13b29-147">Azure AD Premium ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="13b29-147">Azure AD Premium license required</span></span> |<span data-ttu-id="13b29-148">Decision</span><span class="sxs-lookup"><span data-stu-id="13b29-148">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="13b29-149">有効期限ポリシー</span><span class="sxs-lookup"><span data-stu-id="13b29-149">Expiration policy</span></span> |<span data-ttu-id="13b29-150">有効期限ポリシーを設定して、Microsoft 365 グループのライフサイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="13b29-150">Manage the lifecycle of Microsoft 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="13b29-151">P1</span><span class="sxs-lookup"><span data-stu-id="13b29-151">P1</span></span> |<span data-ttu-id="13b29-152">TBD</span><span class="sxs-lookup"><span data-stu-id="13b29-152">TBD</span></span>|
|<span data-ttu-id="13b29-153">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="13b29-153">Retention policy</span></span> |<span data-ttu-id="13b29-154">セキュリティ/コンプライアンス センター内で Teams の保持ポリシーを設定することによって特定の期間におけるデータを保持または削除します。</span><span class="sxs-lookup"><span data-stu-id="13b29-154">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="13b29-155">**注**: この機能を使用するには、Microsoft 365 または Office 365 Enterprise E3 以上のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="13b29-155">**Note**: Using this feature requires licensing of Microsoft 365 or Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="13b29-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="13b29-156">No</span></span> |<span data-ttu-id="13b29-157">TBD</span><span class="sxs-lookup"><span data-stu-id="13b29-157">TBD</span></span> |
|<span data-ttu-id="13b29-158">アーカイブと復元</span><span class="sxs-lookup"><span data-stu-id="13b29-158">Archive and restore</span></span> |<span data-ttu-id="13b29-159">チームがアクティブでなくなったときにチームをアーカイブして、参照用または将来再アクティブ化するために保持します。</span><span class="sxs-lookup"><span data-stu-id="13b29-159">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="13b29-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="13b29-160">No</span></span> |<span data-ttu-id="13b29-161">TBD</span><span class="sxs-lookup"><span data-stu-id="13b29-161">TBD</span></span> |

> [!Note]
> <span data-ttu-id="13b29-p107">グループの有効期限は、Azure AD Premium の機能です。この機能を使えるようにするには、お使いのテナントに、設定と影響を受けるグループのメンバーを構成する管理者の Azure AD Premium とライセンスへのサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="13b29-p107">Group expiration is an Azure AD Premium feature. For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="13b29-164">追加情報</span><span class="sxs-lookup"><span data-stu-id="13b29-164">Additional information</span></span>

<span data-ttu-id="13b29-165">これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13b29-165">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="13b29-166">[Microsoft 365 グループの有効期限を設定します](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)。</span><span class="sxs-lookup"><span data-stu-id="13b29-166">[Set up Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

- <span data-ttu-id="13b29-167">[Teams の保持ポリシーをセットアップする](retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="13b29-167">[Set up Teams retention policies](retention-policies.md).</span></span>

- <span data-ttu-id="13b29-168">[チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="13b29-168">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>

## <a name="group-and-team-membership-management"></a><span data-ttu-id="13b29-169">グループとチームのメンバーシップ管理</span><span class="sxs-lookup"><span data-stu-id="13b29-169">Group and team membership management</span></span>

<span data-ttu-id="13b29-170">迅速なオンボーディングとオフボーディングが必要なチーム、またはユーザーとゲストには、プロジェクト ベースのグループまたは制限付きグループのメンバーを一貫して管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13b29-170">Consistently managing members of project based, or restricted groups are necessary for teams that require rapid onboarding and offboarding or users and guests.</span></span> <span data-ttu-id="13b29-171">また、組織では、現在のすべてのメンバーがチーム内に業務上の正当な理由を持っている必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="13b29-171">Your organization may also need to make sure all current members have the business justification to be in a team.</span></span> <span data-ttu-id="13b29-172">メンバーの管理は、チーム所有者が離れ、通常、プロジェクトが終了したり役割を変更したりするときに、ユーザーが自らグループを離れないので、難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="13b29-172">Managing members can be hard because team owners can leave and users don’t usually leave groups on their own accord when a project ends or when they change roles.</span></span> <span data-ttu-id="13b29-173">必要に応じてユーザーがアクセスできるが、グループに不適切なアクセスのリスクが生じなかったグループ メンバーシップを管理する最適な方法は、資格管理とアクセスレビューの 2 つの地区プロセスを通じて行う方法です。</span><span class="sxs-lookup"><span data-stu-id="13b29-173">The best way to manage group membership that allows users to get access when needed but ensure the group doesn't have a risk of inappropriate access is through two district processes: entitlement management and access reviews.</span></span>

<span data-ttu-id="13b29-174">[資格管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) を使用すると、プロジェクト マネージャーなどの誰かに委任して、チームのメンバーシップを含む必要なすべてのリソースを 1 つのパッケージに収集できます。</span><span class="sxs-lookup"><span data-stu-id="13b29-174">[Entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) allows you to delegate to someone, such as a project manager, to collect all the resources that are needed, including teams memberships, into a single package.</span></span> <span data-ttu-id="13b29-175">また、要求を行えるユーザー (テナント内のユーザーまたは他の接続されている組織からのユーザー) を定義できます。</span><span class="sxs-lookup"><span data-stu-id="13b29-175">They can also define who can make requests: either users in your tenant or from other connected organizations.</span></span> <span data-ttu-id="13b29-176">プロジェクト マネージャーは、メールでアクセス要求を受信し、MyAccess ポータルで要求を承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="13b29-176">The project manager will receive access requests in their email and approve or deny requests in the MyAccess portal.</span></span> <span data-ttu-id="13b29-177">管理者は、アクセスが更新されていない限り、ユーザーまたはゲストがチームから削除される期限の日付または期間を含めるアクセスの条件を構成できます。</span><span class="sxs-lookup"><span data-stu-id="13b29-177">Administrators can configure the conditions of access to include an expiry date or period by when the user or guest will be removed from the team unless access is renewed.</span></span> <span data-ttu-id="13b29-178">管理者は、チームに関連付けられているグループを設定して、アクセスレビューに参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="13b29-178">Administrators can also set up the groups associated with teams to take part in access reviews.</span></span> <span data-ttu-id="13b29-179">アクセス [のレビューでは、](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)グループの所有者は、チームのメンバーをレビューする定期的なアラームを受け取る予定です。</span><span class="sxs-lookup"><span data-stu-id="13b29-179">For [access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview), the group owners will receive regular reminders to review the members of a team.</span></span> <span data-ttu-id="13b29-180">Access のレビューには推奨事項が含まれるので、グループ所有者は通常の構成証明プロセスを簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="13b29-180">Access reviews include recommendations, which makes it easier for group owners to go through their regular attestation process.</span></span>

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | <span data-ttu-id="13b29-181">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="13b29-181">Decision points</span></span> | <span data-ttu-id="13b29-182">組織では、1 つ以上のチームのメンバーシップを管理するための一貫したプロセスが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="13b29-182">Does your organization require a consistent process for managing membership of one or more teams?</span></span> <br> <span data-ttu-id="13b29-183">組織では、定期的に 1 つ以上のチームの継続的なメンバーシップを正当化するために、所有者またはメンバー自身が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="13b29-183">Does your organization require owners, or the members themselves, to justify their continued membership of one or more teams on a regular basis?</span></span> <br> <span data-ttu-id="13b29-184">組織では、チーム、グループ、SharePoint サイト、アプリなどのリソースへのアクセスを要求するために、ユーザーとゲストの承認が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="13b29-184">Does your organization require approval for users and guests to request access to resources including teams, groups, SharePoint sites, and apps?</span></span> |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| <span data-ttu-id="13b29-185">次の手順</span><span class="sxs-lookup"><span data-stu-id="13b29-185">Next steps?</span></span> | <span data-ttu-id="13b29-186">各チームまたは特定のチームのメンバーシップの有効期限が切れている組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="13b29-186">Document your organizations requirements for each team or specific teams for membership expiry.</span></span><br><span data-ttu-id="13b29-187">チーム、グループ、SharePoint サイト、アプリをアクセス パッケージにまとめてバンドルする方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="13b29-187">Plan how your organization can bundle teams, groups, SharePoint sites, and apps together in access packages.</span></span><br><span data-ttu-id="13b29-188">要求者のマネージャー、プロジェクト マネージャー、接続されている組織のスポンサー、組織内のセキュリティ責任者など、アクセス要求を承認または拒否する必要があるユーザーを計画します。</span><span class="sxs-lookup"><span data-stu-id="13b29-188">Plan which people, such as the requestor's manager, a project manager, a sponsor for a connected organization or a security officer in your organization will need to approve or deny access requests.</span></span> |

> [!TIP]
> <span data-ttu-id="13b29-189">次の表を使用して、組織の要件を把握します。</span><span class="sxs-lookup"><span data-stu-id="13b29-189">Use the following table to capture your organization’s requirements.</span></span>

| <span data-ttu-id="13b29-190">機能</span><span class="sxs-lookup"><span data-stu-id="13b29-190">Capability</span></span> | <span data-ttu-id="13b29-191">詳細</span><span class="sxs-lookup"><span data-stu-id="13b29-191">Details</span></span> | <span data-ttu-id="13b29-192">Azure AD Premium ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="13b29-192">Azure AD Premium license required</span></span> | <span data-ttu-id="13b29-193">Decision</span><span class="sxs-lookup"><span data-stu-id="13b29-193">Decision</span></span> |
|:-|:-|:-|:-|
| <span data-ttu-id="13b29-194">Access のレビュー</span><span class="sxs-lookup"><span data-stu-id="13b29-194">Access reviews</span></span> | <span data-ttu-id="13b29-195">アクセスレビューを設定して一定の間隔で特定のチームのメンバーシップを再認定する</span><span class="sxs-lookup"><span data-stu-id="13b29-195">Setup access reviews to recertify the membership of specific teams at regular interval</span></span> | <span data-ttu-id="13b29-196">P2</span><span class="sxs-lookup"><span data-stu-id="13b29-196">P2</span></span> | <span data-ttu-id="13b29-197">TBD</span><span class="sxs-lookup"><span data-stu-id="13b29-197">TBD</span></span> |
| <span data-ttu-id="13b29-198">資格管理</span><span class="sxs-lookup"><span data-stu-id="13b29-198">Entitlement management</span></span> | <span data-ttu-id="13b29-199">ユーザーとゲストがチームへのアクセスを要求できるアクセス パッケージをセットアップする</span><span class="sxs-lookup"><span data-stu-id="13b29-199">Setup access package to allow users and guests to request access to teams</span></span> | <span data-ttu-id="13b29-200">P2</span><span class="sxs-lookup"><span data-stu-id="13b29-200">P2</span></span> | <span data-ttu-id="13b29-201">TBD</span><span class="sxs-lookup"><span data-stu-id="13b29-201">TBD</span></span> |

> [!NOTE]
> <span data-ttu-id="13b29-202">前もって計画を立てるには、 [必要なライセンスの詳細を確認してください](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="13b29-202">To help you plan ahead, [learn more about what licenses they require](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="additional-information"></a><span data-ttu-id="13b29-203">追加情報</span><span class="sxs-lookup"><span data-stu-id="13b29-203">Additional information</span></span>

<span data-ttu-id="13b29-204">これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13b29-204">For technical guidance on how to implement these settings, see:</span></span>

- [<span data-ttu-id="13b29-205">資格管理</span><span class="sxs-lookup"><span data-stu-id="13b29-205">Entitlement management</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [<span data-ttu-id="13b29-206">Access のレビュー</span><span class="sxs-lookup"><span data-stu-id="13b29-206">Access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a><span data-ttu-id="13b29-207">Teams 機能の管理</span><span class="sxs-lookup"><span data-stu-id="13b29-207">Teams feature management</span></span>

<span data-ttu-id="13b29-208">Teams でのガバナンスおよびライフサイクル管理のもう 1 つの重要な側面として、自分たちのユーザーがどの機能にアクセスするかを制御する機能があります。</span><span class="sxs-lookup"><span data-stu-id="13b29-208">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="13b29-209">メッセージング、会議、通話の機能は、Microsoft 365 または Office 365 組織レベルまたはユーザーごとに管理できます。</span><span class="sxs-lookup"><span data-stu-id="13b29-209">You can manage messaging, meeting, and calling features, either at the Microsoft 365 or Office 365 organization level or per-user.</span></span>


|-        |-        |
|---------|---------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/><span data-ttu-id="13b29-211">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="13b29-211">Decision points</span></span>|<ul><li><span data-ttu-id="13b29-212">自分の組織で、テナント全体に対して Teams 機能を制限することが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="13b29-212">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="13b29-213">自分の組織で、特定のユーザーに対して Teams 機能を制限することが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="13b29-213">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/><span data-ttu-id="13b29-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="13b29-215">Next steps</span></span>|<ul><li><span data-ttu-id="13b29-216">テナントおよびユーザー レベルで Teams の機能を制限するための組織の要件を文書化します。</span><span class="sxs-lookup"><span data-stu-id="13b29-216">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="13b29-217">Teams のロールアウトの一部として、特定の要件を実施する計画を立てます。</span><span class="sxs-lookup"><span data-stu-id="13b29-217">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="13b29-218">ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</span><span class="sxs-lookup"><span data-stu-id="13b29-218">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="13b29-219">Teams の機能管理での重点領域</span><span class="sxs-lookup"><span data-stu-id="13b29-219">Teams feature management focus areas</span></span>

<span data-ttu-id="13b29-p111">Teams にはポリシーを介して、メッセージング、会議、通話、ライブ イベントの機能などを制御するための詳細な機能が用意されています。既定ではすべてのユーザー、または組織で必要となるユーザーそれぞれに異なるポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="13b29-p111">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies. Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="13b29-222">自分の組織での各設定の実行についての技術的なガイダンスを含む、すべての設定の詳細なリストについては、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13b29-222">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

- [<span data-ttu-id="13b29-223">組織のMicrosoft Teams の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="13b29-223">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="13b29-224">新しい Microsoft Teams 管理センターへの移行中に Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="13b29-224">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="13b29-225">Microsoft Teams のプライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="13b29-225">Private channels in Microsoft Teams</span></span>](private-channels.md)
- [<span data-ttu-id="13b29-226">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="13b29-226">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="13b29-227">Teams のメッセージング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="13b29-227">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
- [<span data-ttu-id="13b29-228">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="13b29-228">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)

<span data-ttu-id="13b29-229">また、チャネルのモデレートを設定し、特定のユーザーにモデレーター機能を与え、チャネル投稿を作成してそれに応答できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="13b29-229">Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them.</span></span> <span data-ttu-id="13b29-230">詳細 [については、「Microsoft Teams でのチャネル](manage-channel-moderation-in-teams.md) モデレートの設定と管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13b29-230">See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) for more information.</span></span>

## <a name="security-and-compliance"></a><span data-ttu-id="13b29-231">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="13b29-231">Security and compliance</span></span>

<span data-ttu-id="13b29-232">Teams は、Microsoft 365 および Office 365 の高度なセキュリティとコンプライアンス機能の上に構築され、監査とレポート、コンプライアンス コンテンツ検索、電子検出、法的保持、アイテム保持ポリシーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="13b29-232">Teams is built on the advanced security and compliance capabilities of Microsoft 365 and Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span>

> [!Important]
> <span data-ttu-id="13b29-233">自分の組織でコンプライアンスおよびセキュリティに関する要件がある場合は、「[Microsoft Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」の記事で、このトピックについての掘り下げた内容を確認してください。</span><span class="sxs-lookup"><span data-stu-id="13b29-233">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="13b29-234">関連トピック</span><span class="sxs-lookup"><span data-stu-id="13b29-234">Related topics</span></span>

[<span data-ttu-id="13b29-235">Teams のガバナンスのクイック スタート</span><span class="sxs-lookup"><span data-stu-id="13b29-235">Governance quick start for Teams</span></span>](teams-adoption-governance-quick-start.md)

[<span data-ttu-id="13b29-236">セキュリティとコンプライアンスに関する Microsoft 365 &ガイダンス</span><span class="sxs-lookup"><span data-stu-id="13b29-236">Microsoft 365 licensing guidance for security & compliance</span></span>](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
