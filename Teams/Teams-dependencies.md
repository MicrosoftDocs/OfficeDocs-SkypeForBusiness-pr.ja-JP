---
title: "Microsoft のチームでゲスト アクセスを承認します。"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "Microsoft チーム ゲスト アクセス機能と承認の 4 つの異なるレベルの機能を管理します。"
ms.openlocfilehash: 86384a18fdea3d15bfb0bf6368a2529a05872371
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="570a3-103">Microsoft のチームでゲスト アクセスを承認します。</span><span class="sxs-lookup"><span data-stu-id="570a3-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="570a3-p101">組織の要件を満たすためには、Microsoft チーム ゲスト アクセス機能と承認の 4 つの異なるレベルの機能を管理できます。すべての承認レベルは、Office 365 テナントに適用されます。各承認レベルは、次に示すように、ゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="570a3-p101">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization. All the authorization levels apply to your Office 365 tenant. Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="570a3-p102">**Azure Active Directory**: Microsoft チームでゲスト アクセス Azure AD ビジネス基幹業務 (B2B) プラットフォームに依存します。ディレクトリ、テナント、およびアプリケーション レベルでのゲスト ユーザー エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="570a3-p102">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform. Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="570a3-109">**Microsoft チーム**: のみ Microsoft チームを制御します。</span><span class="sxs-lookup"><span data-stu-id="570a3-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="570a3-110">**Office 365 のグループ**: Office 365 のグループおよび Microsoft チーム ゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="570a3-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="570a3-111">**SharePoint Online と OneDrive for Business**: ゲストでの操作環境、SharePoint Online、OneDrive for Business、Office 365 のグループ、および Microsoft チームを制御します。</span><span class="sxs-lookup"><span data-stu-id="570a3-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="570a3-p103">別の承認、次のレベルは、セットアップする方法のゲスト アクセス、組織の柔軟性を提供します。たとえば、Microsoft チーム組織のゲスト ユーザーを許可しない場合は、アクセスだけを無効にゲスト Microsoft チームでします。別の例: AAD、チーム、グループ レベルでゲスト アクセスを有効にできますが、[選択したデータの分類などの 1 つまたは複数の条件を満たすチームで無効にするゲスト ユーザーの追加と値が等しい機密します。またなど、Office 365 グループを使用しません。SharePoint Online と OneDrive for Business、Office 365 のグループに依存しないする独自のゲスト アクセスの設定をあります。</span><span class="sxs-lookup"><span data-stu-id="570a3-p103">These different authorization levels provide you with flexibility in how you set up guest access for your organization. For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams. Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential. And, perhaps you don’t use Office 365 Groups. SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="570a3-117">ゲストは、 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347)と[Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019)サービスの制限の適用対象はします。</span><span class="sxs-lookup"><span data-stu-id="570a3-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="570a3-118">次の図では、ゲスト アクセス承認の依存関係が与えられてし、Azure Active Directory、マイクロソフトのチームと Office 365 の統合方法を示します。</span><span class="sxs-lookup"><span data-stu-id="570a3-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![ゲスト アクセスの承認の依存関係の図。](media/teams_dependencies_image1.png)


##<a name="azure-active-directory"></a><span data-ttu-id="570a3-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="570a3-120">Azure Active Directory</span></span>

<span data-ttu-id="570a3-p104">Azure AD ビジネス基幹業務 (B2B) の共同作業の潜在的なゲスト ユーザーへの招待を送信していないテナント管理者に制限されています。代わりに、委任ロールを持つができるように招待状を送信するのにユーザーを招待状を送信するには、ポリシーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="570a3-p104">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins. Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="570a3-123">招待状の設定は、テナント レベルで適用し、ディレクトリ、テナント、およびアプリケーション レベルでのゲスト ユーザー エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="570a3-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span>


![Azure Active Directory ポータルのスクリーン ショットのユーザー設定します。](media/teams_dependencies_image2.png)


<span data-ttu-id="570a3-125">次の招待状のポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="570a3-125">You can set the following invitation policies:</span></span>
- <span data-ttu-id="570a3-126">招待状をオフにします。</span><span class="sxs-lookup"><span data-stu-id="570a3-126">Turn off invitations.</span></span>
- <span data-ttu-id="570a3-127">管理者とゲスト招待者の役割のユーザーのみを招待できます。</span><span class="sxs-lookup"><span data-stu-id="570a3-127">Only admins and users in the guest inviter role can invite.</span></span>
- <span data-ttu-id="570a3-128">管理者、ゲスト招待者の役割およびメンバーを招待できます。</span><span class="sxs-lookup"><span data-stu-id="570a3-128">Admins, the guest inviter role, and members can invite.</span></span>
- <span data-ttu-id="570a3-p105">ゲストを含む、すべてのユーザーを招待できます。(これは、テナントの既定のポリシーです)。</span><span class="sxs-lookup"><span data-stu-id="570a3-p105">All users, including guests, can invite. (This is the default policy for tenants.)</span></span>


