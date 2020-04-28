---
title: Microsoft Teams でのゲスト アクセスを承認する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 848db9ea517876d941e837eaff34e72e0cff9c2a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778483"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="d3fd5-103">Microsoft Teams でのゲスト アクセスを承認する</span><span class="sxs-lookup"><span data-stu-id="d3fd5-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="d3fd5-104">組織の要件を満たすために、Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="d3fd5-105">すべての承認レベルが Office 365 組織に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-105">All the authorization levels apply to your Office 365 organization.</span></span> <span data-ttu-id="d3fd5-106">それぞれの承認レベルによって、ゲストのエクスペリエンスが次の通り制御されます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="d3fd5-107">**Azure Active Directory**: Microsoft Teams のゲスト アクセスは、Azure Active Directory ビジネス ツー ビジネス (B2B) プラットフォームに依存します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="d3fd5-108">この承認レベルは、ゲストのエクスペリエンスをディレクトリ、テナント、およびアプリケーション レベルで制御します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="d3fd5-109">**Microsoft Teams**: Microsoft Teams のゲストエクスペリエンスのみを管理します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-109">**Microsoft Teams**: Controls the guest experience in Microsoft Teams only.</span></span>
- <span data-ttu-id="d3fd5-110">**Microsoft 365 グループ**: Microsoft 365 グループおよび Microsoft Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-110">**Microsoft 365 Groups**: Controls the guest experience in Microsoft 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="d3fd5-111">**SharePoint Online と OneDrive for Business**: SharePoint Online、OneDrive for Business、Microsoft 365 グループ、および Microsoft Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Microsoft 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="d3fd5-112">これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="d3fd5-113">たとえば、自分の Microsoft Teams でゲスト ユーザーを許可せず、組織全体では許可する場合、Microsoft Teams でゲスト アクセスをオフにするだけです。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="d3fd5-114">別の例: Azure AD、Teams、Groups レベルでゲスト アクセスを有効にしつつ、1 つ以上の基準 (データ分類が社外秘に等しいなど) に一致する選択したチームに対するゲスト ユーザーの追加を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="d3fd5-115">SharePoint Online と OneDrive for Business には、Microsoft 365 グループに依存しない独自のゲスト アクセス設定があります。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Microsoft 365 Groups.</span></span>

> [!NOTE]
> <span data-ttu-id="d3fd5-116">ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-116">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

<span data-ttu-id="d3fd5-117">次の図では、Azure Active Directory、Microsoft Teams、および Office 365 との間でゲスト アクセスの承認の依存関係がどのように与えられているか、および組み合わされているかを示します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>

![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)

<span data-ttu-id="d3fd5-119">次の図は、一般的なゲスト アクセスの招待と引き換えフローを通じて、ユーザーの作業環境がアクセス許可モデルとどのように連動するかを大まかに示しています。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![招待と引き換えフローの図](media/authorize-guest-image1.png)

