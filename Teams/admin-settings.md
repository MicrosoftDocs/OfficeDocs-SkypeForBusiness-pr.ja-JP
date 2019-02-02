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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: da73768f69159c32543d0843139facc2b9ef4f9a
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706356"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="d5462-103">Microsoft Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="d5462-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="d5462-104">アプリケーションは、タブ、コネクタ、ボット、またはチーム (ファースト パーティのアプリケーションとも呼ばれる既定アプリケーション) または (外部のアプリケーションとも呼ばれます)、サード パーティによって提供されるこれら 3 つの任意の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d5462-104">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, and also known as default apps) or by a third-party (also known as external apps).</span></span> <span data-ttu-id="d5462-105">Microsoft 365 管理センターを有効にして既定のアプリケーションを無効にして外部のアプリケーションを制御する設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d5462-105">In the Microsoft 365 admin center, you can enable and disable default apps and configure settings to control external apps.</span></span> <span data-ttu-id="d5462-106">これらの設定を使用して、読み込み側のアプリケーションを許可するかどうか、外部コンテンツが許可され、許可されていない外部のアプリケーションの新しい動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d5462-106">These settings let you specify which external apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

 <span data-ttu-id="d5462-107">チームでのアプリケーションの管理設定を管理する Microsoft 365 の管理ページに移動し、**設定**を選択して > **サービス & アドイン** > **マイクロソフトのチーム**です。</span><span class="sxs-lookup"><span data-stu-id="d5462-107">To manage admin settings for apps in Teams, go to the Microsoft 365 admin center and choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="d5462-108">Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="d5462-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="d5462-109">アプリの管理設定の詳細については、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d5462-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="d5462-110">Managing the App Experience in Microsoft Teams (Microsoft Teams でのアプリの機能と操作性を管理する)</span><span class="sxs-lookup"><span data-stu-id="d5462-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="d5462-111">Allow external apps in Teams (Teams で外部アプリを許可する)</span><span class="sxs-lookup"><span data-stu-id="d5462-111">Allow external apps in Teams</span></span>

<span data-ttu-id="d5462-112">既定では、[**Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)**] がオンになり、すべてのアプリが選択されます。</span><span class="sxs-lookup"><span data-stu-id="d5462-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="d5462-113">この設定をオフにすると、外部のサードパーティのアプリケーションをすべて無効となります。</span><span class="sxs-lookup"><span data-stu-id="d5462-113">If you turn off this setting, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="d5462-114">Enable new external apps by default (既定で新しい外部アプリを有効にする)</span><span class="sxs-lookup"><span data-stu-id="d5462-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="d5462-115">:トロフィー: ベスト プラクティス: 外部アプリを個別に管理する</span><span class="sxs-lookup"><span data-stu-id="d5462-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="d5462-116">一部のアプリをオンにする (その他のアプリはオフにする) には、[**Allow sideloading of external apps (外部アプリのサイドロードを許可する)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d5462-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="d5462-117">自分のユーザーに使用されないようにするアプリをすべてオフにします。</span><span class="sxs-lookup"><span data-stu-id="d5462-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="d5462-118">オプション: [**Enable new external apps by default (既定で新しい外部アプリを有効にする)**] をオフにします (新しいアプリを制御する場合)。</span><span class="sxs-lookup"><span data-stu-id="d5462-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="d5462-119">、マイクロソフトによって作成されたものなど、既定のアプリケーションは、**既定では、新しい外部アプリケーションを有効にする**設定の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="d5462-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="d5462-120">マイクロソフトからリリースされたときに既定では、新しいアプリケーションが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d5462-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="d5462-121">この設定をオンにすると、新しいアプリのユーザーがアクティブにチーム アプリケーション カタログに追加するいるとすぐに。</span><span class="sxs-lookup"><span data-stu-id="d5462-121">When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="d5462-122">Teams アプリ カタログを開くには、Teams の下部にある [**ストア**] をクリックして、[**アプリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5462-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="d5462-123">どのアプリが利用できるかを制御する場合は、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d5462-123">If you want to control which apps are available, turn off this setting.</span></span> <span data-ttu-id="d5462-124">これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5462-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="d5462-125">サイドローディングは、チームに直接 zip ファイルをアップロードすることによって Teams にアプリを追加する方法です。</span><span class="sxs-lookup"><span data-stu-id="d5462-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="d5462-126">サイドローディングにより、開発途中のアプリをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5462-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="d5462-127">内部使用に限定するアプリを構築して、Office ストアの Teams アプリ カタログに送らずにチーム内で共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d5462-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="d5462-128">チーム所有者またはアクセス許可が付与されたメンバーのみが、アプリを Teams にサイドロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5462-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

<span data-ttu-id="d5462-129">![拡張の外部アプリケーションでの画面です]。(media/teams-tenant-wide-settings-external-apps.png "外部のアプリケーションを示す展開された外部のアプリケーション セクションのスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="d5462-129">![Screen shot of the expanded External Apps section.](media/teams-tenant-wide-settings-external-apps.png "Screen shot of the expanded External Apps section showing external apps")</span></span>

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="d5462-130">アプリのパッケージの作成とアップロード</span><span class="sxs-lookup"><span data-stu-id="d5462-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="d5462-131">アプリケーションに関する詳細については、[チーム開発のアプリケーション](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5462-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



