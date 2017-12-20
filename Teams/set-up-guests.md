---
title: "Microsoft Teams へのゲスト アクセスをオンまたはオフにする"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams でのゲスト アクセス機能をオンまたはオフにします。"
ms.openlocfilehash: 5d65e63aab189ef252bde5d14774d8008aaf1872
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2017
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="13f56-103">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="13f56-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================





  



<span data-ttu-id="13f56-104">Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13f56-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="13f56-105">ゲスト設定は Azure Active Directory で設定します。</span><span class="sxs-lookup"><span data-stu-id="13f56-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="13f56-106">その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="13f56-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="13f56-107">ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13f56-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="13f56-108">ゲスト アクセス機能の完全なエクスペリエンスを有効にするためには、Microsoft Teams、Azure Active Directory、および Office 365 の間での中心的な承認の依存関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="13f56-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="13f56-109">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13f56-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

1. <span data-ttu-id="13f56-110">Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="13f56-110">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="13f56-111">ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13f56-111">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Office 365 にサインインし、Office 365 管理センターに移動して、[設定]、[Services &amp; add-ins (サービスとアドイン)] の順に選択します。](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="13f56-113">[**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13f56-113">Select **Microsoft Teams**.</span></span>
    
     ![次のスクリーンショットは、Office 365 管理センターで選択した Microsoft Teams アドインのオプションを示しています。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="13f56-115">[**Select the user/license type you want to configure (構成するユーザー/ライセンスの種類を選択する)**] で [**ゲスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13f56-115">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![Microsoft Teams アドインのスクリーンショットでは、ゲスト ライセンスが選択され、Microsoft Teams オプションがオンに設定されています。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="13f56-117">[**Turn Microsoft Teams on or off for all users of this type (この種類のすべてのユーザーについて Microsoft Teams をオンまたはオフにする)**] の横にあるトグルをクリックまたはタップして [**オン**] にして組織の Teams とゲスト アクセスをオンにし、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13f56-117">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
 <span data-ttu-id="13f56-118">ゲスト アクセスの詳細については以下のビデオを視聴してください。</span><span class="sxs-lookup"><span data-stu-id="13f56-118">Watch the following videos for more details about guest access:</span></span>  

|  |  |
|---------|---------|
| <span data-ttu-id="13f56-119">Microsoft Teams でのゲスト アクセスの有効化</span><span class="sxs-lookup"><span data-stu-id="13f56-119">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/7T54KmlIHQk" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="13f56-120">Microsoft Teams でのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="13f56-120">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 