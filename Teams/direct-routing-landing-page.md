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
description: 構成、必要な主要な展開決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4298cc34122d6b3bb7d9f9bb1f8698aec864426f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122211"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="4cd0f-103">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="4cd0f-103">Phone System Direct Routing</span></span>

<span data-ttu-id="4cd0f-104">[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="4cd0f-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="4cd0f-106">[会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="4cd0f-107">これで、クラウド 音声ワークロードを追加する準備が整い、電話システム ダイレクト ルーティングを使用して、独自のテレフォニー通信事業者を公衆交換電話網 (PSTN) 接続に使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="4cd0f-108">直接ルーティングを使用すると、事実上すべてのテレフォニー通信事業者で電話システムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="4cd0f-109">この記事では、ダイレクト ルーティングの主要な展開決定と、組織のニーズに基づいて検討する必要がある追加の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="4cd0f-110">また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="4cd0f-111">ダイレクト ルーティングの詳細</span><span class="sxs-lookup"><span data-stu-id="4cd0f-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="4cd0f-112">電話システム ダイレクト ルーティングの構成と使用の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="4cd0f-113">直接ルーティングを構成するには、PSTN ルーティングの設計を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="4cd0f-114">ダイレクト ルーティングを計画および構成する方法については、次のすべての記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="4cd0f-115">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="4cd0f-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="4cd0f-116">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="4cd0f-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="4cd0f-117">ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト</span><span class="sxs-lookup"><span data-stu-id="4cd0f-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="4cd0f-118">ダイレクト ルーティングの監視とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4cd0f-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="4cd0f-119">さらに、要件に応じて、次の記事をお読みになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="4cd0f-120">複数のテナントにセッション ボーダー コントローラーを構成する</span><span class="sxs-lookup"><span data-stu-id="4cd0f-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="4cd0f-121">ダイレクト ルーティングに移行する</span><span class="sxs-lookup"><span data-stu-id="4cd0f-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="4cd0f-122">PSTN 接続を使用するハイブリッド環境でのユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="4cd0f-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="4cd0f-123">直接ルーティングの詳細については、次のセッションをご覧ください [:Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="4cd0f-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="4cd0f-124">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-124">Core deployment decisions</span></span>

<span data-ttu-id="4cd0f-125">これらは、ダイレクト ルーティングに関して考慮すべき主要な決定です。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="4cd0f-126">確認事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-126">Ask yourself</span></span>|<span data-ttu-id="4cd0f-127">操作</span><span class="sxs-lookup"><span data-stu-id="4cd0f-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="4cd0f-128">ダイレクト ルーティングを有効にするユーザー</span><span class="sxs-lookup"><span data-stu-id="4cd0f-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="4cd0f-129">詳細については、「ダイレクト ルーティング サービス [でユーザーを有効にする」を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="4cd0f-130">ダイレクト ルーティングに必要なライセンスはありますか?</span><span class="sxs-lookup"><span data-stu-id="4cd0f-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="4cd0f-131">詳細については、「ライセンスと [他の要件」を参照してください](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="4cd0f-132">セッション ボーダー コントローラー (SBC) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="4cd0f-133">直接ルーティングを使用すると、独自のセッション ボーダー コントローラー (SBC) を電話システムに直接接続できます。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="4cd0f-134">認定された SPC の一覧については、「サポートされるセッション ボーダー コントローラー [」を参照してください](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="4cd0f-135">確認事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-135">Ask yourself</span></span>|<span data-ttu-id="4cd0f-136">操作</span><span class="sxs-lookup"><span data-stu-id="4cd0f-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="4cd0f-137">SBC を展開する場所と方法</span><span class="sxs-lookup"><span data-stu-id="4cd0f-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="4cd0f-138">詳細については、「ダイレクト ルーティングの [構成」を参照してください。](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="4cd0f-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="4cd0f-139">複数のテナントがありますか?</span><span class="sxs-lookup"><span data-stu-id="4cd0f-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="4cd0f-140">詳細については、「複数のテナント [のセッション ボーダー コントローラーを構成する」を参照してください](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="4cd0f-141">音声ルーティングに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-141">Voice routing considerations</span></span>

<span data-ttu-id="4cd0f-142">通話を特定の SPC にルーティングするには、電話システムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="4cd0f-143">確認事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-143">Ask yourself</span></span>|<span data-ttu-id="4cd0f-144">操作</span><span class="sxs-lookup"><span data-stu-id="4cd0f-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="4cd0f-145">作成する必要がある音声ルーティング ポリシー、PSTN の使用状況、および音声ルート</span><span class="sxs-lookup"><span data-stu-id="4cd0f-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="4cd0f-146">音声ルーティングの情報については、「音声ルーティングを [構成する」を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="4cd0f-147">定義した音声ルーティング ポリシーに割り当てられるユーザー</span><span class="sxs-lookup"><span data-stu-id="4cd0f-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="4cd0f-148">「音声ルーティングの構成」の [例を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="4cd0f-149">TeamsUpgradePolicy を使用して、着信通話が Teams クライアントに着信する</span><span class="sxs-lookup"><span data-stu-id="4cd0f-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="4cd0f-150">直接ルーティングは、Microsoft Teams でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="4cd0f-151">直接ルーティングを通じて PSTN 通話を受信するには、Teams で着信通話を確実に受信するために TeamsUpgradePolicy を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="4cd0f-152">ユーザーは TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当て、Teams Only モードである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="4cd0f-153">確認事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-153">Ask yourself</span></span>|<span data-ttu-id="4cd0f-154">操作</span><span class="sxs-lookup"><span data-stu-id="4cd0f-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="4cd0f-155">Teams Only モードとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="4cd0f-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="4cd0f-156">詳細については、Skype for Business と共に Teams を使用する組織の移行と相互 [運用性のガイダンスを参照してください](./migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="4cd0f-157">展開に関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-157">Additional deployment considerations</span></span>

<span data-ttu-id="4cd0f-158">組織のニーズと構成に基づいて、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="4cd0f-159">確認事項</span><span class="sxs-lookup"><span data-stu-id="4cd0f-159">Ask yourself</span></span>| <span data-ttu-id="4cd0f-160">操作</span><span class="sxs-lookup"><span data-stu-id="4cd0f-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="4cd0f-161">ハイブリッド接続が構成された既存の Skype for Business Server 展開がありますか?</span><span class="sxs-lookup"><span data-stu-id="4cd0f-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="4cd0f-162">ハイブリッド環境のユーザー アカウントのプロビジョニングと管理方法については、「PSTN 接続を使用したハイブリッド環境のユーザー アカウント」 [を参照してください](direct-routing-user-accounts-in-a-hybrid-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="4cd0f-163">通話プランまたは Skype for Business オンプレミス環境から直接ルーティングに移行していますか?</span><span class="sxs-lookup"><span data-stu-id="4cd0f-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="4cd0f-164">既存の環境からのダイレクト ルーティングへの移行の詳細については、「ダイレクト ルーティングへの移行 [」を参照してください](direct-routing-migrating.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd0f-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||