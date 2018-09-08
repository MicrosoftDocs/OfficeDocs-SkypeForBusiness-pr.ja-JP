---
title: Microsoft Teams でのアプリの管理設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: 外部アプリのサイドロードなど、Microsoft Teams でのアプリの許可と有効化について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1a7d10be12c75b3d25737aa770c94e5a540e683
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881918"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="95d9a-103">Microsoft Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="95d9a-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="95d9a-p101">アプリケーションは、タブ、コネクタ、ボット、またはサードパーティ製のサービスによって提供されるこれら 3 つの任意の組み合わせです。制御をする外部のサードパーティのアプリケーションを許可する Office 365 の管理ページで構成可能なチーム管理ポリシーがあります。これらのポリシーでは、読み込み側のアプリケーションを許可するかどうか、どのアプリが許可され、許可されていない外部のアプリケーションの新しい動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="95d9a-p101">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="95d9a-107">Teams のアプリについての管理設定を管理するには、Office 365 管理センターに移動して、[**設定**] > [**サービスとアドイン**] を開いて、[**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95d9a-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="95d9a-108">Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="95d9a-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="95d9a-109">アプリの管理設定の詳細については、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="95d9a-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="95d9a-110">Managing the App Experience in Microsoft Teams (Microsoft Teams でのアプリの機能と操作性を管理する)</span><span class="sxs-lookup"><span data-stu-id="95d9a-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="95d9a-111">Allow external apps in Teams (Teams で外部アプリを許可する)</span><span class="sxs-lookup"><span data-stu-id="95d9a-111">Allow external apps in Teams</span></span>

<span data-ttu-id="95d9a-112">既定では、[**Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)**] がオンになり、すべてのアプリが選択されます。</span><span class="sxs-lookup"><span data-stu-id="95d9a-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="95d9a-113">このスイッチをオフにすると、すべての外部サード パーティ アプリが無効になります。</span><span class="sxs-lookup"><span data-stu-id="95d9a-113">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="95d9a-114">Enable new external apps by default (既定で新しい外部アプリを有効にする)</span><span class="sxs-lookup"><span data-stu-id="95d9a-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="95d9a-115">:トロフィー: ベスト プラクティス: 外部アプリを個別に管理する</span><span class="sxs-lookup"><span data-stu-id="95d9a-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="95d9a-116">一部のアプリをオンにする (その他のアプリはオフにする) には、[**Allow sideloading of external apps (外部アプリのサイドロードを許可する)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="95d9a-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="95d9a-117">自分のユーザーに使用されないようにするアプリをすべてオフにします。</span><span class="sxs-lookup"><span data-stu-id="95d9a-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="95d9a-118">オプション: [**Enable new external apps by default (既定で新しい外部アプリを有効にする)**] をオフにします (新しいアプリを制御する場合)。</span><span class="sxs-lookup"><span data-stu-id="95d9a-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="95d9a-119">、マイクロソフトによって作成されたものなど、既定のアプリケーションは、**既定では、新しい外部アプリケーションを有効にする**設定の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="95d9a-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="95d9a-120">マイクロソフトからリリースされたときに既定では、新しいアプリケーションが有効になります。</span><span class="sxs-lookup"><span data-stu-id="95d9a-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="95d9a-121">このスイッチがオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されるとそれをすぐにアクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="95d9a-121">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="95d9a-122">Teams アプリ カタログを開くには、Teams の下部にある [**ストア**] をクリックして、[**アプリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95d9a-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="95d9a-123">どのアプリを利用できるようにするかを制御する場合は、このスイッチをオフにします。</span><span class="sxs-lookup"><span data-stu-id="95d9a-123">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="95d9a-124">これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95d9a-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="95d9a-125">サイドローディングは、チームに直接 zip ファイルをアップロードすることによって Teams にアプリを追加する方法です。</span><span class="sxs-lookup"><span data-stu-id="95d9a-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="95d9a-126">サイドローディングにより、開発途中のアプリをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="95d9a-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="95d9a-127">内部使用に限定するアプリを構築して、Office ストアの Teams アプリ カタログに送らずにチーム内で共有することができます。</span><span class="sxs-lookup"><span data-stu-id="95d9a-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="95d9a-128">チーム所有者またはアクセス許可が付与されたメンバーのみが、アプリを Teams にサイドロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="95d9a-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![テナント全体の設定の展開されたアプリケーションのスクリーン ショットです。](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="95d9a-130">アプリのパッケージの作成とアップロード</span><span class="sxs-lookup"><span data-stu-id="95d9a-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="95d9a-131">アプリケーションに関する詳細については、[チーム開発のアプリケーション](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95d9a-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



