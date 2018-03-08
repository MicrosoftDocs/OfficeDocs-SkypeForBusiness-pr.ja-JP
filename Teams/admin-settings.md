---
title: "Microsoft のチームでアプリの管理設定"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "許可して、外部のアプリのサイドの読み込みを含む Microsoft チームでアプリを有効にする方法を学習します。"
ms.openlocfilehash: 4265866bb346da1aa773d337d02fc1c11149f579
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="11e1f-103">Microsoft のチームでアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="11e1f-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="11e1f-p101">アプリは、タブ、コネクタ、コンポーネント、またはサード パーティ サービスによって提供されるこれら 3 つの任意の組み合わせです。どの外部サード パーティのアプリが許可されるコントロールには、Office 365 管理センターで設定できる管理ポリシーがあります。これらのポリシーを使用して、サイドの読み込みのアプリを許可するかどうかとなるアプリの許可、許可されない場合は、新しい外部アプリの動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="11e1f-p101">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="11e1f-p102">チームでアプリの管理設定を管理するには、Office 365 管理センターに移動し、**設定**] を開きます > **サービスとアドイン**]、[ **Microsoft チーム**を選択します。Office 365 の管理者としてサインインしている場合は、このリンクが行わがあります。</span><span class="sxs-lookup"><span data-stu-id="11e1f-p102">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**. If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="11e1f-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="11e1f-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

<span data-ttu-id="11e1f-110">**Microsoft のチームで外部のアプリを許可します。**</span><span class="sxs-lookup"><span data-stu-id="11e1f-110">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="11e1f-p103">既定では、マイクロソフトのチームで外部のアプリが選択されているすべてのアプリを使用して有効になっているを許可します。このポリシーに**""をオフ**にすると、[すべての外部サード パーティのアプリは無効になります。詳細を取得しを有効にして、特定のアプリを個別に無効にする] をオフにする外部のアプリを許可できます。</span><span class="sxs-lookup"><span data-stu-id="11e1f-p103">By default, allow external apps in Microsoft Teams is enabled with all apps selected. When turning this policy to **“Off”**, then all external third-party apps are disabled. You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="11e1f-114">**既定で新しい外部アプリを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="11e1f-114">**Enable new external apps by default**</span></span>

<span data-ttu-id="11e1f-p104">常にこのテナントのユーザーは利用できませんかに関係なくチーム アプリ カタログ] このスイッチを制御する新しいアプリが送信されます。既定では、このポリシーは、 **「上」**ユーザーがチームのアプリ カタログに追加されると、すぐに、アプリにアクセスするに設定されます。アプリを許可すると、チームで使用する前に検証する場合は、[このポリシー設定**オフ**注意してください] に設定する場合は、 **「無効」**新しくを評価する必要があります追加されたアプリを定期的にユーザーのメリットを享受最新の新機能とアプリの追加を行っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="11e1f-p104">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant. By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog. If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.** Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="11e1f-119">**外部のアプリのサイドの読み込みを許可します。**</span><span class="sxs-lookup"><span data-stu-id="11e1f-119">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="11e1f-p105">チームの所有者または、アクセス許可が与えられているメンバーのみが側でロード アプリ Microsoft チームに。Microsoft チームに側の読み込みのアプリのいくつかの利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11e1f-p105">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams. Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="11e1f-122">Microsoft に送信する前にアプリをテストする機能</span><span class="sxs-lookup"><span data-stu-id="11e1f-122">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="11e1f-123">Office ストアに送信することがなく、組織内のユーザーに直接アプリを提供します。</span><span class="sxs-lookup"><span data-stu-id="11e1f-123">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="11e1f-124">Microsoft チームにアプリを読み込む側の詳細についてを参照してください:[側の読み込みアプリをチームに](https://go.microsoft.com/fwlink/?linkid=854631)します。</span><span class="sxs-lookup"><span data-stu-id="11e1f-124">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Microsoft チーム設定の [アプリ] セクションのスクリーン ショット。](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
