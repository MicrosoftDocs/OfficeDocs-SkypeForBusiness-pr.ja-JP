---
title: Microsoft Teams のコラボレーションバーの展開
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
description: この記事では、Microsoft Teams のコラボレーションバーの展開について説明します。
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962908"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a><span data-ttu-id="8de07-103">Microsoft Teams のコラボレーションバーの展開</span><span class="sxs-lookup"><span data-stu-id="8de07-103">Deploy collaboration bars for Microsoft Teams</span></span>

<span data-ttu-id="8de07-104">Microsoft Teams のコラボレーションバーの展開は、次のフェーズに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="8de07-104">Deployment of collaboration bars for Microsoft Teams can be broken down into the following phases:</span></span>

- <span data-ttu-id="8de07-105">**サイトの準備** 展開場所 (会議室) が展開要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8de07-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="8de07-106">**サービスの準備** リソースアカウントを作成してデバイスに割り当てる ([「Microsoft 365 管理センターを使用してリソースアカウントを作成する」を参照](resource-account-ui.md)してください)。</span><span class="sxs-lookup"><span data-stu-id="8de07-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="8de07-107">専用の room ライセンスを使用することをお勧めしますが、適切なライセンスのエンドユーザーアカウントでコラボレーションバーにサインインすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8de07-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to collaboration bars.</span></span>
- <span data-ttu-id="8de07-108">**構成と展開** 会議室でコラボレーションバーを設定し、必要な周辺機器を接続します (共同作業バーについては、製造元のマニュアルを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8de07-108">**Configuration and deployment** Set up collaboration bars in rooms and connect the peripheral devices you need (see the manufacturer's documentation for your collaboration bars).</span></span>

<span data-ttu-id="8de07-109">コラボレーションバーを管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「 [Microsoft teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8de07-109">To manage collaboration bars, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="8de07-110">サイトの準備</span><span class="sxs-lookup"><span data-stu-id="8de07-110">Site readiness</span></span>

<span data-ttu-id="8de07-111">注文されたデバイスは組織に配信されますが、ネットワーク、設備、およびオーディオビジュアルチームと協力して、展開要件が満たされていることを確認し、各サイトと部屋の電力、ネットワーキング、ディスプレイの準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8de07-111">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="8de07-112">コラボレーションバーサイトについての推奨事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8de07-112">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="8de07-113">サイズが最大4人のルーム</span><span class="sxs-lookup"><span data-stu-id="8de07-113">Rooms up to 4 people in size</span></span>
- <span data-ttu-id="8de07-114">専用リソースアカウント</span><span class="sxs-lookup"><span data-stu-id="8de07-114">Dedicated resource accounts</span></span>
- <span data-ttu-id="8de07-115">タッチ対応ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="8de07-115">Touch-enabled displays</span></span>
- <span data-ttu-id="8de07-116">イーサネット接続</span><span class="sxs-lookup"><span data-stu-id="8de07-116">Ethernet cabling</span></span>
- <span data-ttu-id="8de07-117">Microsoft Teams メディアのネットワークで有効になっている QoS (Quality of Service)</span><span class="sxs-lookup"><span data-stu-id="8de07-117">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="8de07-118">物理的なインストールの考慮事項については、製造元のマニュアルを参照してください。いずれかの場合は、画面をインストールして起動し、ケーブルを接続する前に、オーディオビジュアルチームのエクスペリエンスを活用してください。</span><span class="sxs-lookup"><span data-stu-id="8de07-118">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="8de07-119">必ず、「 [ネットワーク](../prepare-network.md) の帯域幅の計画」を確認して、リアルタイムトラフィックに対するネットワークの適合性を評価してください。</span><span class="sxs-lookup"><span data-stu-id="8de07-119">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="8de07-120">Teams デバイスとインターネットの間にプロキシサーバーを配置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="8de07-120">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="8de07-121">プロキシサーバーと Teams の詳細については、「 [teams のプロキシサーバー](../proxy-servers-for-skype-for-business-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8de07-121">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="8de07-123">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="8de07-123">Decision points</span></span>|<ul><li><span data-ttu-id="8de07-124">サイトが Microsoft Teams のコラボレーションバーのサイト準備要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8de07-124">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="8de07-125">各サイトに十分な帯域幅があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8de07-125">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="8de07-127">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8de07-127">Next steps</span></span>|<ul><li><span data-ttu-id="8de07-128">コラボレーションバーの展開と構成の計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="8de07-128">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="8de07-129">サービスの準備</span><span class="sxs-lookup"><span data-stu-id="8de07-129">Service readiness</span></span>

<span data-ttu-id="8de07-130">コラボレーションバーを展開する前に、Microsoft 365 リソースアカウント、エンドユーザーアカウント、または両方を組み合わせて使用するかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8de07-130">Before you deploy your collaboration bars, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="8de07-131">Microsoft 365 リソースアカウントは、会議室、プロジェクターなどの特定のリソース専用のメールボックスおよび Teams アカウントです。</span><span class="sxs-lookup"><span data-stu-id="8de07-131">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="8de07-132">これらのリソースアカウントは、作成時に定義したルールを使って、会議出席依頼に自動的に応答できます。</span><span class="sxs-lookup"><span data-stu-id="8de07-132">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="8de07-133">プライベート使用のためにコラボレーションバーが特定の個人専用である場合を除き、Microsoft 365 リソースアカウントを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8de07-133">Unless a collaboration bar is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="8de07-134">リソースアカウントの使用</span><span class="sxs-lookup"><span data-stu-id="8de07-134">Using a resource account</span></span>

<span data-ttu-id="8de07-135">Microsoft 365 リソースアカウントを設定する場合は、会議室ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8de07-135">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="8de07-136">会議室ライセンスには、組織内のユーザーが Outlook または Teams で会議室を予約できるようにするリソースメールボックスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8de07-136">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="8de07-137">このライセンスでは、会議参加者間でのビデオおよび音声会議や画面共有も可能です。</span><span class="sxs-lookup"><span data-stu-id="8de07-137">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="8de07-138">外部の電話番号に対して電話をかけたり、発信したりする必要がある場合は、通話プランまたは Microsoft 365 Business Voice [アドオンライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="8de07-138">If you need to receive or make calls to or from an external telephone number, you may need a Calling Plan or Microsoft 365 Business Voice [add-on license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business).</span></span> <span data-ttu-id="8de07-139">組織で直接ルーティングを有効にしている場合は、会議室の SKU のみが必要になります。</span><span class="sxs-lookup"><span data-stu-id="8de07-139">If you have Direct Routing enabled in your organization, you only need the Meeting Room SKU.</span></span>

<span data-ttu-id="8de07-140">リソースアカウントを作成するときに、アカウントに対して自動的に会議出席依頼を承諾または辞退するか、定期的な会議を許可するか、または他のユーザーがリソースを予約できるようにするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8de07-140">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="8de07-141">Microsoft 365 リソースアカウントのコラボレーションバーの詳細については、「 [microsoft 365 管理センターを使用してリソースアカウントを作成](resource-account-ui.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8de07-141">For more information about collaboration bars for Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="8de07-143">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="8de07-143">Decision points</span></span>|<ul><li><span data-ttu-id="8de07-144">外部の電話を発信または受信するかどうかを決定し、リソースアカウントのライセンス要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="8de07-144">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="8de07-146">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8de07-146">Next steps</span></span>|<ul><li><span data-ttu-id="8de07-147">リソースアカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="8de07-147">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="8de07-148">構成と展開</span><span class="sxs-lookup"><span data-stu-id="8de07-148">Configuration and deployment</span></span>

<span data-ttu-id="8de07-149">構成と展開を計画する主要分野は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8de07-149">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="8de07-150">リソースアカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="8de07-150">Resource account provisioning</span></span>
- <span data-ttu-id="8de07-151">デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="8de07-151">Device deployment</span></span>
- <span data-ttu-id="8de07-152">Microsoft Teams アプリケーションと周辺機器構成のコラボレーションバー</span><span class="sxs-lookup"><span data-stu-id="8de07-152">Collaboration bars for Microsoft Teams application and peripheral device configuration</span></span>
- <span data-ttu-id="8de07-153">テスト</span><span class="sxs-lookup"><span data-stu-id="8de07-153">Testing</span></span>
- <span data-ttu-id="8de07-154">資産管理</span><span class="sxs-lookup"><span data-stu-id="8de07-154">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="8de07-155">アカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="8de07-155">Account provisioning</span></span>

<span data-ttu-id="8de07-156">Microsoft 365 リソースアカウントを使用して、ユーザーがコラボレーションバーを利用できるようにする場合は、「 [microsoft 365 管理センターを使用してリソースアカウントを作成](resource-account-ui.md) する」の手順に従って、1つのコラボレーションバーに対して microsoft 365 リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8de07-156">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="8de07-157">また、組織が直接ルーティングを使用していない場合は、会議室のライセンスをリソースアカウントに追加する必要があります。また、外部電話番号への通話を発信または受信したい場合は、通話プランまたはビジネスボイスライセンスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8de07-157">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Calling Plan or Business Voice license if your organization is not using Direct Routing.</span></span>

<span data-ttu-id="8de07-158">プライベートで使用するためにコラボレーションバーを個々のユーザーに割り当てる場合は、追加のアカウントを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8de07-158">If you want to assign collaboration bars to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="8de07-159">ユーザーは個人アカウントを使用してコラボレーションバーにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="8de07-159">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="8de07-160">Microsoft 365 リソースアカウントの表示名をわかりやすく簡単に理解できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8de07-160">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="8de07-161">これらは、Microsoft Teams のコラボレーションバーを検索して追加するときにユーザーに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="8de07-161">These are the names that users will see when searching for and adding collaboration bars for Microsoft Teams to meetings.</span></span> <span data-ttu-id="8de07-162">*サイト* - *ルーム名*(*最大会議*室の容量) などの規則を使うことができます。たとえば、curie の4人の人物の会議室には、表示名として「LON-curie (4)」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="8de07-162">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="8de07-164">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="8de07-164">Decision points</span></span>|<ul><li><span data-ttu-id="8de07-165">専用リソースアカウントの名前付け規則を決定します。</span><span class="sxs-lookup"><span data-stu-id="8de07-165">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="8de07-166">個別のアカウントを作成するか、一括プロビジョニングスクリプトを使用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8de07-166">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="8de07-168">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8de07-168">Next steps</span></span>|<ul><li><span data-ttu-id="8de07-169">デバイスの展開の計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="8de07-169">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="8de07-170">デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="8de07-170">Device deployment</span></span>

<span data-ttu-id="8de07-171">次に、デバイスと割り当てられた周辺機器をルームに配信するための計画を作成してから、インストールと構成に進みます。</span><span class="sxs-lookup"><span data-stu-id="8de07-171">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="8de07-173">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="8de07-173">Decision points</span></span>|<ul><li><span data-ttu-id="8de07-174">サイトごとの展開を管理するユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="8de07-174">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="8de07-175">Microsoft Teams on the site のコラボレーションバーをインストールし、構成とテストに着手するリソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="8de07-175">Identify the resources who will install the collaboration bars for Microsoft Teams on site and undertake the configuration and testing.</span></span></li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="8de07-177">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8de07-177">Next steps</span></span>|<ul><li><span data-ttu-id="8de07-178">デバイスのテストを開始します。</span><span class="sxs-lookup"><span data-stu-id="8de07-178">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="8de07-179">テスト</span><span class="sxs-lookup"><span data-stu-id="8de07-179">Testing</span></span>

<span data-ttu-id="8de07-180">Microsoft Teams のコラボレーションバーが展開されたら、それをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8de07-180">After the collaboration bars for Microsoft Teams have been deployed, you should test them.</span></span> <span data-ttu-id="8de07-181">デバイスにサインインし、展開されたデバイスで予期される機能が動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8de07-181">Sign in to the device and check that the expected capabilities are working on the deployed device.</span></span> <span data-ttu-id="8de07-182">Microsoft Teams 管理センターの [**デバイス**] タブの [**コラボレーションバー** ] セクションに、デバイスが表示されていることを確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8de07-182">We highly recommend that you verify that the devices are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="8de07-183">また、さまざまなテスト通話と会議を行って、品質とパフォーマンスをチェックすることも重要です。</span><span class="sxs-lookup"><span data-stu-id="8de07-183">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="8de07-184">Microsoft Teams の一般的なロールアウトの一環として、通話品質ダッシュボードの構築ファイル (CQD) を構成し、品質の傾向を監視し、エクスペリエンスレビュープロセスに参加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8de07-184">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="8de07-185">詳細については、「 [エクスペリエンスの品質レビューガイド](https://aka.ms/qerguide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8de07-185">For more information, see the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

### <a name="asset-management"></a><span data-ttu-id="8de07-186">資産管理</span><span class="sxs-lookup"><span data-stu-id="8de07-186">Asset management</span></span>

<span data-ttu-id="8de07-187">展開の一環として、ルーム名、サインインしたリソースアカウント、および割り当てられた周辺機器を使用して、資産登録を更新します。</span><span class="sxs-lookup"><span data-stu-id="8de07-187">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8de07-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="8de07-188">Related topics</span></span>

[<span data-ttu-id="8de07-189">Microsoft Teams 管理センターを使用して Microsoft Teams のコラボレーションバーのアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="8de07-189">Configure accounts for collaboration bars for Microsoft Teams using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
