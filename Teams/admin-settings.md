---
title: "Microsoft Teams でのアプリの管理設定"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "外部アプリのサイドロードなど、Microsoft Teams でのアプリの許可と有効化について説明します。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4cdca98cca13ffb49575b808a5cfa82f784d1752
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="0f525-103">Microsoft Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="0f525-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="0f525-p101">アプリとは、単一のサードパーティ サービスによって提供されるタブ、コネクタ、ボットという 3 つの要素のあらゆる組み合わせで構成されているものです。Office 365 管理センターで構成可能な Teams 管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。このポリシーでは、許可または禁止するアプリ、新しい外部アプリの動作、アプリのサイドロードを許可するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0f525-p101">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="0f525-107">Teams のアプリについての管理設定を管理するには、Office 365 管理センターに移動して、[**設定**] > [**サービスとアドイン**] を開いて、[**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f525-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="0f525-108">Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。</span><span class="sxs-lookup"><span data-stu-id="0f525-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="0f525-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="0f525-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="0f525-110">Allow external apps in Teams (Teams で外部アプリを許可する)</span><span class="sxs-lookup"><span data-stu-id="0f525-110">Allow external apps in Microsoft Teams</span></span>

<span data-ttu-id="0f525-111">既定では、[**Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)**] がオンになり、すべてのアプリが選択されます。</span><span class="sxs-lookup"><span data-stu-id="0f525-111">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="0f525-112">このスイッチをオフにすると、すべての外部サード パーティ アプリが無効になります。</span><span class="sxs-lookup"><span data-stu-id="0f525-112">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="0f525-113">Enable new external apps by default (既定で新しい外部アプリを有効にする)</span><span class="sxs-lookup"><span data-stu-id="0f525-113">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="0f525-114">:トロフィー: ベスト プラクティス: 外部アプリを個別に管理する</span><span class="sxs-lookup"><span data-stu-id="0f525-114">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="0f525-115">一部のアプリをオンにする (その他のアプリはオフにする) には、[**Allow sideloading of external apps (外部アプリのサイドロードを許可する)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="0f525-115">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="0f525-116">自分のユーザーに使用されないようにするアプリをすべてオフにします。</span><span class="sxs-lookup"><span data-stu-id="0f525-116">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="0f525-117">オプション: [**Enable new external apps by default (既定で新しい外部アプリを有効にする)**] をオフにします (新しいアプリを制御する場合)。</span><span class="sxs-lookup"><span data-stu-id="0f525-117">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

<span data-ttu-id="0f525-118">このスイッチがオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されるとそれをすぐにアクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="0f525-118">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="0f525-119">Teams アプリ カタログを開くには、Teams の下部にある [**ストア**] をクリックして、[**アプリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f525-119">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="0f525-120">どのアプリを利用できるようにするかを制御する場合は、このスイッチをオフにします。</span><span class="sxs-lookup"><span data-stu-id="0f525-120">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="0f525-121">これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f525-121">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="0f525-122">サイドローディングは、チームに直接 zip ファイルをアップロードすることによって Teams にアプリを追加する方法です。</span><span class="sxs-lookup"><span data-stu-id="0f525-122">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="0f525-123">サイドローディングにより、開発途中のアプリをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f525-123">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="0f525-124">内部使用に限定するアプリを構築して、Office ストアの Teams アプリ カタログに送らずにチーム内で共有することができます。</span><span class="sxs-lookup"><span data-stu-id="0f525-124">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="0f525-125">チーム所有者またはアクセス許可が付与されたメンバーのみが、アプリを Teams にサイドロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f525-125">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![Microsoft Teams の設定の [アプリ] セクションのスクリーンショット](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png) 

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="0f525-127">アプリのパッケージの作成とアップロード</span><span class="sxs-lookup"><span data-stu-id="0f525-127">Creating and uploading app packages</span></span> 

<span data-ttu-id="0f525-128">アプリの詳細については、「[Teams 用のアプリを開発する](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f525-128">To learn more about apps, read [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



