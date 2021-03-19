---
title: Android に Microsoft Teams の会議室を展開する
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
description: Android での Microsoft Teams の会議室の展開については、この記事をお読みください。
ms.openlocfilehash: bb02ff59eb473d0db276fd773e9f1ff3f1ae0007
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875007"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a><span data-ttu-id="586ab-103">Android に Microsoft Teams の会議室を展開する</span><span class="sxs-lookup"><span data-stu-id="586ab-103">Deploy Microsoft Teams Rooms on Android</span></span>

<span data-ttu-id="586ab-104">Android での Microsoft Teams Rooms の展開は、次のフェーズに分けすることができます。</span><span class="sxs-lookup"><span data-stu-id="586ab-104">Deployment of Microsoft Teams Rooms on Android can be broken down into the following phases:</span></span>

- <span data-ttu-id="586ab-105">**サイトの準備** 展開場所 (会議室) が展開要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="586ab-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="586ab-106">**サービスの準備** リソース アカウントを作成し、デバイスに割り当てる [(「Microsoft 365](resource-account-ui.md)管理センターを使用してリソース アカウントを作成する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="586ab-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="586ab-107">専用ルーム ライセンスの使用をお勧めしますが、適切にライセンスを取得したエンド ユーザー アカウントは Android 版 Teams Rooms にサインインすることもできます。</span><span class="sxs-lookup"><span data-stu-id="586ab-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to Teams Rooms on Android.</span></span>
- <span data-ttu-id="586ab-108">**構成と展開** Teams 会議室をセットアップし、必要な周辺機器を接続します (詳細については、製造元のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="586ab-108">**Configuration and deployment** Set up Teams Rooms and connect the peripheral devices you need (see the manufacturer's documentation for details).</span></span>

<span data-ttu-id="586ab-109">Teams 会議室を管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「Microsoft Teams 管理者ロールを使用して Teams を管理 [する」を参照してください](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="586ab-109">To manage Teams Rooms, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="586ab-110">サイトの準備</span><span class="sxs-lookup"><span data-stu-id="586ab-110">Site readiness</span></span>

<span data-ttu-id="586ab-111">注文されたデバイスが組織に配信されている間は、ネットワーク、施設、およびオーディオ ビジュアル チームと共同で、展開要件が満たされ、各サイトと部屋が電源、ネットワーク、表示の面で準備が整っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="586ab-111">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="586ab-112">コラボレーション バー サイトに関する推奨事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="586ab-112">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="586ab-113">最大 5 名の会議室</span><span class="sxs-lookup"><span data-stu-id="586ab-113">Rooms up to 5 people in size</span></span>
- <span data-ttu-id="586ab-114">専用リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="586ab-114">Dedicated resource accounts</span></span>
- <span data-ttu-id="586ab-115">タッチ対応ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="586ab-115">Touch-enabled displays</span></span>
- <span data-ttu-id="586ab-116">イーサネット ケーブル</span><span class="sxs-lookup"><span data-stu-id="586ab-116">Ethernet cabling</span></span>
- <span data-ttu-id="586ab-117">Microsoft Teams メディアのネットワークで有効になっているサービスの品質 (QoS)</span><span class="sxs-lookup"><span data-stu-id="586ab-117">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="586ab-118">物理的なインストールに関する考慮事項については、製造元のマニュアルを参照し、お持ちである場合は、スクリーンをインストールしてマウントし、ケーブルを実行する前に、オーディオ ビジュアル チームのエクスペリエンスを活用してください。</span><span class="sxs-lookup"><span data-stu-id="586ab-118">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="586ab-119">帯域幅計画およびリアルタイム トラフィックに対するネットワークの適性の評価のために [、Teams](../prepare-network.md) 用のネットワークを準備する方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="586ab-119">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="586ab-120">Teams デバイスとインターネットの間にプロキシ サーバーを配置はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="586ab-120">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="586ab-121">プロキシ サーバーと Teams の詳細については、Teams の [プロキシ サーバーを確認してください](../proxy-servers-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="586ab-121">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="586ab-123">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="586ab-123">Decision points</span></span>|<ul><li><span data-ttu-id="586ab-124">サイトが Microsoft Teams のコラボレーション バーのサイト準備要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="586ab-124">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="586ab-125">各サイトに十分な帯域幅があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="586ab-125">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![次の手順を表すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="586ab-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="586ab-127">Next steps</span></span>|<ul><li><span data-ttu-id="586ab-128">コラボレーション バーの展開と構成の計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="586ab-128">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="586ab-129">サービスの準備</span><span class="sxs-lookup"><span data-stu-id="586ab-129">Service readiness</span></span>

<span data-ttu-id="586ab-130">Teams 会議室を展開する前に、それらのユーザーが Microsoft 365 リソース アカウント、エンド ユーザー アカウント、または両方の組み合わを使用するか決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586ab-130">Before you deploy Teams Rooms, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="586ab-131">Microsoft 365 リソース アカウントは、会議室、プロジェクターなどの特定のリソース専用のメールボックスアカウントと Teams アカウントです。</span><span class="sxs-lookup"><span data-stu-id="586ab-131">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="586ab-132">これらのリソース アカウントは、作成時に定義したルールを使用して会議出席招待に自動的に応答できます。</span><span class="sxs-lookup"><span data-stu-id="586ab-132">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="586ab-133">Teams Rooms が個人のプライベート使用のために特定の個人専用である場合を限り、Microsoft 365 リソース アカウントをセットアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="586ab-133">Unless Teams Rooms is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="586ab-134">リソース アカウントを使用する</span><span class="sxs-lookup"><span data-stu-id="586ab-134">Using a resource account</span></span>

<span data-ttu-id="586ab-135">Microsoft 365 リソース アカウントを設定する場合は、その会議室ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586ab-135">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="586ab-136">会議室ライセンスには、組織内のユーザーが Outlook または Teams を介して会議室を予約できるリソース メールボックスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="586ab-136">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="586ab-137">このライセンスでは、会議参加者間のビデオ会議や電話会議、画面共有も有効にできます。</span><span class="sxs-lookup"><span data-stu-id="586ab-137">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="586ab-138">外部の電話番号との間で通話を受信または発信する必要がある場合は、通話プランまたは Microsoft 365 Business Voice アドオン ライセンス [が必要な場合があります](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)。</span><span class="sxs-lookup"><span data-stu-id="586ab-138">If you need to receive or make calls to or from an external telephone number, you may need a Calling Plan or Microsoft 365 Business Voice [add-on license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business).</span></span> <span data-ttu-id="586ab-139">組織で直接ルーティングを有効にしている場合は、会議室 SKU だけが必要です。</span><span class="sxs-lookup"><span data-stu-id="586ab-139">If you have Direct Routing enabled in your organization, you only need the Meeting Room SKU.</span></span>

<span data-ttu-id="586ab-140">リソース アカウントを作成するときに、アカウントで会議出席依頼を自動的に承諾するか辞退するか、定期的な会議を許可するか、ユーザーがリソースを予約できる事前の時間を指定するか、などと選択できます。</span><span class="sxs-lookup"><span data-stu-id="586ab-140">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="586ab-141">Microsoft 365 リソース アカウントの詳細については [、「Microsoft 365](resource-account-ui.md)管理センターを使用してリソース アカウントを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="586ab-141">For more information about Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="586ab-143">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="586ab-143">Decision points</span></span>|<ul><li><span data-ttu-id="586ab-144">外部電話の送受信を行うかどうかを決定し、リソース アカウントのライセンス要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="586ab-144">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![次の手順を表すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="586ab-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="586ab-146">Next steps</span></span>|<ul><li><span data-ttu-id="586ab-147">リソース アカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="586ab-147">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="586ab-148">構成と展開</span><span class="sxs-lookup"><span data-stu-id="586ab-148">Configuration and deployment</span></span>

<span data-ttu-id="586ab-149">構成と展開を計画する主要分野は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="586ab-149">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="586ab-150">リソース アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="586ab-150">Resource account provisioning</span></span>
- <span data-ttu-id="586ab-151">デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="586ab-151">Device deployment</span></span>
- <span data-ttu-id="586ab-152">Teams Rooms アプリケーションと周辺機器の構成</span><span class="sxs-lookup"><span data-stu-id="586ab-152">Teams Rooms application and peripheral device configuration</span></span>
- <span data-ttu-id="586ab-153">テスト</span><span class="sxs-lookup"><span data-stu-id="586ab-153">Testing</span></span>
- <span data-ttu-id="586ab-154">資産管理</span><span class="sxs-lookup"><span data-stu-id="586ab-154">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="586ab-155">アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="586ab-155">Account provisioning</span></span>

<span data-ttu-id="586ab-156">Microsoft 365 リソース アカウントを使用してユーザーがコラボレーション バーを予約する場合は [、「Microsoft 365](resource-account-ui.md) 管理センターを使用してリソース アカウントを作成する」の手順に従って、必要なコラボレーション バーごとに Microsoft 365 リソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="586ab-156">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="586ab-157">また、この場所では、リソース アカウントに会議室のライセンスを追加する必要があります。また、組織が直接ルーティングを使用していない場合に、外部の電話番号との間で通話を発信または受信する場合は、通話プランまたは Business Voice ライセンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586ab-157">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Calling Plan or Business Voice license if your organization is not using Direct Routing.</span></span>

<span data-ttu-id="586ab-158">個人使用のために Teams 会議室を個々のユーザーに割り当てる場合は、追加のアカウントを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="586ab-158">If you want to assign Teams Rooms to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="586ab-159">ユーザーは、個人用アカウントを使用してコラボレーション バーにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="586ab-159">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="586ab-160">Microsoft 365 リソース アカウントの表示名をわかりやすいわかりやすい名前にします。</span><span class="sxs-lookup"><span data-stu-id="586ab-160">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="586ab-161">Teams 会議室を検索して会議に追加するときに表示される名前は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="586ab-161">These are the names that users will see when searching for and adding Teams Rooms to meetings.</span></span> <span data-ttu-id="586ab-162">*たとえば*、ロンドンの 4 人の会議室である Curie には、"サイト ルーム名 " (最大会議室の最大容量) のような規則を使用できます。たとえば - 、LON-CURIE(4)という表示名を付けます。</span><span class="sxs-lookup"><span data-stu-id="586ab-162">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="586ab-164">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="586ab-164">Decision points</span></span>|<ul><li><span data-ttu-id="586ab-165">専用リソース アカウントの名前付け規則を決定します。</span><span class="sxs-lookup"><span data-stu-id="586ab-165">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="586ab-166">個々のアカウントを作成するか、一括プロビジョニング スクリプトを使用するか決定します。</span><span class="sxs-lookup"><span data-stu-id="586ab-166">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![次の手順を表すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="586ab-168">次のステップ</span><span class="sxs-lookup"><span data-stu-id="586ab-168">Next steps</span></span>|<ul><li><span data-ttu-id="586ab-169">デバイスの展開の計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="586ab-169">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="586ab-170">デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="586ab-170">Device deployment</span></span>

<span data-ttu-id="586ab-171">次に、デバイスと割り当てられた周辺機器を会議室に配信する計画を作成し、インストールと構成に進む必要があります。</span><span class="sxs-lookup"><span data-stu-id="586ab-171">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="586ab-173">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="586ab-173">Decision points</span></span>|<ul><li><span data-ttu-id="586ab-174">サイトごとの展開を管理するユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="586ab-174">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="586ab-175">Teams Rooms をサイトにインストールし、構成とテストを実行するリソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="586ab-175">Identify the resources who will install Teams Rooms on site and undertake the configuration and testing.</span></span></li></ul>|
| ![次の手順を表すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="586ab-177">次のステップ</span><span class="sxs-lookup"><span data-stu-id="586ab-177">Next steps</span></span>|<ul><li><span data-ttu-id="586ab-178">デバイスのテストを開始します。</span><span class="sxs-lookup"><span data-stu-id="586ab-178">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="586ab-179">テスト</span><span class="sxs-lookup"><span data-stu-id="586ab-179">Testing</span></span>

<span data-ttu-id="586ab-180">Teams 会議室を展開した後は、それらをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="586ab-180">After you have deployed Teams Rooms, you should test them.</span></span> <span data-ttu-id="586ab-181">Teams の会議室にサインインし、期待される機能が機能しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="586ab-181">Sign in to Teams Rooms and check that the expected capabilities are working.</span></span> <span data-ttu-id="586ab-182">Microsoft Teams 管理センターの [デバイス] タブの [コラボレーションバー] セクションに表示されるのを確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="586ab-182">We highly recommend that you verify that they are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="586ab-183">また、品質とパフォーマンスをチェックするために、テスト通話や会議を多数行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="586ab-183">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="586ab-184">Microsoft Teams の一般的なロールアウトの一環として、通話品質ダッシュボード (CQD) のファイルの構築、品質の傾向の監視、品質レビュー プロセスへの参加を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="586ab-184">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="586ab-185">詳細については、「エクスペリエンスの品質 [レビュー ガイド」を参照してください](https://aka.ms/qerguide)。</span><span class="sxs-lookup"><span data-stu-id="586ab-185">For more information, see the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

### <a name="asset-management"></a><span data-ttu-id="586ab-186">資産管理</span><span class="sxs-lookup"><span data-stu-id="586ab-186">Asset management</span></span>

<span data-ttu-id="586ab-187">展開の一環として、ルーム名、サインイン済みリソース アカウント、および割り当てられた周辺機器を使用して資産登録を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586ab-187">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="586ab-188">関連トピック</span><span class="sxs-lookup"><span data-stu-id="586ab-188">Related topics</span></span>

[<span data-ttu-id="586ab-189">Microsoft Teams 管理センターを使用して Microsoft Teams 会議室のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="586ab-189">Configure accounts for Microsoft Teams Rooms using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
