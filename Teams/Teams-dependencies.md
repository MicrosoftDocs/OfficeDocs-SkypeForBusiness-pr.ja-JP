---
title: Microsoft Teams でのゲスト アクセスを承認する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理します。
ms.openlocfilehash: 40bc8c68ac3f1ad3117fa47aa0aad5f14ff3be69
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030993"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="179f4-103">Microsoft Teams でのゲスト アクセスを承認する</span><span class="sxs-lookup"><span data-stu-id="179f4-103">Authorize guest access in Microsoft Teams</span></span>

<span data-ttu-id="179f4-104">組織の要件を満たすために、Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理することができます。</span><span class="sxs-lookup"><span data-stu-id="179f4-104">To satisfy your organization's requirements, you can manage Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="179f4-105">すべての承認レベルが Microsoft 365 組織に適用されます。</span><span class="sxs-lookup"><span data-stu-id="179f4-105">All the authorization levels apply to your Microsoft 365 organization.</span></span> <span data-ttu-id="179f4-106">それぞれの承認レベルによって、ゲストのエクスペリエンスが次の通り制御されます。</span><span class="sxs-lookup"><span data-stu-id="179f4-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="179f4-107">**Azure Active Directory**: Teams のゲスト アクセスは、Azure Active Directory ビジネス ツー ビジネス (B2B) プラットフォームに依存します。</span><span class="sxs-lookup"><span data-stu-id="179f4-107">**Azure Active Directory**: Guest access in Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="179f4-108">この承認レベルは、ゲストのエクスペリエンスをディレクトリ、テナント、およびアプリケーション レベルで制御します。</span><span class="sxs-lookup"><span data-stu-id="179f4-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="179f4-109">**Teams**: Teams のゲストエクスペリエンスのみを管理します。</span><span class="sxs-lookup"><span data-stu-id="179f4-109">**Teams**: Controls the guest experience in Teams only.</span></span>
- <span data-ttu-id="179f4-110">**Microsoft 365 グループ**: Microsoft 365 グループおよび Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="179f4-110">**Microsoft 365 Groups**: Controls the guest experience in Microsoft 365 Groups and Teams.</span></span>
- <span data-ttu-id="179f4-111">**SharePoint と OneDrive**: SharePoint、OneDrive、Microsoft 365 グループ、およびチームのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="179f4-111">**SharePoint and OneDrive**: Controls the guest experience in SharePoint, OneDrive, Microsoft 365 Groups, and Teams.</span></span>

