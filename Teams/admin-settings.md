---
title: "Microsoft Teams でのアプリの管理設定"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "外部アプリのサイドロードなど、Microsoft Teams でのアプリの許可と有効化について説明します。"
ms.openlocfilehash: 4265866bb346da1aa773d337d02fc1c11149f579
ms.sourcegitcommit: ee1c79b6d6d73e5fc702fe55b9e5aee8a7aae793
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="94dbc-103">Microsoft Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="94dbc-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="94dbc-p101">アプリとは、単一のサードパーティ サービスによって提供されるタブ、コネクタ、ボットという 3 つの要素のあらゆる組み合わせで構成されているものです。Office 365 管理センターで構成可能な管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。このポリシーでは、許可または禁止するアプリ、新しい外部アプリの動作、アプリのサイドロードを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="94dbc-p101">In this section, we refer to tabs, connectors, and bots, or any combination of these capabilities, provided by a single third-party service as Apps. There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="94dbc-107">Teams のアプリについての管理設定を管理するには、Office 365 管理センターに移動して、[**設定**] > [**サービスとアドイン**] を開いて、[**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94dbc-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="94dbc-108">Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="94dbc-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="94dbc-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="94dbc-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

<span data-ttu-id="94dbc-110">**Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)**</span><span class="sxs-lookup"><span data-stu-id="94dbc-110">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="94dbc-p103">既定では、選択したすべてのアプリに対して [Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)] が有効になります。このポリシーを「**オフ**」にすると、すべての外部サードパーティ アプリが無効化されます。細かく調整して特定の外部アプリを有効にするには、アプリを個別にオフにして無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="94dbc-p103">By default, allow external apps in Microsoft Teams is enabled with all apps selected. When turning this policy to **“Off”**, then all external third-party apps are disabled. You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="94dbc-114">**Enable new external apps by default (既定で新しい外部アプリを有効にする)**</span><span class="sxs-lookup"><span data-stu-id="94dbc-114">**Enable new external apps by default**</span></span>

<span data-ttu-id="94dbc-p104">Teams アプリ カタログに送られる新しいアプリについて、このスイッチはテナントのユーザーに対して利用可能にするかどうかを制御します。既定では、このポリシーは「**オン**」に設定されています。ユーザーはアプリがチームのアプリ カタログに追加されると同時にそのアプリにアクセスできます。Teams での使用を許可する前にアプリを検証する場合は、このポリシーを「**オフ**」に設定します。「**オフ**」に設定する場合は、新しく追加されるアプリを定期的に評価して、それらのアプリがもたらす最新の革新的機能や追加機能をユーザーが利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="94dbc-p104">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant. By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog. If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.** Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="94dbc-119">**Allow sideloading of external apps (外部アプリのサイドローディングを許可する)**</span><span class="sxs-lookup"><span data-stu-id="94dbc-119">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="94dbc-p105">権限が与えられたチーム所有者またはメンバーのみが Microsoft Teams でアプリをサイドロードできます。Microsoft Teams でアプリをサイドロードすると、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="94dbc-p105">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams. Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="94dbc-122">Microsoft に送信する前にアプリをテストできる</span><span class="sxs-lookup"><span data-stu-id="94dbc-122">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="94dbc-123">アプリを Office ストアに送信することなく、組織内のユーザーに直接に提供できる.</span><span class="sxs-lookup"><span data-stu-id="94dbc-123">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="94dbc-124">Microsoft Teams でのアプリのサイドロードについて詳しくは、「[Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631)」(英語版) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="94dbc-124">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Microsoft Teams の設定の [アプリ] セクションのスクリーンショット](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
