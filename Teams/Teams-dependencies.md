---
title: Microsoft Teams でのゲスト アクセスを承認する
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d31bb8eafdaa6a04fe34f8433e8484ec447e7c1
ms.sourcegitcommit: 2ce680aba13d1d781019b766a04e4e7d46d4f72c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2018
ms.locfileid: "21136308"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="32680-103">Microsoft Teams でのゲスト アクセスを承認する</span><span class="sxs-lookup"><span data-stu-id="32680-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="32680-104">組織の要件を満たすために、Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理することができます。</span><span class="sxs-lookup"><span data-stu-id="32680-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="32680-105">すべての承認レベルが Office 365 テナントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="32680-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="32680-106">それぞれの承認レベルによって、ゲストのエクスペリエンスが次の通り制御されます。</span><span class="sxs-lookup"><span data-stu-id="32680-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="32680-107">**Azure Active Directory**: Microsoft Teams のゲスト アクセスは、Azure Active Directory ビジネス ツー ビジネス (B2B) プラットフォームに依存します。</span><span class="sxs-lookup"><span data-stu-id="32680-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="32680-108">ゲストのエクスペリエンスをディレクトリ、テナント、およびアプリケーション レベルで制御します。</span><span class="sxs-lookup"><span data-stu-id="32680-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="32680-109">**Microsoft Teams**: Microsoft Teams のみを制御します。</span><span class="sxs-lookup"><span data-stu-id="32680-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="32680-110">**Office 365 グループ**: Office 365 グループおよび Microsoft Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="32680-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="32680-111">**SharePoint Online と OneDrive for Business**: SharePoint Online、OneDrive for Business、Office 365 グループ、および Microsoft Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="32680-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="32680-112">これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="32680-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="32680-113">たとえば、自分の Microsoft Teams の組織でゲスト ユーザーを許可したくない場合は、Microsoft Teams でゲスト アクセスをオフにするだけです。</span><span class="sxs-lookup"><span data-stu-id="32680-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="32680-114">別の例: AAD、Teams、Groups レベルでゲスト アクセスを有効にしつつ、1 つ以上の基準 (データ分類が社外秘に等しいなど) に一致する選択したチームに対するゲスト ユーザーの追加を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="32680-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="32680-115">また、Office 365 グループを使用していないことも考えられます。</span><span class="sxs-lookup"><span data-stu-id="32680-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="32680-116">SharePoint Online と OneDrive for Business には、Office 365 グループに依存しない独自のゲスト アクセス設定があります。</span><span class="sxs-lookup"><span data-stu-id="32680-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="32680-117">ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="32680-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="32680-118">次の図では、Azure Active Directory、Microsoft Teams、および Office 365 との間でゲスト アクセスの承認の依存関係がどのように与えられているか、および組み合わされているかを示します。</span><span class="sxs-lookup"><span data-stu-id="32680-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a><span data-ttu-id="32680-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="32680-120">Azure Active Directory</span></span>

<span data-ttu-id="32680-121">Azure AD ビジネス ツー ビジネス (B2B) コラボレーションでは、潜在的なゲスト ユーザーへの招待の送信はテナントの管理者に制限されません。</span><span class="sxs-lookup"><span data-stu-id="32680-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="32680-122">代わりに、ポリシーを使用して、招待を送信できる役割が設定されているユーザーに、招待状を送信する権限を委任します。</span><span class="sxs-lookup"><span data-stu-id="32680-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="32680-123">招待の設定は、テナント レベルで適用され、ディレクトリ、テナント、アプリケーション レベルでゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="32680-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="32680-124">来園者をサポートするために最低でも、**メンバーを招待**する必要がありますに設定する **[はい]**。</span><span class="sxs-lookup"><span data-stu-id="32680-124">At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>


![Azure Active Directory ポータルのユーザー設定のスクリーンショット。](media/teams_dependencies_image2.png)

