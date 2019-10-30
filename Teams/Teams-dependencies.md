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
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
description: Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ae23ec1a77a4adeaf6ec577146001e108807c15
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753262"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="bf6f2-103">Microsoft Teams でのゲスト アクセスを承認する</span><span class="sxs-lookup"><span data-stu-id="bf6f2-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="bf6f2-104">組織の要件を満たすために、Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="bf6f2-105">すべての承認レベルが Office 365 テナントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="bf6f2-106">それぞれの承認レベルによって、ゲストのエクスペリエンスが次の通り制御されます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="bf6f2-107">**Azure Active Directory**: Microsoft Teams のゲスト アクセスは、Azure Active Directory ビジネス ツー ビジネス (B2B) プラットフォームに依存します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="bf6f2-108">この承認レベルは、ゲストのエクスペリエンスをディレクトリ、テナント、およびアプリケーション レベルで制御します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="bf6f2-109">**Microsoft Teams**: Microsoft Teams のゲストエクスペリエンスのみを管理します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-109">**Microsoft Teams**: Controls the guest experience in Microsoft Teams only.</span></span>
- <span data-ttu-id="bf6f2-110">**Office 365 グループ**: Office 365 グループおよび Microsoft Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="bf6f2-111">**SharePoint Online と OneDrive for Business**: SharePoint Online、OneDrive for Business、Office 365 グループ、および Microsoft Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="bf6f2-112">これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="bf6f2-113">たとえば、自分の Microsoft Teams でゲスト ユーザーを許可せず、組織全体では許可する場合、Microsoft Teams でゲスト アクセスをオフにするだけです。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="bf6f2-114">別の例: Azure AD、Teams、Groups レベルでゲスト アクセスを有効にしつつ、1 つ以上の基準 (データ分類が社外秘に等しいなど) に一致する選択したチームに対するゲスト ユーザーの追加を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="bf6f2-115">SharePoint Online と OneDrive for Business には、Office 365 グループに依存しない独自のゲスト アクセス設定があります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span>

> [!NOTE]
> <span data-ttu-id="bf6f2-116">ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-116">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

<span data-ttu-id="bf6f2-117">次の図では、Azure Active Directory、Microsoft Teams、および Office 365 との間でゲスト アクセスの承認の依存関係がどのように与えられているか、および組み合わされているかを示します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>

![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)

<span data-ttu-id="bf6f2-119">次の図は、一般的なゲスト アクセスの招待と引き換えフローを通じて、ユーザーの作業環境がアクセス許可モデルとどのように連動するかを大まかに示しています。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![招待と引き換えフローの図](media/authorize-guest-image1.png)

