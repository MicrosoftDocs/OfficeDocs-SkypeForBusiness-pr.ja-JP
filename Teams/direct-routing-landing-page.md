---
title: 電話システムのダイレクト ルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 詳細については、「構成」、「基本的な展開の決定事項」、「ボイスルーティングの考慮事項」などのダイレクトルーティングについて説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c5120f60778879be0978cb80c56daf99e5b5a38
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031823"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="ea788-103">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="ea788-103">Phone System Direct Routing</span></span>

<span data-ttu-id="ea788-104">[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="ea788-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="ea788-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="ea788-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="ea788-106">[会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea788-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="ea788-107">これで、クラウド音声のワークロードを追加する準備ができました。電話システムのダイレクトルーティングを使用して、PSTN (公衆交換電話網) 接続用の独自のテレフォニーキャリアを使用することにしました。</span><span class="sxs-lookup"><span data-stu-id="ea788-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="ea788-108">直接ルーティングを使用すると、ほぼすべてのテレフォニーキャリアで電話システムを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ea788-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="ea788-109">この記事では、組織のニーズに基づいて、直接ルーティングを行う場合の主要な展開と、検討する必要があるその他の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea788-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="ea788-110">また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="ea788-111">直接ルーティングの詳細については、こちらを参照してください</span><span class="sxs-lookup"><span data-stu-id="ea788-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="ea788-112">次の記事では、電話システムのダイレクトルーティングを構成して使用する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ea788-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="ea788-113">直接ルーティングを構成するには、PSTN ルーティングの設計を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea788-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="ea788-114">直接ルーティングを計画して構成する方法については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="ea788-115">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="ea788-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="ea788-116">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="ea788-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="ea788-117">ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト</span><span class="sxs-lookup"><span data-stu-id="ea788-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="ea788-118">ダイレクト ルーティングの監視とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ea788-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="ea788-119">さらに、必要に応じて、次の記事も参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="ea788-120">複数のテナントにセッション ボーダー コントローラーを構成する</span><span class="sxs-lookup"><span data-stu-id="ea788-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="ea788-121">ダイレクト ルーティングに移行する</span><span class="sxs-lookup"><span data-stu-id="ea788-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="ea788-122">PSTN 接続を使用するハイブリッド環境でのユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="ea788-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="ea788-123">直接ルーティングの詳細については、次のセッションをご覧ください。 [Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="ea788-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="ea788-124">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="ea788-124">Core deployment decisions</span></span>

<span data-ttu-id="ea788-125">これは、直接ルーティングについて考慮するべき主要な決定事項です。</span><span class="sxs-lookup"><span data-stu-id="ea788-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="ea788-126">確認事項</span><span class="sxs-lookup"><span data-stu-id="ea788-126">Ask yourself</span></span>|<span data-ttu-id="ea788-127">アクション</span><span class="sxs-lookup"><span data-stu-id="ea788-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="ea788-128">どのユーザーが直接ルーティングを有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="ea788-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="ea788-129">詳細については、「 [ユーザーが直接ルーティングサービスを有効にする](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="ea788-130">直接ルーティングのために必要なライセンスはありますか?</span><span class="sxs-lookup"><span data-stu-id="ea788-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="ea788-131">詳細については、「 [ライセンスとその他の要件](direct-routing-plan.md#licensing-and-other-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="ea788-132">セッションボーダーコントローラー (SBC) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ea788-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="ea788-133">直接ルーティングでは、独自のセッションボーダーコントローラー (SBC) を直接電話システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="ea788-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="ea788-134">認定された SBCs の一覧については、 [サポートされているセッション境界コントローラー](direct-routing-border-controllers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="ea788-135">確認事項</span><span class="sxs-lookup"><span data-stu-id="ea788-135">Ask yourself</span></span>|<span data-ttu-id="ea788-136">アクション</span><span class="sxs-lookup"><span data-stu-id="ea788-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="ea788-137">SBCs はどこで展開されますか?</span><span class="sxs-lookup"><span data-stu-id="ea788-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="ea788-138">詳細については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="ea788-139">複数のテナントがある場合</span><span class="sxs-lookup"><span data-stu-id="ea788-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="ea788-140">詳細については、「 [複数のテナントのセッション境界コントローラーを構成](direct-routing-sbc-multiple-tenants.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="ea788-141">音声ルーティングに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ea788-141">Voice routing considerations</span></span>

<span data-ttu-id="ea788-142">特定の SBCs への通話をルーティングするように電話システムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea788-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="ea788-143">確認事項</span><span class="sxs-lookup"><span data-stu-id="ea788-143">Ask yourself</span></span>|<span data-ttu-id="ea788-144">アクション</span><span class="sxs-lookup"><span data-stu-id="ea788-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="ea788-145">作成する必要がある音声ルーティングポリシー、PSTN 使用状況、および音声ルート</span><span class="sxs-lookup"><span data-stu-id="ea788-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="ea788-146">音声ルーティング情報については、「 [ボイスルーティングを構成する](direct-routing-configure.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ea788-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="ea788-147">定義した音声ルーティングポリシーにはどのユーザーが割り当てられますか。</span><span class="sxs-lookup"><span data-stu-id="ea788-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="ea788-148">「 [音声ルーティングを構成する](direct-routing-configure.md)」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="ea788-149">TeamsUpgradePolicy を使用して、チームクライアントで着信通話を確実に行う</span><span class="sxs-lookup"><span data-stu-id="ea788-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="ea788-150">直接ルーティングは、Microsoft Teams でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ea788-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="ea788-151">直接ルーティングを使用して PSTN 通話を受信するには、TeamsUpgradePolicy を構成して、Teams で確実に着信を受信できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea788-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="ea788-152">ユーザーは、チーム専用モードである必要があります。これには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ea788-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="ea788-153">確認事項</span><span class="sxs-lookup"><span data-stu-id="ea788-153">Ask yourself</span></span>|<span data-ttu-id="ea788-154">アクション</span><span class="sxs-lookup"><span data-stu-id="ea788-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="ea788-155">チーム専用モードの意味を教えてください。</span><span class="sxs-lookup"><span data-stu-id="ea788-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="ea788-156">詳細については、「 [Skype For business で Teams を使用する組織向けの移行と相互運用性](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)に関するガイダンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="ea788-157">その他の展開に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ea788-157">Additional deployment considerations</span></span>

<span data-ttu-id="ea788-158">組織のニーズと構成に基づいて、次のことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="ea788-159">確認事項</span><span class="sxs-lookup"><span data-stu-id="ea788-159">Ask yourself</span></span>| <span data-ttu-id="ea788-160">アクション</span><span class="sxs-lookup"><span data-stu-id="ea788-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="ea788-161">ハイブリッド接続が構成されている既存の Skype for Business Server 展開がありますか?</span><span class="sxs-lookup"><span data-stu-id="ea788-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="ea788-162">ハイブリッド環境でのユーザーアカウントのプロビジョニングと管理の方法については、「 [PSTN 接続を使用したハイブリッド環境のユーザーアカウント](direct-routing-user-accounts-in-a-hybrid-environment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="ea788-163">通話プランまたは Skype for Business オンプレミス環境からの直接ルーティングに移行していますか?</span><span class="sxs-lookup"><span data-stu-id="ea788-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="ea788-164">既存の環境からの直接ルーティングへの移行の詳細については、「 [ダイレクトルーティングへの移行](direct-routing-migrating.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea788-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
