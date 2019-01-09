---
title: Microsoft Teams でのゲスト アクセスを承認する
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/18
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams のゲスト アクセス機能を 4 つの異なる承認レベルで管理します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e07bfc162f2d3fbc59aa26dcf2cabd1bcf003e74
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772786"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="9efea-103">Microsoft Teams でのゲスト アクセスを承認する</span><span class="sxs-lookup"><span data-stu-id="9efea-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="9efea-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span><span class="sxs-lookup"><span data-stu-id="9efea-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="9efea-105">All the authorization levels apply to your Office 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="9efea-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="9efea-106">Each authorization level controls the guest experience as shown below:</span><span class="sxs-lookup"><span data-stu-id="9efea-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="9efea-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span><span class="sxs-lookup"><span data-stu-id="9efea-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="9efea-108">Controls the guest experience at the directory, tenant, and application level.</span><span class="sxs-lookup"><span data-stu-id="9efea-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="9efea-109">**Microsoft Teams**: Microsoft Teams のみを制御します。</span><span class="sxs-lookup"><span data-stu-id="9efea-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="9efea-110">**Office 365 グループ**: Office 365 グループおよび Microsoft Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="9efea-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="9efea-111">**SharePoint Online と OneDrive for Business**: SharePoint Online、OneDrive for Business、Office 365 グループ、および Microsoft Teams でのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="9efea-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="9efea-112">これらの異なる承認レベルにより、組織におけるゲスト アクセスを柔軟にセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9efea-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="9efea-113">など、マイクロソフトのチームにゲスト ユーザーを許可するが、組織の全体的なことができるようにするのにする場合は、だけにマイクロソフトのチームでのゲスト アクセスを無効します。</span><span class="sxs-lookup"><span data-stu-id="9efea-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="9efea-114">別の例: AAD、Teams、Groups レベルでゲスト アクセスを有効にしつつ、1 つ以上の基準 (データ分類が社外秘に等しいなど) に一致する選択したチームに対するゲスト ユーザーの追加を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9efea-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="9efea-115">SharePoint Online と OneDrive for Business には、Office 365 グループに依存しない独自のゲスト アクセス設定があります。</span><span class="sxs-lookup"><span data-stu-id="9efea-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="9efea-116">ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9efea-116">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

<span data-ttu-id="9efea-117">次の図では、Azure Active Directory、Microsoft Teams、および Office 365 との間でゲスト アクセスの承認の依存関係がどのように与えられているか、および組み合わされているかを示します。</span><span class="sxs-lookup"><span data-stu-id="9efea-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>

![ゲスト アクセスの承認の依存関係の図](media/teams_dependencies_image1.png)

<span data-ttu-id="9efea-119">次の図を示しています、高レベルは、一般的なゲスト アクセスへの招待と償還の流れを使用して、アクセス許可モデルに対するユーザーの操作性がどのように機能するか。</span><span class="sxs-lookup"><span data-stu-id="9efea-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![招待と償還のフローの図](media/authorize-guest-image1.png)