<span data-ttu-id="bf6f2-121">ここで重要なことは、アプリ、ボット、コネクタが独自のアクセス許可のセットや、ユーザー アカウントに固有の同意が必要な可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="bf6f2-122">それぞれに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-122">These might need to be granted separately.</span></span> <span data-ttu-id="bf6f2-123">同様に SharePoint は、特定のユーザー、ユーザーのグループ、またはサイト レベルであっても、外部共有の境界を追加することがあります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="bf6f2-124">上の 2 つの図は、[Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) でも同じように利用することができます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-124">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="bf6f2-125">Azure Active Directory のゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="bf6f2-125">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="bf6f2-126">Azure AD を使用し、外部の共同作業者をゲストとして、どんな方法で、テナントに招待できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-126">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="bf6f2-127">Azure B2B のゲスト アクセスの詳細については、「[Azure Active Directory B2B のゲスト ユーザー アクセスとは](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-127">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="bf6f2-128">Azure AD の役割に関する詳細については、「[Azure Active Directory テナントでパートナー組織からユーザーにアクセス許可を付与する](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-128">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="bf6f2-129">招待の設定は、テナント レベルで適用され、ディレクトリ、テナント、アプリケーション レベルでゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-129">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="bf6f2-130">Azure portal でこの設定を構成するには、**[Azure Active Directory]** > **[ユーザー]** > **[ユーザー設定]** の順に移動し、**[外部ユーザー]** で **[外部コラボレーションの設定を管理します]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-130">To configure these settings in the Azure portal, go to **Azure Active Directory** > **Users** > **User settings**, and under **External users**, select **Manage external collaboration settings**.</span></span>

<span data-ttu-id="bf6f2-131">Azure AD には、外部ユーザーを構成する次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-131">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="bf6f2-132">[**ゲスト ユーザーのアクセス権を制限**]: [**はい**] の場合、ゲストにはユーザー、グループ、その他のディレクトリ リソースの列挙などの特定のディレクトリのタスクに対するアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-132">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="bf6f2-133">また、自分のディレクトリでの管理者の役割にゲストを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-133">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="bf6f2-134">[**いいえ**] の場合、自分のディレクトリで一般ユーザーが持っているアクセス権と同じアクセス権を、ゲスト ユーザーが持つことになります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-134">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="bf6f2-135">[**管理者とゲスト招待元ロールのユーザーが招待可能**]: [**はい**] の場合、管理者およびゲスト招待元ロールのユーザーがテナントにゲストを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-135">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="bf6f2-136">[**いいえ**] の場合、管理者およびユーザーはゲストをテナントに招待できません。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-136">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="bf6f2-137">[**メンバーが招待可能**]: [**はい**] の場合、自分のディレクトリ内の管理者ではないメンバーが、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどで共同作業を行うゲストを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-137">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="bf6f2-138">[**いいえ**] の場合、ゲストを自分のディレクトリに招待できるのは管理者のみになります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-138">**No** means that only admins can invite guests to your directory.</span></span></br>
      
    > [!IMPORTANT]
    > <span data-ttu-id="bf6f2-139">ゲスト アクセスを Teams ですべて機能させるには、[**メンバーが招待できる**] を [**はい**] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-139">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>
- <span data-ttu-id="bf6f2-140">[**ゲストが招待可能**]: [**はい**] の場合、自分のディレクトリ内のゲストは他のゲストを招待して、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどでそれらのゲストと共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-140">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="bf6f2-141">[**いいえ**] の場合、組織と共同作業を行う他のゲストをゲストが招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-141">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="bf6f2-142">現在、Teams はゲスト招待者の役割をサポートしていないため、[**ゲストが招待できる**] を [**はい**] に設定しても、ゲストは Teams 内の他のゲストを招待できません。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-142">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
 
<span data-ttu-id="bf6f2-143">ゲストを招待できるユーザーの管理方法の詳細については、「[Azure Active Directory B2B コラボレーションの招待の委任](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-143">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="bf6f2-144">どのドメインをゲストとしてテナントに招待できるかを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-144">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="bf6f2-145">詳細については、「[Office 365 グループへのゲスト アクセスを許可/拒否する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-145">See [Allow/Block guest access to Office 365 Groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span>

<span data-ttu-id="bf6f2-146">ユーザー ゲスト アカウントを手動で Azure AD B2B に追加する必要はありません。ゲストを Teams に追加すると、アカウントは自動的にディレクトリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-146">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="bf6f2-147">ゲスト アクセスのライセンス</span><span class="sxs-lookup"><span data-stu-id="bf6f2-147">Licensing for guest access</span></span>
<span data-ttu-id="bf6f2-148">ゲスト アクセス ライセンスは、Azure AD ライセンスの一部です。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-148">Guest access licensing is part of Azure AD licensing.</span></span> <span data-ttu-id="bf6f2-149">ゲスト アクセスはすべての Office 365 Business Premium サブスクリプションおよび Office 365 Enterprise サブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-149">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="bf6f2-150">ライセンスに関する詳細については、[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-150">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="bf6f2-151">Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-151">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="bf6f2-152">Teams を使用するこれらのユーザーの場合は、Office 365 Business Premium、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-152">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="bf6f2-153">Teams でのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="bf6f2-153">Control guest access in Teams</span></span>

<span data-ttu-id="bf6f2-154">Teams でのゲスト アクセスは、既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-154">Guest access is turned off by default.</span></span> <span data-ttu-id="bf6f2-155">ゲスト アクセスをオンにするに場合は、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-155">To turn on guest access, see [Turn on or off guest access in Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-office-365-groups"></a><span data-ttu-id="bf6f2-156">Office 365 グループでゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="bf6f2-156">Control guest access in Office 365 Groups</span></span>

<span data-ttu-id="bf6f2-157">Office 365 グループから、自分の組織内のすべての Office 365 グループおよび Microsoft Teams のチームへのゲスト ユーザーおよびゲスト アクセスの追加を制御できます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-157">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 Groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="bf6f2-158">[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) で、Office 365 全体管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-158">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="bf6f2-159">左側で [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-159">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>

3. <span data-ttu-id="bf6f2-160">[**Office 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-160">Select **Office 365 Groups**.</span></span>

     ![設定での Office 365 グループを示すスクリーン ショット](media/authorize-guest-image2.png)
  
4. <span data-ttu-id="bf6f2-162">組織外のチーム所有者やグループ所有者に Office 365 へのアクセスを許可するか否かに応じて、[Office 365 グループ] ページのトグルを [**オン**] または [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-162">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Office 365 Groups.</span></span> <span data-ttu-id="bf6f2-163">[**グループ所有者に組織外のユーザーをグループに追加させる**] の横にあるトグルをクリックまたはタップして [**オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-163">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="bf6f2-164">このトグルを**オン**にすると、グループおよびチームの所有者が組織外のユーザーを Office 365 グループおよび Microsoft Teams に追加できるかどうかを制御するための別のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-164">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="bf6f2-165">グループおよびチームの所有者がゲスト ユーザーを追加できるようにする場合は、このトグルを**オン**に設定します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-165">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![オプションが有効になっている Office 365 グループ パネルを示すスクリーン ショット](media/authorize-guest-image3.png)

<span data-ttu-id="bf6f2-167">上記の設定は、テナント レベルで適用され、Office 365 グループおよび Teams でのゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-167">These settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>

<span data-ttu-id="bf6f2-168">グループのゲスト アクセスの詳細については、「[Office 365 グループのゲスト アクセス](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」を参照してください。ゲスト アクセスの仕組み、ゲスト アクセスの管理方法、よくある質問への回答が記載されています。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-168">See [Guest access in Office 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="bf6f2-169">SharePoint Online と OneDrive for Business へのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="bf6f2-169">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="bf6f2-170">Teams は、SharePoint Online と OneDrive for Business を利用して、チャネルとチャット会話のファイルやドキュメントを保管します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-170">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  

<span data-ttu-id="bf6f2-171">Teams のゲスト アクセスを完全に利用するには、Office 365 管理者は次の設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-171">To enable the full Teams guest access experience, Office 365 admins need to select On for the following settings:</span></span>

- <span data-ttu-id="bf6f2-172">SharePoint Online: **既存のゲスト**、**新規および既存のゲスト**、または **すべてのユーザー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-172">In SharePoint Online: **Existing guests**, **New and existing guests**, or **Anyone**</span></span>

    <span data-ttu-id="bf6f2-173">詳細については、「[外部共有をオンまたはオフにする](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-173">For more information, see [Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).</span></span>

- <span data-ttu-id="bf6f2-174">Office 365 グループ: [**グループ所有者が組織外のユーザーをグループに追加できるようにする**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-174">In Office 365 Groups: **Let group owners add people outside the organization to groups**</span></span>

    <span data-ttu-id="bf6f2-175">詳細については、上記の「[Office 365 グループのゲスト アクセスを管理する](#control-guest-access-in-office-365-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-175">For more information, see [Control guest access in Office 365 Groups](#control-guest-access-in-office-365-groups), above.</span></span>
  
<span data-ttu-id="bf6f2-176">上記の設定は、テナント レベルで適用され、SharePoint Online、OneDrive for Business、Office 365 グループおよび Teams でのゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-176">These settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups, and Teams.</span></span>

<span data-ttu-id="bf6f2-177">Teams に接続されたチーム サイトの SharePoint Online の外部ユーザー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-177">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="bf6f2-178">詳細については、「[SharePoint チーム サイト設定を管理する](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bf6f2-178">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="bf6f2-179">外部アクセス (フェデレーション) とゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="bf6f2-179">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="bf6f2-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf6f2-180">Related topics</span></span>

- [<span data-ttu-id="bf6f2-181">Microsoft 365 ゲストの共有設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="bf6f2-181">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
