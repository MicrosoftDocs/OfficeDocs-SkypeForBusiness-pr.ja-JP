---
title: 設置型のビジネスには、マイクロソフトのチームの Skype のアップグレードします。展開 |Lync
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネス上の設置型展開チームに、Skype のアップグレードに関する考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5628b0bb382ef12580bb7bab12dca13e288fead7
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349336"
---
<span data-ttu-id="ee2f1-103">![展開に重点を置いて、アップグレードの旅の段階や実装段階](media/upgrade-banner-deployment.png "展開に重点を置いて、アップグレードの旅の段階や実装段階")</span><span class="sxs-lookup"><span data-stu-id="ee2f1-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="ee2f1-104">この資料は、アップグレード、旅の導入と展開の段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="ee2f1-105">進む前に、次のアクティビティを完了したしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="ee2f1-106">プロジェクトの利害関係者が参加しています。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ee2f1-107">プロジェクト スコープの定義</span><span class="sxs-lookup"><span data-stu-id="ee2f1-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ee2f1-108">ビジネスとチームの共存と Skype の相互運用性を理解します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ee2f1-109">アップグレード、旅を選択</span><span class="sxs-lookup"><span data-stu-id="ee2f1-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="ee2f1-110">環境を準備</span><span class="sxs-lookup"><span data-stu-id="ee2f1-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="ee2f1-111">組織の準備</span><span class="sxs-lookup"><span data-stu-id="ee2f1-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="ee2f1-112">パイロットを実施しました。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="ee2f1-113">ビジネス設置型展開で、Skype からチームへのアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="ee2f1-114">Skype のビジネスを展開している Microsoft Lync の設置型や組織がアップグレードのチームにするか、選択的にする場合この資料の指示に従います: 複数の共存モードを使用して- またはオールインワン。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="ee2f1-115">最初の手順は、Office 365 のテナントとのハイブリッド接続の設定し Skype をオンライン ビジネスのユーザーを移動し、適切な共存を割り当てるし、モードのアップグレードには。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="ee2f1-116">手順 1: ハイブリッド接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-116">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="ee2f1-117">チームにユーザーをアップグレードするためのキーの必要条件では、ハイブリッドの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="ee2f1-118">既存の Skype ビジネスまたは Lync の展開用の新しい外部接続を展開するか、Office 365 テナントにハイブリッドの関係を構成するだけ、この関数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span>

<span data-ttu-id="ee2f1-119">詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の展開](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="ee2f1-120">手順 2: Skype をオンライン ビジネスのユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-120">Step 2: Move users to Skype for Business Online</span></span>

<span data-ttu-id="ee2f1-121">ハイブリッドの設定が完了したら後、は、オンライン ビジネスの Skype にユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span>

<span data-ttu-id="ee2f1-122">詳細については、[ビジネス オンラインの Skype を施設内でのユーザーの移動](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-122">For more information, see [Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span></span>

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="ee2f1-123">手順 3: は、共存を割り当てるし、モードのアップグレード</span><span class="sxs-lookup"><span data-stu-id="ee2f1-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="ee2f1-124">Skype をオンライン ビジネスのユーザーに移動した、割り当てることができます、組織が選択したアップグレードの旅に基づく適切な共存モードです。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="ee2f1-125">詳細についてを参照してください[、共存を設定および設定をアップグレード](https://aka.ms/SkypeToTeams-SetCoexistence)し、 [TeamsUpgradePolicy: 移行と共存を管理する](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="ee2f1-126">ビジネス サーバー 2019 およびビジネス サーバー 2015 の Skype の今後の累積的な更新プログラムの Skype でことができます (ユーザーの Skype をオンライン ビジネスの移動)、ステップ 2 とステップ 3 (チームへのアップグレードのユーザー) を 1 ステップで実行します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="ee2f1-127">詳細については、ビジネス サーバー 2019 の Skype のリリース後に提供されます。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="ee2f1-128">電話システムとチームのアップグレード</span><span class="sxs-lookup"><span data-stu-id="ee2f1-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="ee2f1-129">エンタープライズ ボイスの計画を呼び出すと、電話システムにビジネスの設置を展開するため、Skype に移行しているし、Microsoft は、公衆交換電話網 (PSTN) プロバイダーになる場合、電話番号を完了したことを前提として、移植-チームにユーザーをアップグレードすると、チームへのインバウンドの PSTN 通話は自動的に移行します。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-129">If you’re transitioning your Skype for Business on-premises deployment from enterprise voice to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="ee2f1-130">計画を呼び出すことがない場合は、マイクロソフト電話システム直接ルーティングするのには、エンタープライズ ボイスの展開に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="ee2f1-131">チームにユーザーをアップグレードするには、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee2f1-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>