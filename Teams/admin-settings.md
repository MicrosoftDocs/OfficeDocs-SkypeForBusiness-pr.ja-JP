---
title: "Microsoft Teams でのアプリの管理設定 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "外部アプリのサイドロードなど、Microsoft Teams でのアプリの許可と有効化について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 19ed683382cd06d0b0c33686391e012f35f35fc4
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="6b8b7-103">Microsoft Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="6b8b7-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="6b8b7-p101">このセクションでは、単一のサードパーティ サービスによって提供されるタブ、コネクタ、ボット、これらの機能を組み合わせたものをアプリと言います。Office 365 管理ポータルで構成可能な管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。このポリシーでは、許可または禁止するアプリ、新しい外部アプリの動作、アプリのサイドロードを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b8b7-p101">In this section, we refer to tabs, connectors, and bots, or any combination of these capabilities, provided by a single third-party service as Apps. There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

<span data-ttu-id="6b8b7-107">**Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)**</span><span class="sxs-lookup"><span data-stu-id="6b8b7-107">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="6b8b7-p102">既定では、選択したすべてのアプリに対して [Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)] が有効になります。このポリシーを「**オフ**」にすると、すべての外部サードパーティ アプリが無効化されます。細かく調整して特定の外部アプリを有効にするには、アプリを個別にオフにして無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b8b7-p102">By default, allow external apps in Microsoft Teams is enabled with all apps selected. When turning this policy to **“Off”**, then all external third-party apps are disabled. You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="6b8b7-111">**Enable new external apps by default (既定で新しい外部アプリを有効にする)**</span><span class="sxs-lookup"><span data-stu-id="6b8b7-111">**Enable new external apps by default**</span></span>

<span data-ttu-id="6b8b7-p103">Teams アプリ カタログに送られる新しいアプリについて、このスイッチはテナントのユーザーに対して利用可能にするかどうかを制御します。既定では、このポリシーは「**オン**」に設定されています。ユーザーはアプリがチームのアプリ カタログに追加されると同時にそのアプリにアクセスできます。Teams での使用を許可する前にアプリを検証する場合は、このポリシーを「**オフ**」に設定します。「**オフ**」に設定する場合は、新しく追加されるアプリを定期的に評価して、それらのアプリがもたらす最新の革新的機能や追加機能をユーザーが利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6b8b7-p103">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant. By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog. If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.** Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="6b8b7-116">**Allow sideloading of external apps (外部アプリのサイドローディングを許可する)**</span><span class="sxs-lookup"><span data-stu-id="6b8b7-116">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="6b8b7-p104">権限が与えられたチーム所有者またはメンバーのみが Microsoft Teams でアプリをサイドロードできます。Microsoft Teams でアプリをサイドロードすると、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="6b8b7-p104">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams. Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="6b8b7-119">Microsoft に送信する前にアプリをテストできる</span><span class="sxs-lookup"><span data-stu-id="6b8b7-119">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="6b8b7-120">アプリを Office ストアに送信することなく、組織内のユーザーに直接に提供できる.</span><span class="sxs-lookup"><span data-stu-id="6b8b7-120">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="6b8b7-121">Microsoft Teams でのアプリのサイドロードについて詳しくは、「[Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631)」(英語版) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="6b8b7-121">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
