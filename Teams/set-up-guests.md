---
title: "Microsoft Teams へのゲスト アクセスをセットアップする"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams でのゲスト アクセス機能を有効にします。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a><span data-ttu-id="2e4e9-103">Microsoft Teams へのゲスト アクセスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="2e4e9-103">Set up guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="2e4e9-104">Microsoft Teams は Office 365 グループに基づき構築されていて、SharePoint Online も利用しています。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-104">Microsoft Teams is built upon Office 365 Groups, and it also relies on SharePoint Online.</span></span> <span data-ttu-id="2e4e9-105">このため、Teams でのゲスト アクセス機能をオンにすることに加えて、特定の設定を Office 365 グループおよび SharePoint Online で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-105">That’s why specific settings must be enabled in Office 365 Groups and SharePoint Online in addition to turning on the guest access feature in Teams.</span></span>


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a><span data-ttu-id="2e4e9-106">Office 365 グループでのゲストの追加を許可する</span><span class="sxs-lookup"><span data-stu-id="2e4e9-106">Allow the addition of guests in Office 365 Groups</span></span>
<span data-ttu-id="2e4e9-107"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="2e4e9-107"></span></span>


1. <span data-ttu-id="2e4e9-108">Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-108">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="2e4e9-109">ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-109">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="2e4e9-110">[**Office 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-110">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 グループ](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="2e4e9-112">組織外のチーム所有者やグループ所有者に Office 365 へのアクセスを許可するかどうかに応じて、[Office 365 グループ] ページのトグルを [**オン**] または [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-112">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="2e4e9-113">[**Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**] の横にあるトグルをクリックまたはタップして [**オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-113">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>


![次のスクリーンショットは、組織外のグループ メンバーによるグループのコンテンツへのアクセス、グループ所有者による組織外のユーザーのグループへの追加のオプションをオンにした [Office 365 グループ] パネルを示しています。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a><span data-ttu-id="2e4e9-115">SharePoint Online での共有を有効にする</span><span class="sxs-lookup"><span data-stu-id="2e4e9-115">Enable sharing in SharePoint Online</span></span>

<span data-ttu-id="2e4e9-116">SharePoint Online の [共有] オプションでは、組織へのゲストの追加を許可します。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-116">The Sharing option allows guests to be added to your organization.</span></span> <span data-ttu-id="2e4e9-117">既定では、[共有] オプションは有効です。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-117">By default, the Sharing option is enabled.</span></span> <span data-ttu-id="2e4e9-118">[共有] オプションをオフにする方法の詳細については、「[[共有] オプションをオンまたはオフにする](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-118">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
   <span data-ttu-id="2e4e9-119">管理者は、外部共有の設定から独立して、Azure Active Directory でゲスト アカウントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-119">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="2e4e9-120">外部共有がオフの場合、管理者のみがゲスト アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-120">If external sharing is off, only an admin can create guest accounts.</span></span> 
    

> [!IMPORTANT]
> <span data-ttu-id="2e4e9-121">[共有] オプションをオフにすると、ゲスト アクセスが利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-121">If you turn off the Sharing option, guest access isn't available.</span></span> 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="2e4e9-122">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="2e4e9-122">Turn on or off guest access for Microsoft Teams</span></span>
<span data-ttu-id="2e4e9-123"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="2e4e9-123"></span></span>

<span data-ttu-id="2e4e9-124">Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-124">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="2e4e9-125">ゲスト設定は Azure Active Directory で設定します。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-125">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="2e4e9-126">その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-126">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="2e4e9-127">ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-127">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>



1. <span data-ttu-id="2e4e9-128">Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-128">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="2e4e9-129">ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-129">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Office 365 にサインインし、Office 365 管理センターに移動して、[設定]、[Services &amp; add-ins (サービスとアドイン)] の順に選択します。](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="2e4e9-131">[**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-131">Select **Microsoft Teams**.</span></span>
    
     ![次のスクリーンショットは、Office 365 管理センターで選択した Microsoft Teams アドインのオプションを示しています。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="2e4e9-133">[**Select the user/license type you want to configure (構成するユーザー/ライセンスの種類を選択する)**] で [**ゲスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-133">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![Microsoft Teams アドインのスクリーンショットでは、ゲスト ライセンスが選択され、Microsoft Teams オプションがオンに設定されています。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="2e4e9-135">[**Turn Microsoft Teams on or off for all users of this type (この種類のすべてのユーザーについて Microsoft Teams をオンまたはオフにする)**] の横にあるトグルをクリックまたはタップして [**オン**] にして組織の Teams とゲスト アクセスをオンにし、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e4e9-135">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  

