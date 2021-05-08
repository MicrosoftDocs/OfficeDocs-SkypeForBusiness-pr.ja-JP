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
description: 構成、必要なコア デプロイの決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
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
# <a name="phone-system-direct-routing"></a><span data-ttu-id="07e3c-103">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="07e3c-103">Phone System Direct Routing</span></span>

<span data-ttu-id="07e3c-104">[使用開始](get-started-with-teams-quick-start.md)の手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="07e3c-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="07e3c-105">Teams の[チャット、チーム、チャネル、およびアプリ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)を組織全体に展開しました。</span><span class="sxs-lookup"><span data-stu-id="07e3c-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="07e3c-106">[会議および電話会議](deploy-meetings-microsoft-teams-landing-page.md)を展開した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="07e3c-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="07e3c-107">これでクラウド音声ワークロードを追加する準備が整い、電話システム ダイレクト ルーティングを使用して、公衆交換電話網 (PSTN) 接続に独自のテレフォニー 通信事業者を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="07e3c-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="07e3c-108">ダイレクト ルーティングでは、事実上すべてのテレフォニー 電話システムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="07e3c-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="07e3c-109">この記事では、直接ルーティングの主要なデプロイの決定と、組織のニーズに基づいて考慮する必要がある追加の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e3c-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="07e3c-110">また、Microsoft のクラウド ボイス サービスの詳細については、「[Microsoft Teams でのクラウド ボイス](cloud-voice-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e3c-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="07e3c-111">ダイレクト ルーティングの詳細を確認する</span><span class="sxs-lookup"><span data-stu-id="07e3c-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="07e3c-112">次の記事では、ダイレクト ルーティングの構成と使用の詳細電話システム説明します。</span><span class="sxs-lookup"><span data-stu-id="07e3c-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="07e3c-113">直接ルーティングを構成するには、PSTN ルーティング設計について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e3c-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="07e3c-114">直接ルーティングを計画および構成する方法については、次のすべての記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e3c-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="07e3c-115">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="07e3c-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="07e3c-116">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="07e3c-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="07e3c-117">ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト</span><span class="sxs-lookup"><span data-stu-id="07e3c-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="07e3c-118">ダイレクト ルーティングの監視とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="07e3c-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="07e3c-119">さらに、要件に応じて、次の記事を読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e3c-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="07e3c-120">複数のテナントにセッション ボーダー コントローラーを構成する</span><span class="sxs-lookup"><span data-stu-id="07e3c-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="07e3c-121">ダイレクト ルーティングに移行する</span><span class="sxs-lookup"><span data-stu-id="07e3c-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="07e3c-122">PSTN 接続を使用するハイブリッド環境でのユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="07e3c-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="07e3c-123">ダイレクト ルーティングの詳細については、次のセッションをご[Microsoft Teams覧](https://aka.ms/teams-direct-routing)ください。</span><span class="sxs-lookup"><span data-stu-id="07e3c-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="07e3c-124">展開に関する重要な決定事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-124">Core deployment decisions</span></span>

<span data-ttu-id="07e3c-125">これらは、ダイレクト ルーティングに関して考慮すべき主要な決定です。</span><span class="sxs-lookup"><span data-stu-id="07e3c-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="07e3c-126">確認事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-126">Ask yourself</span></span>|<span data-ttu-id="07e3c-127">アクション</span><span class="sxs-lookup"><span data-stu-id="07e3c-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="07e3c-128">ダイレクト ルーティングを有効にするユーザー</span><span class="sxs-lookup"><span data-stu-id="07e3c-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="07e3c-129">詳細については、「ダイレクト ルーティング サービスの [ユーザーを有効にする」を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="07e3c-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="07e3c-130">ダイレクト ルーティングに必要なライセンスはありますか。</span><span class="sxs-lookup"><span data-stu-id="07e3c-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="07e3c-131">詳細については、「ライセンスと他 [の要件」を参照してください](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="07e3c-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="07e3c-132">セッション ボーダー コントローラー (SBC) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="07e3c-133">直接ルーティングを使用すると、独自のセッション ボーダー コントローラー (SBC) を直接接続して、電話システム。</span><span class="sxs-lookup"><span data-stu-id="07e3c-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="07e3c-134">認定された SBC の一覧については、「サポートされているセッション ボーダー コントローラー [」を参照してください](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="07e3c-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="07e3c-135">確認事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-135">Ask yourself</span></span>|<span data-ttu-id="07e3c-136">アクション</span><span class="sxs-lookup"><span data-stu-id="07e3c-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="07e3c-137">SBC をデプロイする場所と方法</span><span class="sxs-lookup"><span data-stu-id="07e3c-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="07e3c-138">詳細については、「ダイレクト ルーティングの [構成」を参照してください。](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="07e3c-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="07e3c-139">複数のテナントがありますか?</span><span class="sxs-lookup"><span data-stu-id="07e3c-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="07e3c-140">詳細については、「複数のテナント [のセッション ボーダー コントローラーを構成する」を参照してください](direct-routing-sbc-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="07e3c-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="07e3c-141">音声ルーティングに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-141">Voice routing considerations</span></span>

<span data-ttu-id="07e3c-142">呼び出しを特定の SBC にルーティング電話システムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e3c-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="07e3c-143">確認事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-143">Ask yourself</span></span>|<span data-ttu-id="07e3c-144">アクション</span><span class="sxs-lookup"><span data-stu-id="07e3c-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="07e3c-145">作成する必要がある音声ルーティング ポリシー、PSTN 使用法、音声ルート</span><span class="sxs-lookup"><span data-stu-id="07e3c-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="07e3c-146">音声ルーティングの情報については、「音声ルーティングの [構成」を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="07e3c-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="07e3c-147">定義する音声ルーティング ポリシーに割り当てられるユーザー</span><span class="sxs-lookup"><span data-stu-id="07e3c-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="07e3c-148">「音声ルーティングの構成」 [の例を参照してください](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="07e3c-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="07e3c-149">TeamsUpgradePolicy を使用して、Teamsクライアントに着信通話が着信する</span><span class="sxs-lookup"><span data-stu-id="07e3c-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="07e3c-150">ダイレクト ルーティングは、直接ルーティングがサポートされているMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="07e3c-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="07e3c-151">直接ルーティングを介して PSTN 通話を受信するには、TeamsUpgradePolicy を構成して、着信通話が着信通話で受信Teams。</span><span class="sxs-lookup"><span data-stu-id="07e3c-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="07e3c-152">ユーザーは、TeamsUpgradePolicy Teams UpgradeToTeams" インスタンスを割り当て、ユーザーを [のみ] モードにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e3c-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="07e3c-153">確認事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-153">Ask yourself</span></span>|<span data-ttu-id="07e3c-154">アクション</span><span class="sxs-lookup"><span data-stu-id="07e3c-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="07e3c-155">[のみ] Teamsとはどういう意味ですか?</span><span class="sxs-lookup"><span data-stu-id="07e3c-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="07e3c-156">詳細については、「移行と相互運用性に関する[Skype for Business Teamsガイダンス](./migration-interop-guidance-for-teams-with-skype.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e3c-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="07e3c-157">その他のデプロイに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-157">Additional deployment considerations</span></span>

<span data-ttu-id="07e3c-158">組織のニーズと構成に基づいて、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="07e3c-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="07e3c-159">確認事項</span><span class="sxs-lookup"><span data-stu-id="07e3c-159">Ask yourself</span></span>| <span data-ttu-id="07e3c-160">アクション</span><span class="sxs-lookup"><span data-stu-id="07e3c-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="07e3c-161">ハイブリッド接続が構成された既存Skype for Business Serverデプロイはありますか。</span><span class="sxs-lookup"><span data-stu-id="07e3c-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="07e3c-162">ハイブリッド環境のユーザー アカウントがどのようにプロビジョニングおよび管理されるのかについては、「PSTN 接続を使用したハイブリッド環境のユーザー アカウント」 [を参照してください](direct-routing-user-accounts-in-a-hybrid-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="07e3c-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="07e3c-163">通話プランまたはオンプレミス環境から直接ルーティングに移行Skype for Business移行していますか。</span><span class="sxs-lookup"><span data-stu-id="07e3c-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="07e3c-164">既存の環境からのダイレクト ルーティングへの移行の詳細については、「ダイレクト ルーティングへの移行 [」を参照してください](direct-routing-migrating.md)。</span><span class="sxs-lookup"><span data-stu-id="07e3c-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||