<span data-ttu-id="9efea-121">アプリケーション、コンポーネント、およびコネクタ可能性があります独自のアクセス許可のセットを必要とするまたはある特定のユーザー アカウントに同意するものと、ここで注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efea-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="9efea-122">これらは、個別に付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efea-122">These might need to be granted separately.</span></span> <span data-ttu-id="9efea-123">同様に、SharePoint では、余分な外部共有の境界を特定のユーザーのグループ、ユーザー、またはサイト レベルであってもを課す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9efea-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="9efea-124">Azure Active Directory 内のゲスト アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="9efea-124">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="9efea-125">Azure AD を使用すると、来園者とはどのような方法で、社外の関係者をテナントに招待できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="9efea-125">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="9efea-126">Azure の B2B のゲスト アクセスの詳細については、 [Azure Active Directory の B2B のゲスト ユーザーのアクセス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9efea-126">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="9efea-127">Azure AD のロールの詳細については[、Azure Active Directory テナント内のパートナーの組織からユーザーにアクセス許可を付与](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9efea-127">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="9efea-128">招待の設定は、テナント レベルで適用され、ディレクトリ、テナント、アプリケーション レベルでゲストのエクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="9efea-128">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> 

![Azure Active Directory ポータルのユーザー設定のスクリーンショット。](media/teams_dependencies_image2.png)

<span data-ttu-id="9efea-130">Azure AD での、外部ユーザーを構成するための設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9efea-130">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="9efea-131">**[Guest user permissions are limited (ゲスト ユーザーのアクセス権を制限)]**: **[Yes (はい)]** の場合、ゲストにはユーザー、グループ、その他のディレクトリ リソースの列挙などの特定のディレクトリのタスクに対するアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="9efea-131">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="9efea-132">また、自分のディレクトリでの管理者の役割にゲストを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="9efea-132">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="9efea-133">**[No (いいえ)]** の場合、自分のディレクトリで一般ユーザーが持っているアクセス権と同じアクセス権を、ゲスト ユーザーが持つことになります。</span><span class="sxs-lookup"><span data-stu-id="9efea-133">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="9efea-134">**[Admins and users in the guest inviter role can invite (管理者とゲスト招待元ロールのユーザーが招待可能)]**: **[Yes (はい)]** の場合、管理者およびゲスト招待元ロールのユーザーがテナントにゲストを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="9efea-134">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="9efea-135">**[No (いいえ)]** の場合、管理者およびユーザーはゲストをテナントに招待することができません。</span><span class="sxs-lookup"><span data-stu-id="9efea-135">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="9efea-136">**[Members can invite (メンバーが招待可能)]**: **[Yes (はい)]** の場合、自分のディレクトリ内の管理者ではないメンバーが、Azure AD によってセキュリティが確保された SharePoint サイトや Azure リソースなどで共同作業を行うゲストを招待することができます。</span><span class="sxs-lookup"><span data-stu-id="9efea-136">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="9efea-137">**[No (いいえ)]** の場合、ゲストを自分のディレクトリに招待できるのは管理者のみになります。</span><span class="sxs-lookup"><span data-stu-id="9efea-137">**No** means that only admins can invite guests to your directory.</span></span></br>
      
    > [!NOTE]
    > <span data-ttu-id="9efea-138">現時点では、チームでは、ゲストの招待者の役割をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9efea-138">Currently, Teams doesn't support the guest inviter role.</span></span> <span data-ttu-id="9efea-139">最低限の**メンバーを招待できます**] に **[はい]** のゲスト アクセスのチームで作業するのには表示/非表示を設定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="9efea-139">at a minimum the **Members can invite** toggle must be set to **Yes** for guest access to work in Teams.</span></span>
- <span data-ttu-id="9efea-140">**来園者が招待することができます**: **[はい]** をディレクトリ内には、来園者自身に招待できます、Azure AD、SharePoint サイトまたは Azure のリソースなど、セキュリティで保護されたリソースに対する共同作業を行うには、他のゲストを意味します。</span><span class="sxs-lookup"><span data-stu-id="9efea-140">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="9efea-141">**[No (いいえ)]** の場合、組織と共同作業を行う他のゲストをゲストが招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="9efea-141">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 
<span data-ttu-id="9efea-142">来園者を招待することができますを制御する方法の詳細については、 [Azure Active Directory の B2B の共同作業のための代理人の招待状](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9efea-142">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)</span></span>

> [!NOTE]
> <span data-ttu-id="9efea-143">どのドメインをゲストとしてテナントに招待することができるかを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="9efea-143">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="9efea-144">詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9efea-144">See [Allow/Block guest access to Office 365 groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span> 

<span data-ttu-id="9efea-145">アカウント追加されるので、ディレクトリに自動的にチームにゲストを追加すると、Azure AD B2B にユーザー アカウントを手動で追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9efea-145">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span> 

<span data-ttu-id="9efea-146">Azure AD のライセンスを使用すると、1 ライセンスあたり 5 つまでの来園者を追加します。</span><span class="sxs-lookup"><span data-stu-id="9efea-146">Azure AD licensing allows you to add up to 5 guests per license.</span></span> <span data-ttu-id="9efea-147">Azure AD のライセンスの詳細については、 [Azure Active Directory B2B コラボレーションのライセンス ガイド](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9efea-147">For more information about Azure AD licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span>

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="9efea-148">チームでのゲスト アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="9efea-148">Control guest access in Teams</span></span>

<span data-ttu-id="9efea-149">チームでは、ゲストの経験が有効か無効か、組織を制御できます。</span><span class="sxs-lookup"><span data-stu-id="9efea-149">In Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="9efea-150">設定は、既定で無効にし、チームのだけテナントのレベルで適用します。</span><span class="sxs-lookup"><span data-stu-id="9efea-150">The setting is disabled by default and applies at the tenant level for Teams only.</span></span>

<span data-ttu-id="9efea-151">マイクロソフトのチームとビジネス管理センターの Skype からチームのゲスト アクセスの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="9efea-151">You can manage Teams guest access settings from the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="9efea-152">詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9efea-152">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-office-365-groups"></a><span data-ttu-id="9efea-153">Office 365 のグループでのゲスト アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="9efea-153">Control guest access in Office 365 Groups</span></span>

<span data-ttu-id="9efea-154">Office 365 グループから、自分の組織内のすべての Office 365 グループおよび Microsoft Teams へのゲスト ユーザーおよびゲスト アクセスの追加を制御できます。</span><span class="sxs-lookup"><span data-stu-id="9efea-154">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="9efea-155">Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9efea-155">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="9efea-156">ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9efea-156">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
3. <span data-ttu-id="9efea-157">[**Office 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9efea-157">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 グループ](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  
4. <span data-ttu-id="9efea-159">Office 365 のグループ] ページでを**オン**または**オフ**、組織の Office 365 のアクセス グループの外のチームとグループの所有者を許可するかどうかに応じて、表示/非表示を設定します。</span><span class="sxs-lookup"><span data-stu-id="9efea-159">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="9efea-160">[**Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**] の横にあるトグルをクリックまたはタップして [**オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="9efea-160">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="9efea-161">\*\*\*\* するには、この切り替えを有効にする場合にマイクロソフト チームのグループを許可してチームの所有者は、Office 365 のグループに、組織外のユーザーを追加するかどうかは、コントロールに別のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9efea-161">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="9efea-162">グループを許可して、チームの所有者は、ゲスト ユーザーを追加する場合は、**上**にこの切り替えを設定します。</span><span class="sxs-lookup"><span data-stu-id="9efea-162">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![次のスクリーンショットは、組織外のグループ メンバーによるグループのコンテンツへのアクセス、グループ所有者による組織外のユーザーのグループへの追加のオプションをオンにした [Office 365 グループ] パネルを示しています。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)

<span data-ttu-id="9efea-164">これらの設定では、テナントのレベルで適用され、Office 365 のグループとマイクロソフトのチームでのゲストの経験を制御します。</span><span class="sxs-lookup"><span data-stu-id="9efea-164">These settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>

<span data-ttu-id="9efea-165">ゲスト アクセスのしくみ、ゲスト アクセス、およびよく寄せられる質問への回答を管理する方法を含め、グループでのゲスト アクセスの詳細については、 [Office 365 のグループにアクセスするゲスト](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9efea-165">See [Guest access in Office 365 Groups](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in Groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="9efea-166">ビジネスの SharePoint Online と OneDrive に、ゲスト アクセスを制御</span><span class="sxs-lookup"><span data-stu-id="9efea-166">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="9efea-167">Teams は、SharePoint Online と OneDrive for Business を利用して、チャネルとチャット会話のファイルやドキュメントを保管します。</span><span class="sxs-lookup"><span data-stu-id="9efea-167">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
   
<span data-ttu-id="9efea-168">Teams のゲスト アクセスの完全な操作性を有効にするため、Office 365 管理者は次の設定を**オン**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9efea-168">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>

- <span data-ttu-id="9efea-169">SharePoint Online: **Only allow sharing with external users already in the directory (ディレクトリに既に存在する外部ユーザーのみとの共有を許可する)**</span><span class="sxs-lookup"><span data-stu-id="9efea-169">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="9efea-170">詳しくは、「[SharePoint Online 環境の外部共有を管理する](https://docs.microsoft.com/sharepoint/external-sharing-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9efea-170">For more information, see [Manage external sharing for your SharePoint Online environment](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span></span>
    
- <span data-ttu-id="9efea-171">Office 365 グループ: **Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**</span><span class="sxs-lookup"><span data-stu-id="9efea-171">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="9efea-172">詳細については、上記の[Office 365 のグループでのゲスト アクセスの制御](#control-guest-access-in-office-365-groups)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9efea-172">For more information, see [Control guest access in Office 365 Groups](#control-guest-access-in-office-365-groups), above.</span></span>
  
<span data-ttu-id="9efea-173">これらの設定では、テナントのレベルで適用され、ビジネス、Office 365 のグループ、およびチームの SharePoint のオンライン、OneDrive でゲストの経験を制御します。</span><span class="sxs-lookup"><span data-stu-id="9efea-173">These settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups, and Teams.</span></span>

<span data-ttu-id="9efea-174">Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="9efea-174">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="9efea-175">詳細については、「[SharePoint チーム サイト設定を管理する](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9efea-175">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

