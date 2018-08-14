---
title: ビジネスのハイブリッド展開するため、Skype からチームのチームで Microsoft にアップグレードします。
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネスのハイブリッド展開するため、Skype からチームへのアップグレードに関する考慮事項
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 314a7f1ef6a74734d99839ea2aab4c23fcd58057
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2018
ms.locfileid: "21148339"
---
<span data-ttu-id="e2266-103">![展開に重点を置いて、アップグレードの旅の段階や実装段階](media/upgrade-banner-deployment.png "展開に重点を置いて、アップグレードの旅の段階や実装段階")</span><span class="sxs-lookup"><span data-stu-id="e2266-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e2266-104">この資料は、アップグレード、旅の導入と展開の段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="e2266-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e2266-105">進む前に、次のアクティビティを完了したしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2266-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="e2266-106">プロジェクトの利害関係者が参加しています。</span><span class="sxs-lookup"><span data-stu-id="e2266-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="e2266-107">プロジェクト スコープの定義</span><span class="sxs-lookup"><span data-stu-id="e2266-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="e2266-108">ビジネスとチームの共存と Skype の相互運用性を理解します。</span><span class="sxs-lookup"><span data-stu-id="e2266-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="e2266-109">アップグレード、旅を選択</span><span class="sxs-lookup"><span data-stu-id="e2266-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="e2266-110">環境を準備</span><span class="sxs-lookup"><span data-stu-id="e2266-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="e2266-111">組織の準備</span><span class="sxs-lookup"><span data-stu-id="e2266-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="e2266-112">パイロットを実施しました。</span><span class="sxs-lookup"><span data-stu-id="e2266-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="e2266-113">ビジネスのハイブリッド展開するため、Skype からチームへのアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e2266-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="e2266-114">Skype のビジネスを展開しているや Microsoft Lync の設置型と、Office 365 のテナントのハイブリッド展開を構成して、組織がアップグレードのチームにするか、選択的にする場合この資料の指示に従います: 複数を使用して、共存モード、またはオールインワン。</span><span class="sxs-lookup"><span data-stu-id="e2266-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="e2266-115">いずれかのアップグレードの旅 (それらは既にホーム サーバーの場合オンライン) は、オンライン ビジネスの Skype にユーザーを移動し、それらの適切な共存およびアップグレード モードが必要です。</span><span class="sxs-lookup"><span data-stu-id="e2266-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="e2266-116">手順 1: Skype をオンライン ビジネスのユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="e2266-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="e2266-117">この手順は、オンプレミスで現在のホーム ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e2266-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="e2266-118">ビジネス オンラインの Skype にこれらのユーザーを移動する方法の詳細については、[上の Skype ビジネスをオンラインにするには、社内設置型からユーザーを移動](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2266-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="e2266-119">手順 2: は、共存を割り当てるし、モードのアップグレード</span><span class="sxs-lookup"><span data-stu-id="e2266-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="e2266-120">Skype をオンライン ビジネスのユーザーに移動した、割り当てることができます、組織が選択したアップグレードの旅に基づく適切な共存モードです。</span><span class="sxs-lookup"><span data-stu-id="e2266-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="e2266-121">詳細についてを参照してください[、共存を設定および設定をアップグレード](https://aka.ms/SkypeToTeams-SetCoexistence)し、 [TeamsUpgradePolicy: 移行と共存を管理する](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="e2266-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="e2266-122">ビジネス サーバー 2019 およびビジネス サーバー 2015 の Skype の今後の累積的な更新プログラムの Skype でことができます (ユーザーの Skype をオンライン ビジネスの移動) ステップ 1 とステップ 2 (チームへのアップグレードのユーザー) を 1 ステップで実行します。</span><span class="sxs-lookup"><span data-stu-id="e2266-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="e2266-123">詳細については、ビジネス サーバー 2019 の Skype のリリース後に提供されます。</span><span class="sxs-lookup"><span data-stu-id="e2266-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e2266-124">電話システムとチームのアップグレード</span><span class="sxs-lookup"><span data-stu-id="e2266-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e2266-125">ビジネスのハイブリッド展開計画を呼び出すと、電話システムには、Skype に移行しているし、Microsoft は、公衆交換電話網 (PSTN) プロバイダーになる場合、電話番号の移植が完了したことを前提として、-にユーザーをアップグレードします。チームは、チームを呼び出す受信の PSTN と自動的に遷移させます。</span><span class="sxs-lookup"><span data-stu-id="e2266-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="e2266-126">計画を呼び出すことがない、または、既存の PSTN 接続のプロバイダーを使用する、エンタープライズ ボイス展開に移行する必要があります- または、既存を使用するハイブリッド ボイスの展開設置型展開またはクラウド コネクタ エディション-にマイクロソフトの電話システムでは、ルーティングを指示します。</span><span class="sxs-lookup"><span data-stu-id="e2266-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="e2266-127">チームにユーザーをアップグレードするには、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2266-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