<span data-ttu-id="32680-126">Azure AD には、外部のユーザーを構成するのには次の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="32680-126">Azure AD includes the following settings to configure external users:</span></span>
- <span data-ttu-id="32680-127">**ゲスト ユーザーのアクセス許可が制限されます**: **[はい]** [来園者がディレクトリの特定のタスクのアクセス許可を持つ、ユーザー、グループ、またはその他のディレクトリ リソースを次のように列挙されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="32680-127">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="32680-128">さらに、来園者は、ディレクトリ内の管理役割に割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="32680-128">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="32680-129">来園者は**** ことを意味では、通常のユーザーのディレクトリにあるディレクトリ データへのアクセスがありません。</span><span class="sxs-lookup"><span data-stu-id="32680-129">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="32680-130">**管理者グループおよびゲストの招待者のロールにユーザーを招待できます**:**はい**できることを意味管理者グループおよびユーザーを「ゲスト招待者」の役割テナントには、来園者を招待します。</span><span class="sxs-lookup"><span data-stu-id="32680-130">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="32680-131">**なし**には、管理者ことを意味し、ユーザーは、テナントには、来園者を招待できません。</span><span class="sxs-lookup"><span data-stu-id="32680-131">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="32680-132">**メンバーが招待することができます**:**はい**ディレクトリの管理者以外のメンバーが、Azure AD、SharePoint サイトまたは Azure のリソースなど、セキュリティで保護されたリソースに対する共同作業を行うには、来園者を招待することを意味します。</span><span class="sxs-lookup"><span data-stu-id="32680-132">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="32680-133">ディレクトリに来園者は管理者のみが招待することができます**しない**ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="32680-133">**No** means that only admins can invite guests to your directory.</span></span>
- <span data-ttu-id="32680-134">**来園者が招待することができます**: **[はい]** をディレクトリ内には、来園者自身に招待できます、Azure AD、SharePoint サイトまたは Azure のリソースなど、セキュリティで保護されたリソースに対する共同作業を行うには、他のゲストを意味します。</span><span class="sxs-lookup"><span data-stu-id="32680-134">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guest to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="32680-135">来園者は**ない**ことを意味は、組織との共同作業には、他のゲストを招待できません。</span><span class="sxs-lookup"><span data-stu-id="32680-135">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 


> [!NOTE]
> <span data-ttu-id="32680-136">ゲストとして、テナントにどのドメインを招待することができますを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="32680-136">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="32680-137">[Office 365 のグループへのゲスト アクセスの許可/禁止](https://technet.microsoft.com/library/a86bb46f-0e5b-43a3-b6ef-7394f344a8da)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32680-137">See [Allow/Block guest access to Office 365 groups](https://technet.microsoft.com/library/a86bb46f-0e5b-43a3-b6ef-7394f344a8da).</span></span> 

## <a name="microsoft-teams"></a><span data-ttu-id="32680-138">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32680-138">Microsoft Teams</span></span>
<span data-ttu-id="32680-139">Microsoft Teams では、自分の組織においてゲストのエクスペリエンスを有効にするか無効にするかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="32680-139">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="32680-140">この設定は既定で無効になっていて、Microsoft Teams のテナント レベルのみで適用されます。</span><span class="sxs-lookup"><span data-stu-id="32680-140">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="32680-141">Office 365 管理センターで Microsoft Teams ゲスト アクセスの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="32680-141">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="32680-142">詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32680-142">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="office-365-groups"></a><span data-ttu-id="32680-143">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="32680-143">Office 365 Groups</span></span>

<span data-ttu-id="32680-144">Office 365 グループから、自分の組織内のすべての Office 365 グループおよび Microsoft Teams へのゲスト ユーザーおよびゲスト アクセスの追加を制御できます。</span><span class="sxs-lookup"><span data-stu-id="32680-144">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="32680-145">Office 365 のグローバル管理者アカウントを使用してサインイン[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="32680-145">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="32680-146">ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32680-146">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="32680-147">[**Office 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32680-147">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 グループ](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="32680-149">組織外のチーム所有者やグループ所有者に Office 365 へのアクセスを許可するかどうかに応じて、[Office 365 グループ] ページのトグルを [**オン**] または [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="32680-149">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="32680-150">[**Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**] の横にあるトグルをクリックまたはタップして [**オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="32680-150">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="32680-151">このトグルをオンにすると、グループおよびチームの所有者が組織外のユーザーを Office 365 グループおよび Microsoft Teams に追加できるかどうかを制御するための別のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32680-151">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="32680-152">グループおよびチームの所有者がゲスト ユーザーを追加できるようにする場合は、このトグルをオンに設定します。</span><span class="sxs-lookup"><span data-stu-id="32680-152">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="32680-153">![次のスクリーンショットは、組織外のグループ メンバーによるグループのコンテンツへのアクセス、グループ所有者による組織外のユーザーのグループへの追加のオプションをオンにした [Office 365 グループ] パネルを示しています。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="32680-153">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="32680-154">上記の設定は、テナント レベルで適用され、Office 365 グループおよび Microsoft Teams でのゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="32680-154">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


## <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="32680-155">SharePoint Online と OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="32680-155">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="32680-156">Teams は、SharePoint Online と OneDrive for Business を利用して、チャネルとチャット会話のファイルやドキュメントを保管します。</span><span class="sxs-lookup"><span data-stu-id="32680-156">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="32680-157">Teams のゲスト アクセスの完全な操作性を有効にするため、Office 365 管理者は次の設定を**オン**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32680-157">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="32680-158">SharePoint Online: **Only allow sharing with external users already in the directory (ディレクトリに既に存在する外部ユーザーのみとの共有を許可する)**</span><span class="sxs-lookup"><span data-stu-id="32680-158">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="32680-159">詳しくは、「[SharePoint Online 環境の外部共有を管理する](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32680-159">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="32680-160">Office 365 グループ: **Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**</span><span class="sxs-lookup"><span data-stu-id="32680-160">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="32680-161">詳細については、「[Control guest access to Microsoft Teams (Microsoft Teams へのゲスト アクセスを制御する)](#controlguest)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32680-161">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="32680-162">上記の設定は、テナント レベルで適用され、SharePoint Online、OneDrive for Business、Office 365 グループおよび Microsoft Teams でのゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="32680-162">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="32680-163">Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="32680-163">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="32680-164">詳細については、「[SharePoint チーム サイト設定を管理する](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="32680-164">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