<span data-ttu-id="d3fd5-121">ここで重要なことは、アプリ、ボット、コネクタが独自のアクセス許可のセットや、ユーザー アカウントに固有の同意が必要な可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="d3fd5-122">それぞれに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-122">These might need to be granted separately.</span></span> <span data-ttu-id="d3fd5-123">同様に SharePoint は、特定のユーザー、ユーザーのグループ、またはサイト レベルであっても、外部共有の境界を追加することがあります。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="d3fd5-124">上の 2 つの図は、[Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) でも同じように利用することができます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-124">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="d3fd5-125">Azure Active Directory のゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="d3fd5-125">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="d3fd5-126">Azure AD を使用し、外部の共同作業者をゲストとして、どんな方法で、テナントに招待できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-126">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="d3fd5-127">Azure B2B のゲスト アクセスの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-127">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="d3fd5-128">Azure AD の役割に関する詳細については、「[Azure Active Directory テナントでパートナー組織からユーザーにアクセス許可を付与する](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-128">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="d3fd5-129">招待の設定は、テナント レベルで適用され、ディレクトリ、テナント、アプリケーション レベルでゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-129">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="d3fd5-130">Azure portal でこの設定を構成するには、**[Azure Active Directory]** > **[ユーザー]** > **[ユーザー設定]** の順に移動し、**[外部ユーザー]** で **[外部コラボレーションの設定を管理します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-130">To configure these settings in the Azure portal, go to **Azure Active Directory** > **Users** > **User settings**, and under **External users**, select **Manage external collaboration settings**.</span></span>

<span data-ttu-id="d3fd5-131">Azure AD には、外部ユーザーを構成する次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-131">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="d3fd5-132">[**ゲスト ユーザーのアクセス権を制限**]: [**はい**] の場合、ゲストにはユーザー、グループ、その他のディレクトリ リソースの列挙などの特定のディレクトリのタスクに対するアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-132">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="d3fd5-133">また、自分のディレクトリでの管理者の役割にゲストを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-133">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="d3fd5-134">[**いいえ**] の場合、自分のディレクトリで一般ユーザーが持っているアクセス権と同じアクセス権を、ゲスト ユーザーが持つことになります。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-134">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="d3fd5-135">[**管理者とゲスト招待元ロールのユーザーが招待可能**]: [**はい**] の場合、管理者およびゲスト招待元ロールのユーザーがテナントにゲストを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-135">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="d3fd5-136">[**いいえ**] の場合、管理者およびユーザーはゲストをテナントに招待できません。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-136">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="d3fd5-137">[**メンバーが招待可能**]: ディレクトリの管理者以外のメンバーがゲストを招待できるようにするには、このポリシーを [**はい**] に設定します (推奨)。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-137">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="d3fd5-138">管理者だけがゲストを追加できるようにする場合は、このポリシーを [**いいえ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-138">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="d3fd5-139">[**いいえ**] に設定すると、管理者以外の Teams 所有者のゲスト エクスペリエンスが制限され、管理者により AAD に追加されたゲストだけを Teams に追加できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-139">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
- <span data-ttu-id="d3fd5-140">[**ゲストが招待可能**]: [**はい**] の場合、自分のディレクトリ内のゲストは他のゲストを招待して、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどでそれらのゲストと共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-140">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="d3fd5-141">[**いいえ**] の場合、組織と共同作業を行う他のゲストをゲストが招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-141">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="d3fd5-142">現在、Teams はゲスト招待者の役割をサポートしていないため、[**ゲストが招待できる**] を [**はい**] に設定しても、ゲストは Teams 内の他のゲストを招待できません。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-142">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
 
<span data-ttu-id="d3fd5-143">ゲストを招待できるユーザーの管理方法の詳細については、「[Azure Active Directory B2B コラボレーションの招待の委任](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-143">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="d3fd5-144">どのドメインをゲストとしてテナントに招待できるかを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-144">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="d3fd5-145">詳細については、「[Microsoft 365 グループへのゲスト アクセスの許可/ブロック](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-145">See [Allow/Block guest access to Microsoft 365 Groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span>

<span data-ttu-id="d3fd5-146">ユーザー ゲスト アカウントを手動で Azure AD B2B に追加する必要はありません。ゲストを Teams に追加すると、アカウントは自動的にディレクトリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-146">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="d3fd5-147">ゲスト アクセスのライセンス</span><span class="sxs-lookup"><span data-stu-id="d3fd5-147">Licensing for guest access</span></span>
<span data-ttu-id="d3fd5-148">ゲスト アクセス ライセンスは、Azure AD ライセンスの一部です。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-148">Guest access licensing is part of Azure AD licensing.</span></span> <span data-ttu-id="d3fd5-149">ゲスト アクセスは、Microsoft 365 Business Standard および Office 365 Enterprise のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-149">Guest access is included with all Microsoft 365 Business Standard and Office 365 Enterprise subscriptions.</span></span> <span data-ttu-id="d3fd5-150">ライセンスに関する詳細については、[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-150">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="d3fd5-151">Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-151">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="d3fd5-152">これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-152">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="d3fd5-153">Teams でのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="d3fd5-153">Control guest access in Teams</span></span>

<span data-ttu-id="d3fd5-154">Teams でのゲスト アクセスは、既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-154">Guest access is turned off by default in Teams.</span></span> <span data-ttu-id="d3fd5-155">ゲスト アクセスをオンにするに場合は、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-155">To turn on guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="d3fd5-156">Microsoft 365 グループでのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="d3fd5-156">Control guest access in Microsoft 365 Groups</span></span>

<span data-ttu-id="d3fd5-157">Microsoft 365 グループから、自分の組織内のすべての Microsoft 365 グループおよび Microsoft Teams のチームへのゲスト ユーザーおよびゲスト アクセスの追加を管理できます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-157">From Microsoft 365 Groups, you can control adding guest users and guest access to all Microsoft 365 Groups and Microsoft Teams teams in your organization.</span></span>

1. <span data-ttu-id="d3fd5-158">[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) で、グローバル管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-158">Sign in with your global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="d3fd5-159">左側で [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-159">On the left, choose **Settings** and then select **Services &amp; add-ins**.</span></span>

3. <span data-ttu-id="d3fd5-160">**[Microsoft 365 グループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-160">Select **Microsoft 365 Groups**.</span></span>

     ![設定での Microsoft 365 グループを示すスクリーン ショット](media/authorize-guest-image2.png)
  
4. <span data-ttu-id="d3fd5-162">組織外のチーム所有者やグループ所有者に Microsoft 365 へのアクセスを許可するか否かに応じて、[Microsoft 365 グループ] ページのトグルを **[オン]** または **[オフ]** にします。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-162">On the Microsoft 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Microsoft 365 Groups.</span></span> <span data-ttu-id="d3fd5-163">[**グループ所有者に組織外のユーザーをグループに追加させる**] の横にあるトグルをクリックまたはタップして [**オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-163">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="d3fd5-164">このトグルを **[オン]** にすると、グループおよびチームの所有者が組織外のユーザーを Microsoft 365 グループおよび Microsoft Teams に追加できるかどうかを制御するための別のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-164">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Microsoft 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="d3fd5-165">グループおよびチームの所有者がゲスト ユーザーを追加できるようにする場合は、このトグルを**オン**に設定します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-165">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![オプションが有効になっている Microsoft 365 グループ パネルを示すスクリーン ショット](media/authorize-guest-image3.png)

<span data-ttu-id="d3fd5-167">上記の設定は、テナント レベルで適用され、Microsoft 365 グループおよび Teams でのゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-167">These settings apply at the tenant level and control the guest experience in Microsoft 365 Groups and Teams.</span></span>

<span data-ttu-id="d3fd5-168">グループのゲスト アクセスの詳細については、「[ゲストを Microsoft 365 グループに追加する](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」を参照してください。ゲスト アクセスの仕組み、ゲスト アクセスの管理方法、よくある質問への回答が記載されています。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-168">See [Guest access in Microsoft 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="d3fd5-169">SharePoint Online と OneDrive for Business へのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="d3fd5-169">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="d3fd5-170">Teams は、SharePoint Online と OneDrive for Business を利用して、チャネルとチャット会話のファイルやドキュメントを保管します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-170">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  

<span data-ttu-id="d3fd5-171">Teams のゲスト アクセスを完全に利用するには、Office 365 管理者は次の設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-171">For the full Teams guest access experience, Office 365 admins need to configure the following settings:</span></span>

- <span data-ttu-id="d3fd5-172">SharePoint Online: **既存のゲスト**、**新規および既存のゲスト**、または **すべてのユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-172">In SharePoint Online: Select **Existing guests**, **New and existing guests**, or **Anyone**.</span></span>

    <span data-ttu-id="d3fd5-173">詳細については、「[外部共有をオンまたはオフにする](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-173">For more information, see [Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).</span></span>

- <span data-ttu-id="d3fd5-174">Microsoft 365 グループ: **[グループ所有者が組織外のユーザーをグループに追加できるようにする]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-174">In Microsoft 365 Groups: Turn on **Let group owners add people outside the organization to groups**</span></span>

    <span data-ttu-id="d3fd5-175">詳細については、上記の「[Microsoft 365 グループでのゲスト アクセスを管理する](#control-guest-access-in-microsoft-365-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-175">For more information, see [Control guest access in Microsoft 365 Groups](#control-guest-access-in-microsoft-365-groups), above.</span></span>
  
<span data-ttu-id="d3fd5-176">上記の設定は、テナント レベルで適用され、SharePoint Online、OneDrive for Business、Microsoft 365 グループ、Teams でのゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-176">These settings apply at the tenant level and control the guest experience in SharePoint Online, OneDrive for Business, Microsoft 365 Groups, and Teams.</span></span>

<span data-ttu-id="d3fd5-177">Teams に接続されたチーム サイトの SharePoint Online の外部ユーザー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-177">You can manage SharePoint Online external user settings for the team sites connected to Teams.</span></span> <span data-ttu-id="d3fd5-178">詳細については、「[SharePoint チーム サイト設定を管理する](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3fd5-178">To learn more, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="d3fd5-179">外部アクセス (フェデレーション) とゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="d3fd5-179">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="d3fd5-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3fd5-180">Related topics</span></span>

- [<span data-ttu-id="d3fd5-181">Microsoft 365 ゲストの共有設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="d3fd5-181">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