##<a name="microsoft-teams"></a><span data-ttu-id="570a3-131">Microsoft チーム</span><span class="sxs-lookup"><span data-stu-id="570a3-131">Microsoft Teams</span></span>

<span data-ttu-id="570a3-p106">Microsoft チームで、ゲスト エクスペリエンスが有効か無効か、組織を制御できます。設定は、既定で無効にし、Microsoft チームのみテナント レベルで適用します。</span><span class="sxs-lookup"><span data-stu-id="570a3-p106">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization. The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="570a3-p107">Office 365 管理センターから Microsoft チーム ゲスト アクセスの設定を管理できます。詳細については、 [Microsoft チームにゲスト アクセスを無効または有効にする](set-up-guests.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="570a3-p107">You can manage Microsoft Teams guest access settings from the Office 365 admin center. For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


##<a name="office-365-groups"></a><span data-ttu-id="570a3-136">Office 365 のグループ</span><span class="sxs-lookup"><span data-stu-id="570a3-136">Office 365 Groups</span></span>

<span data-ttu-id="570a3-137">Office 365 のグループから、組織内には、ゲスト ユーザーの追加とすべての Office 365 のグループおよび Microsoft チームにゲスト アクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="570a3-137">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="570a3-138">[Https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)での自分の Office 365 グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="570a3-138">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="570a3-139">ナビゲーション メニューで、**設定**を選択し、[**サービス&amp;アドイン**します。</span><span class="sxs-lookup"><span data-stu-id="570a3-139">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="570a3-140">**Office 365 グループ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="570a3-140">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 のグループ](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="570a3-p108">[Office 365 のグループ] ページで、設定に切り替えますの**オン**と**オフを切り替える**、によっては、組織の Office 365 へのアクセス グループ外チーム、グループの所有者ができるようにする場合。をクリックするか、 **[** **グループに所属組織外の人を追加するグループ所有者**の横にあるトグルをタップします。この切り替えを有効にする場合に、組織外のユーザーを Office 365 のグループに追加するグループとチームの所有者ができるようにして、チームが Microsoft かどうかは、コントロールに別のオプションが表示されます。ゲスト ユーザーの追加] グループおよびチームの所有者ができるようにする場合、この切り替え上に設定します。![スクリーン ショットは、グループ コンテンツには、組織のアクセスの外側のグループのメンバーができるようにして、組織外のユーザーをグループに追加するグループの所有者をオンにするオプションを使用して、Office 365 グループ パネルを示しています。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="570a3-p108">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups. Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**. If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams. Set this toggle to On if you want to let group and team owners add guest users. ![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="570a3-147">上記の設定は、テナント レベルで適用し、Office 365 のグループおよび Microsoft チーム ゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="570a3-147">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


##<a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="570a3-148">SharePoint Online と OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="570a3-148">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="570a3-149">チームは、SharePoint Online と OneDrive for Business にファイルやチャネルおよびチャットのドキュメントの保存に依存します。</span><span class="sxs-lookup"><span data-stu-id="570a3-149">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="570a3-150">エクスペリエンスを可能に、完全なチーム ゲスト アクセス、Office 365 の管理者は**、次の設定をオン**に必要があります。</span><span class="sxs-lookup"><span data-stu-id="570a3-150">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="570a3-151">SharePoint Online: を**のみディレクトリ内にある外部ユーザーとの共有を許可します。**</span><span class="sxs-lookup"><span data-stu-id="570a3-151">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="570a3-152">詳細については、 [SharePoint Online 環境の外部共有を管理する](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="570a3-152">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="570a3-153">Office 365 のグループ:**グループの所有者グループに所属組織外の人を追加します。**</span><span class="sxs-lookup"><span data-stu-id="570a3-153">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="570a3-154">詳細については、 [Microsoft チームへのゲスト アクセスの制御](#controlguest)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="570a3-154">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="570a3-155">上記の設定は、テナント レベルで適用し、SharePoint Online、OneDrive for Business、Office 365 のグループと Microsoft チームのゲスト エクスペリエンスを制御します。</span><span class="sxs-lookup"><span data-stu-id="570a3-155">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="570a3-p109">チーム接続されているチーム サイトの SharePoint Online の外部のユーザー設定を管理することができます。詳細については、 [SharePoint チーム サイトの設定を管理する](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="570a3-p109">You can manage SharePoint Online external user settings for the Teams connected team site. For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>