---
title: Office 365 組織でマイクロソフトのチーム機能を管理します。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 有効または無効のタブ、コネクタ、ボット、または 3 つの任意の組み合わせを含む、Office 365 の組織でアプリケーションをマイクロソフトのチームにする方法を説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86fa8178b52c621c664afc49edd4f8d2c81c1fea
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882054"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="5a987-103">Office 365 組織でマイクロソフトのチーム機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="5a987-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="5a987-104">チームのすべての設定は、新しいマイクロソフトのチームとビジネス管理センターの Skype をすぐに移行されます。</span><span class="sxs-lookup"><span data-stu-id="5a987-104">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="5a987-105">チームがこの機能を Office 365 の管理センターで管理されているとは、アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="5a987-105">The only Teams feature that is managed in the Office 365 admin center is apps.</span></span> 

<span data-ttu-id="5a987-106">特に明記されていない場合を除き、オプションの規定値はオンです。</span><span class="sxs-lookup"><span data-stu-id="5a987-106">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="5a987-107">Teams についての管理設定を管理するには、Office 365 管理センターに移動して、[**設定**] > [**サービスとアドイン**] を開いて、[**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a987-107">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="5a987-108">Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="5a987-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="5a987-109">Office 365 テナント全体の設定</span><span class="sxs-lookup"><span data-stu-id="5a987-109">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="5a987-110">**テナント全体の設定**] を有効にするまたはアプリケーションを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5a987-110">In **Tenant-wide settings**, you can turn on or turn off apps.</span></span>

<span data-ttu-id="5a987-111">Teams の**テナント全体の設定**を編集するには、Office 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a987-111">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="5a987-112">[**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Teams**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5a987-112">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

## <a name="apps"></a><span data-ttu-id="5a987-113">アプリ</span><span class="sxs-lookup"><span data-stu-id="5a987-113">Apps</span></span>

<span data-ttu-id="5a987-114">アプリとは、サードパーティのサービスによって提供されるタブ、コネクタ、ボットという 3 つの要素のあらゆる組み合わせで構成されているものです。</span><span class="sxs-lookup"><span data-stu-id="5a987-114">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="5a987-115">Office 365 管理センターで構成可能な Teams 管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="5a987-115">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="5a987-116">これらのポリシーでは、読み込み側のアプリケーションを許可するかどうか、どのアプリが許可され、許可されていない外部のアプリケーションの新しい動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5a987-116">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="5a987-117">[**アプリ**] の下で、組織の次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a987-117">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![[アプリ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="5a987-119">**Microsoft Teams の外部アプリを許可する**: このスイッチがオンになると、ユーザーは Office 365 テナントで利用できるタブやボットを 追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5a987-119">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![[アプリ] セクションの外部アプリの許可コントロールのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="5a987-121">**既定で新しい外部アプリを有効にする**: このスイッチがオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されるとそれをすぐにアクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="5a987-121">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="5a987-122">新しいアプリに対する制御を行う場合はこのスイッチをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5a987-122">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="5a987-123">これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a987-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="5a987-124">**外部アプリのサイドロードを許可する:** このスイッチがオンになると、ユーザーはカスタムのボットやタブをインストールして有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a987-124">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="5a987-125">詳細については、[Teams でのアプリの管理設定](admin-settings.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5a987-125">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

