---
title: Android Microsoft Teams ミーティングをデプロイする
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: この記事では、Android にアプリをMicrosoft Teams ミーティング説明します。
ms.openlocfilehash: 3da0192ee3676f5ff7294ba719c778ea7b1cc7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120799"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a><span data-ttu-id="a185a-103">Android Microsoft Teams ミーティングをデプロイする</span><span class="sxs-lookup"><span data-stu-id="a185a-103">Deploy Microsoft Teams Rooms on Android</span></span>

<span data-ttu-id="a185a-104">Android でのMicrosoft Teams ミーティングの展開は、次のフェーズに分け可能です。</span><span class="sxs-lookup"><span data-stu-id="a185a-104">Deployment of Microsoft Teams Rooms on Android can be broken down into the following phases:</span></span>

- <span data-ttu-id="a185a-105">**サイトの準備** デプロイの場所 (会議室) がデプロイ要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a185a-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="a185a-106">**サービスの準備** リソース アカウントを作成し、デバイスに割り当てる (「管理センターでリソース アカウントを [作成するMicrosoft 365参照してください](resource-account-ui.md))。</span><span class="sxs-lookup"><span data-stu-id="a185a-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="a185a-107">専用ルーム ライセンスを使用することをお勧めしますが、適切にライセンスされたエンド ユーザー アカウントは、Android 上の Teams ミーティングサインインすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a185a-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to Teams Rooms on Android.</span></span>
- <span data-ttu-id="a185a-108">**構成とデプロイ** 必要なTeams ミーティングデバイスをセットアップして接続します (詳細については、製造元のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a185a-108">**Configuration and deployment** Set up Teams Rooms and connect the peripheral devices you need (see the manufacturer's documentation for details).</span></span>

<span data-ttu-id="a185a-109">アカウントをTeams ミーティングするには、グローバル管理者、サービス管理者、Teamsデバイス管理者Teams必要があります。管理者ロールの詳細については、「管理者ロールを使用してMicrosoft Teams[を管理する」を](../using-admin-roles.md)Teams。</span><span class="sxs-lookup"><span data-stu-id="a185a-109">To manage Teams Rooms, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="a185a-110">サイトの準備</span><span class="sxs-lookup"><span data-stu-id="a185a-110">Site readiness</span></span>

<span data-ttu-id="a185a-111">注文されたデバイスが組織に配信されている間は、ネットワーク、施設、およびオーディオ ビジュアル チームと共同で、展開要件が満たされ、各サイトと部屋が電源、ネットワーク、表示の面で準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a185a-111">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="a185a-112">コラボレーション バー サイトに関する推奨事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a185a-112">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="a185a-113">最大 5 名の会議室</span><span class="sxs-lookup"><span data-stu-id="a185a-113">Rooms up to 5 people in size</span></span>
- <span data-ttu-id="a185a-114">専用リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="a185a-114">Dedicated resource accounts</span></span>
- <span data-ttu-id="a185a-115">タッチ対応ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="a185a-115">Touch-enabled displays</span></span>
- <span data-ttu-id="a185a-116">イーサネット ケーブル接続</span><span class="sxs-lookup"><span data-stu-id="a185a-116">Ethernet cabling</span></span>
- <span data-ttu-id="a185a-117">ネットワーク上で有効になっているサービス品質 (QoS) が、Microsoft Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="a185a-117">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="a185a-118">物理的なインストールに関する考慮事項については、製造元のドキュメントを参照してください。また、ある場合は、画面をインストールしてマウントし、ケーブル配線を実行する前に、オーディオ ビジュアル チームのエクスペリエンスを活用してください。</span><span class="sxs-lookup"><span data-stu-id="a185a-118">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="a185a-119">「帯域幅の計画とリアルタイム トラフィックに対するネットワーク[の適合性の評価Teams](../prepare-network.md)ネットワークを準備する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a185a-119">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="a185a-120">複数のデバイスとインターネットの間にプロキシ Teams配置はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a185a-120">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="a185a-121">プロキシ サーバーとプロキシ サーバーの詳細については、Teams のプロキシ サーバーに関[するTeams。](../proxy-servers-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="a185a-121">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a185a-123">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="a185a-123">Decision points</span></span>|<ul><li><span data-ttu-id="a185a-124">サイトがコラボレーション バーのサイト準備要件を満たしていることを確認Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a185a-124">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="a185a-125">各サイトに十分な帯域幅があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a185a-125">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![次の手順を示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a185a-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="a185a-127">Next steps</span></span>|<ul><li><span data-ttu-id="a185a-128">コラボレーション バーのデプロイと構成の計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="a185a-128">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="a185a-129">サービスの準備</span><span class="sxs-lookup"><span data-stu-id="a185a-129">Service readiness</span></span>

<span data-ttu-id="a185a-130">アプリケーションをデプロイTeams ミーティング、リソース アカウント、エンド ユーザー アカウント、または両方をMicrosoft 365を使用するか判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-130">Before you deploy Teams Rooms, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="a185a-131">Microsoft 365アカウントは、会議室Teamsプロジェクターなど、特定のリソース専用のメールボックス アカウントとリソース アカウントです。</span><span class="sxs-lookup"><span data-stu-id="a185a-131">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="a185a-132">これらのリソース アカウントは、作成時に定義したルールを使用して、会議出席招待に自動的に応答できます。</span><span class="sxs-lookup"><span data-stu-id="a185a-132">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="a185a-133">特定のTeams ミーティング専用のリソース アカウントがない限り、リソース アカウントMicrosoft 365を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a185a-133">Unless Teams Rooms is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="a185a-134">リソース アカウントの使用</span><span class="sxs-lookup"><span data-stu-id="a185a-134">Using a resource account</span></span>

<span data-ttu-id="a185a-135">リソース アカウントを設定するMicrosoft 365、リソース アカウントのライセンスを購入ミーティング ルーム必要があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-135">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="a185a-136">このミーティング ルームライセンスには、組織内のユーザーが会議や会議を通じて会議室を予約できるリソース メールボックスOutlook含Teams。</span><span class="sxs-lookup"><span data-stu-id="a185a-136">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="a185a-137">このライセンスでは、会議参加者間でのビデオ会議と電話会議と画面共有も可能です。</span><span class="sxs-lookup"><span data-stu-id="a185a-137">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="a185a-138">外部の電話番号との間で通話を受信または発信する必要がある場合は、通話プランまたはアドオン ライセンス Microsoft 365 Business Voice[必要な場合があります](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。</span><span class="sxs-lookup"><span data-stu-id="a185a-138">If you need to receive or make calls to or from an external telephone number, you may need a Calling Plan or Microsoft 365 Business Voice [add-on license](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business).</span></span> <span data-ttu-id="a185a-139">組織で直接ルーティングを有効にしている場合は、その SKU ミーティング ルーム必要です。</span><span class="sxs-lookup"><span data-stu-id="a185a-139">If you have Direct Routing enabled in your organization, you only need the Meeting Room SKU.</span></span>

<span data-ttu-id="a185a-140">リソース アカウントを作成するときに、アカウントで会議出席依頼を自動的に承諾または拒否するか、定期的な会議を許可するか、ユーザーがリソースを予約できる時間を事前に指定するかなどについて選択できます。</span><span class="sxs-lookup"><span data-stu-id="a185a-140">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="a185a-141">リソース アカウントの詳細についてはMicrosoft 365管理センターを使用してリソース アカウント[を作成するMicrosoft 365参照してください](resource-account-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="a185a-141">For more information about Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a185a-143">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="a185a-143">Decision points</span></span>|<ul><li><span data-ttu-id="a185a-144">外部の電話の送受信を行うかどうかを決定し、リソース アカウントのライセンス要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="a185a-144">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![次の手順を示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a185a-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="a185a-146">Next steps</span></span>|<ul><li><span data-ttu-id="a185a-147">リソース アカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="a185a-147">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="a185a-148">構成と展開</span><span class="sxs-lookup"><span data-stu-id="a185a-148">Configuration and deployment</span></span>

<span data-ttu-id="a185a-149">構成と展開を計画する主要分野は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a185a-149">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="a185a-150">リソース アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="a185a-150">Resource account provisioning</span></span>
- <span data-ttu-id="a185a-151">デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="a185a-151">Device deployment</span></span>
- <span data-ttu-id="a185a-152">Teams ミーティングおよび周辺機器の構成</span><span class="sxs-lookup"><span data-stu-id="a185a-152">Teams Rooms application and peripheral device configuration</span></span>
- <span data-ttu-id="a185a-153">テスト</span><span class="sxs-lookup"><span data-stu-id="a185a-153">Testing</span></span>
- <span data-ttu-id="a185a-154">資産管理</span><span class="sxs-lookup"><span data-stu-id="a185a-154">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="a185a-155">アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="a185a-155">Account provisioning</span></span>

<span data-ttu-id="a185a-156">Microsoft 365 リソース アカウントを使用してコラボレーション バーを予約する場合は[、「Microsoft 365](resource-account-ui.md)管理センターを使用してリソース アカウントを作成する」の手順に従って、必要なコラボレーション バーごとに Microsoft 365 リソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a185a-156">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="a185a-157">また、リソース アカウントに ミーティング ルーム ライセンスを追加する必要があります。また、組織が直接ルーティングを使用していない場合は、外部の電話番号との間で通話を発信または受信する場合は、通話プランまたは Business Voice ライセンスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-157">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Calling Plan or Business Voice license if your organization is not using Direct Routing.</span></span>

<span data-ttu-id="a185a-158">個々のユーザーにTeams ミーティングを割り当てる場合は、追加のアカウントを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a185a-158">If you want to assign Teams Rooms to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="a185a-159">ユーザーは、個人用アカウントを使用してコラボレーション バーにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="a185a-159">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="a185a-160">リソース アカウントの表示名をわかりやすいMicrosoft 365わかりやすい名前にします。</span><span class="sxs-lookup"><span data-stu-id="a185a-160">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="a185a-161">これらは、ユーザーが会議を検索して会議に追加するときに表示Teams ミーティング名前です。</span><span class="sxs-lookup"><span data-stu-id="a185a-161">These are the names that users will see when searching for and adding Teams Rooms to meetings.</span></span> <span data-ttu-id="a185a-162">*サイト* ルーム名 ( 最大会議室の容量) などの規則を使用できます。そのため、たとえば、ロンドンの 4 人の会議室である Curie は、表示名 - LON-CURIE(4)を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-162">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a185a-164">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="a185a-164">Decision points</span></span>|<ul><li><span data-ttu-id="a185a-165">専用リソース アカウントの名前付け規則を決定します。</span><span class="sxs-lookup"><span data-stu-id="a185a-165">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="a185a-166">個々のアカウントを作成するか、一括プロビジョニング スクリプトを使用するか決定します。</span><span class="sxs-lookup"><span data-stu-id="a185a-166">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![次の手順を示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a185a-168">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a185a-168">Next steps</span></span>|<ul><li><span data-ttu-id="a185a-169">デバイスの展開の計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="a185a-169">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="a185a-170">デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="a185a-170">Device deployment</span></span>

<span data-ttu-id="a185a-171">次に、デバイスと割り当てられた周辺機器を会議室に配信する計画を作成し、インストールと構成に進む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-171">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="a185a-173">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="a185a-173">Decision points</span></span>|<ul><li><span data-ttu-id="a185a-174">サイトごとの展開を管理するユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="a185a-174">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="a185a-175">サイトにインストールするリソースTeams ミーティング、構成とテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="a185a-175">Identify the resources who will install Teams Rooms on site and undertake the configuration and testing.</span></span></li></ul>|
| ![次の手順を示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="a185a-177">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a185a-177">Next steps</span></span>|<ul><li><span data-ttu-id="a185a-178">デバイスのテストを開始します。</span><span class="sxs-lookup"><span data-stu-id="a185a-178">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="a185a-179">テスト</span><span class="sxs-lookup"><span data-stu-id="a185a-179">Testing</span></span>

<span data-ttu-id="a185a-180">アプリケーションをデプロイした後Teams ミーティングテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-180">After you have deployed Teams Rooms, you should test them.</span></span> <span data-ttu-id="a185a-181">サインインして、Teams ミーティング機能が動作している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-181">Sign in to Teams Rooms and check that the expected capabilities are working.</span></span> <span data-ttu-id="a185a-182">管理センターの [デバイス] タブの [コラボレーションバー] セクションに表示Microsoft Teams強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a185a-182">We highly recommend that you verify that they are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="a185a-183">また、品質とパフォーマンスを確認するために、テスト通話や会議を多数行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-183">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="a185a-184">Microsoft Teams の一般的なロールアウトの一環として、通話品質ダッシュボード (CQD) のファイルの作成、品質の傾向の監視、およびエクスペリエンスの品質レビュー プロセスへの参加を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a185a-184">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="a185a-185">詳細については、「エクスペリエンスの品質 [レビュー ガイド」を参照してください](../quality-of-experience-review-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="a185a-185">For more information, see the [Quality of Experience Review Guide](../quality-of-experience-review-guide.md).</span></span>

### <a name="asset-management"></a><span data-ttu-id="a185a-186">資産管理</span><span class="sxs-lookup"><span data-stu-id="a185a-186">Asset management</span></span>

<span data-ttu-id="a185a-187">デプロイの一環として、ルーム名、サインイン済みリソース アカウント、および割り当てられた周辺機器を使用してアセット レジスタを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a185a-187">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a185a-188">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a185a-188">Related topics</span></span>

[<span data-ttu-id="a185a-189">管理センターを使用Microsoft Teams ミーティングアカウントMicrosoft Teams構成する</span><span class="sxs-lookup"><span data-stu-id="a185a-189">Configure accounts for Microsoft Teams Rooms using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->