<span data-ttu-id="179f4-112">これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="179f4-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="179f4-113">たとえば、自分の Microsoft Teams でゲスト ユーザーを許可せず、組織全体では許可する場合、Microsoft Teams でゲスト アクセスをオフにするだけです。</span><span class="sxs-lookup"><span data-stu-id="179f4-113">For example, if you don't want to allow guest users in Teams but want to allow it overall in your organization, just turn off guest access in Teams.</span></span> <span data-ttu-id="179f4-114">別の例: Azure AD、Teams、Groups レベルでゲスト アクセスを有効にしつつ、[1 つ以上の基準 (データ分類が社外秘に等しいなど) に一致する選択したチームに対するゲスト ユーザーの追加を無効にする](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)ことができます。</span><span class="sxs-lookup"><span data-stu-id="179f4-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then [disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="179f4-115">SharePoint と OneDrive には、Microsoft 365 グループに依存しない独自のゲスト アクセス設定があります。</span><span class="sxs-lookup"><span data-stu-id="179f4-115">SharePoint and OneDrive have their own guest access settings that don't rely on Microsoft 365 Groups.</span></span>

<span data-ttu-id="179f4-116">エンドツーエンドのゲスト アクセス設定手順については、「[チームでゲストと共同で作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="179f4-116">For end-to-end guest access configuration instructions, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

> [!NOTE]
> <span data-ttu-id="179f4-117">ゲストは、「[Microsoft 365 および Office 365 サービスの説明](https://go.microsoft.com/fwlink/p/?linkid=282347)」および「[Azure AD B2B コラボレーションの制限での制限](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)」に記載されているサービスの制限の対象となります。</span><span class="sxs-lookup"><span data-stu-id="179f4-117">Guests are subject to the service limits described in [Microsoft 365 and Office 365 service descriptions](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Limitations of Azure AD B2B collaboration](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations).</span></span> 

<span data-ttu-id="179f4-118">次の図では、Azure Active Directory、Teams、および Microsoft 365 との間でゲスト アクセスの承認の依存関係がどのように与えられているか、および組み合わされているかを示します。</span><span class="sxs-lookup"><span data-stu-id="179f4-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Teams, and Microsoft 365.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="179f4-119">![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)</span><span class="sxs-lookup"><span data-stu-id="179f4-119">![Diagram of authorization dependencies for guest access.](media/teams_dependencies_image1.png)</span></span>

<span data-ttu-id="179f4-120">次の図は、一般的なゲスト アクセスの招待と引き換えフローを通じて、ユーザーの作業環境がアクセス許可モデルとどのように連動するかを大まかに示しています。</span><span class="sxs-lookup"><span data-stu-id="179f4-120">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="179f4-121">![招待と引き換えフローの図](media/authorize-guest-image1.png)</span><span class="sxs-lookup"><span data-stu-id="179f4-121">![Diagram of invitation and redemption flows](media/authorize-guest-image1.png)</span></span>

<span data-ttu-id="179f4-122">ここで重要なことは、アプリ、ボット、コネクタが独自のアクセス許可のセットや、ユーザー アカウントに固有の同意が必要な可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="179f4-122">It's important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="179f4-123">それぞれに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="179f4-123">These might need to be granted separately.</span></span> <span data-ttu-id="179f4-124">同様に SharePoint は、特定のユーザー、ユーザーのグループ、またはサイト レベルであっても、外部共有の境界を追加することがあります。</span><span class="sxs-lookup"><span data-stu-id="179f4-124">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="179f4-125">上の 2 つの図は、[Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) でも同じように利用することができます。</span><span class="sxs-lookup"><span data-stu-id="179f4-125">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="179f4-126">Azure Active Directory のゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="179f4-126">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="179f4-127">Azure AD を使用し、外部の共同作業者をゲストとして、どんな方法で、テナントに招待できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="179f4-127">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="179f4-128">Azure B2B のゲスト アクセスの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="179f4-128">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="179f4-129">Azure AD の役割に関する詳細については、「[Azure Active Directory テナントでパートナー組織からユーザーにアクセス許可を付与する](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="179f4-129">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="179f4-130">招待の設定は、組織レベルで適用され、ディレクトリ、アプリケーション レベルでゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="179f4-130">The settings for invitations apply at the organization level and control the guest experience at the directory and application level.</span></span> <span data-ttu-id="179f4-131">これらの設定は、[外部コラボレーション設定](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)で構成できます。</span><span class="sxs-lookup"><span data-stu-id="179f4-131">You can configure these settings in [External collaboration settings](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).</span></span>

<span data-ttu-id="179f4-132">Azure AD には、外部ユーザーを構成する次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="179f4-132">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="179f4-133">[[ゲスト ユーザー アクセスの制限]](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)</span><span class="sxs-lookup"><span data-stu-id="179f4-133">[Guest user access restrictions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)</span></span>

- <span data-ttu-id="179f4-134">[**管理者とゲスト招待元ロールのユーザーが招待可能**]: [**はい**] の場合、管理者およびゲスト招待元ロールのユーザーがテナントにゲストを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="179f4-134">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="179f4-135">[**いいえ**] の場合、管理者およびユーザーはゲストをテナントに招待できません。</span><span class="sxs-lookup"><span data-stu-id="179f4-135">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="179f4-136">[**メンバーが招待可能**]: ディレクトリの管理者以外のメンバーがゲストを招待できるようにするには、このポリシーを [**はい**] に設定します (推奨)。</span><span class="sxs-lookup"><span data-stu-id="179f4-136">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="179f4-137">管理者だけがゲストを追加できるようにする場合は、このポリシーを [**いいえ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="179f4-137">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="179f4-138">[**いいえ**] に設定すると、管理者以外の Teams 所有者のゲスト エクスペリエンスが制限され、管理者により AAD に追加されたゲストだけを Teams に追加できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="179f4-138">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
- <span data-ttu-id="179f4-139">[**ゲストが招待可能**]: [**はい**] の場合、自分のディレクトリ内のゲストは他のゲストを招待して、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどでそれらのゲストと共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="179f4-139">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="179f4-140">[**いいえ**] の場合、組織と共同作業を行う他のゲストをゲストが招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="179f4-140">**No** means that guests can't invite other guests to collaborate with your organization.</span></span> <span data-ttu-id="179f4-141">**[はい]** に設定されている場合でも、ゲストはチームの他のゲストを招待できません。</span><span class="sxs-lookup"><span data-stu-id="179f4-141">Even if set to **Yes**, guest cannot invite other guests in Teams.</span></span>
 
<span data-ttu-id="179f4-142">ゲストを招待できるユーザーの制御の詳細については、「[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザー管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="179f4-142">For more information about controlling who can invite guests, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="179f4-143">どのドメインをゲストとしてテナントに招待できるかを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="179f4-143">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="179f4-144">「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="179f4-144">See [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list).</span></span>

<span data-ttu-id="179f4-145">ユーザー ゲスト アカウントを手動で Azure AD B2B に追加する必要はありません。ゲストを Teams に追加すると、アカウントは自動的にディレクトリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="179f4-145">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="179f4-146">ゲスト アクセスのライセンス</span><span class="sxs-lookup"><span data-stu-id="179f4-146">Licensing for guest access</span></span>

<span data-ttu-id="179f4-147">ゲスト アクセス ライセンスは、Azure AD External Identities の料金を使用し、毎月のアクティブ ゲストに基づいています。</span><span class="sxs-lookup"><span data-stu-id="179f4-147">Guest access licensing uses Azure AD External Identities pricing and is based on monthly active guests.</span></span> <span data-ttu-id="179f4-148">「[Azure AD External Identities の課金モデル](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="179f4-148">See [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) for details.</span></span>

> [!NOTE]
> <span data-ttu-id="179f4-149">Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。</span><span class="sxs-lookup"><span data-stu-id="179f4-149">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="179f4-150">これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="179f4-150">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="179f4-151">外部アクセス (フェデレーション) とゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="179f4-151">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="179f4-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="179f4-152">Related topics</span></span>

- [<span data-ttu-id="179f4-153">Microsoft 365 ゲストの共有設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="179f4-153">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[<span data-ttu-id="179f4-154">Microsoft 365 とセキュリティで保護された共同作業を設定する</span><span class="sxs-lookup"><span data-stu-id="179f4-154">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
