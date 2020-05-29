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
ms.openlocfilehash: 71f9482dd5f42ddeb56b32c1a92db033d1f179f7
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410452"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a><span data-ttu-id="924be-103">Microsoft Teams のコラボレーションバーの展開</span><span class="sxs-lookup"><span data-stu-id="924be-103">Deploy collaboration bars for Microsoft Teams</span></span>

<span data-ttu-id="924be-104">Microsoft Teams のコラボレーションバーの展開は、次のフェーズに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="924be-104">Deployment of collaboration bars for Microsoft Teams can be broken down into the following phases:</span></span>

- <span data-ttu-id="924be-105">**サイトの準備**展開場所 (会議室) が展開要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="924be-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="924be-106">**サービスの準備**リソースアカウントを作成してデバイスに割り当てる ([「Microsoft 365 管理センターを使用してリソースアカウントを作成する」を参照](resource-account-ui.md)してください)。</span><span class="sxs-lookup"><span data-stu-id="924be-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="924be-107">専用の room ライセンスを使用することをお勧めしますが、適切なライセンスのエンドユーザーアカウントでコラボレーションバーにサインインすることもできます。</span><span class="sxs-lookup"><span data-stu-id="924be-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to collaboration bars.</span></span>
- <span data-ttu-id="924be-108">**構成と展開**会議室でコラボレーションバーを設定し、必要な周辺機器を接続します (共同作業バーについては、製造元のマニュアルを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="924be-108">**Configuration and deployment** Set up collaboration bars in rooms and connect the peripheral devices you need (see the manufacturer's documentation for your collaboration bars).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="924be-109">サイトの準備</span><span class="sxs-lookup"><span data-stu-id="924be-109">Site readiness</span></span>

<span data-ttu-id="924be-110">注文されたデバイスは組織に配信されますが、ネットワーク、設備、およびオーディオビジュアルチームと協力して、展開要件が満たされていることを確認し、各サイトと部屋の電力、ネットワーキング、ディスプレイの準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="924be-110">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="924be-111">コラボレーションバーサイトについての推奨事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="924be-111">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="924be-112">サイズが最大4人のルーム</span><span class="sxs-lookup"><span data-stu-id="924be-112">Rooms up to 4 people in size</span></span>
- <span data-ttu-id="924be-113">専用リソースアカウント</span><span class="sxs-lookup"><span data-stu-id="924be-113">Dedicated resource accounts</span></span>
- <span data-ttu-id="924be-114">タッチ対応ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="924be-114">Touch-enabled displays</span></span>
- <span data-ttu-id="924be-115">イーサネット接続</span><span class="sxs-lookup"><span data-stu-id="924be-115">Ethernet cabling</span></span>
- <span data-ttu-id="924be-116">Microsoft Teams メディアのネットワークで有効になっている QoS (Quality of Service)</span><span class="sxs-lookup"><span data-stu-id="924be-116">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="924be-117">物理的なインストールの考慮事項については、製造元のマニュアルを参照してください。いずれかの場合は、画面をインストールして起動し、ケーブルを接続する前に、オーディオビジュアルチームのエクスペリエンスを活用してください。</span><span class="sxs-lookup"><span data-stu-id="924be-117">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="924be-118">必ず、「[ネットワーク](../prepare-network.md)の帯域幅の計画」を確認して、リアルタイムトラフィックに対するネットワークの適合性を評価してください。</span><span class="sxs-lookup"><span data-stu-id="924be-118">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="924be-119">Teams デバイスとインターネットの間にプロキシサーバーを配置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="924be-119">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="924be-120">プロキシサーバーと Teams の詳細については、「 [teams のプロキシサーバー](../proxy-servers-for-skype-for-business-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="924be-120">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="924be-122">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="924be-122">Decision points</span></span>|<ul><li><span data-ttu-id="924be-123">サイトが Microsoft Teams のコラボレーションバーのサイト準備要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="924be-123">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="924be-124">各サイトに十分な帯域幅が用意されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="924be-124">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="924be-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="924be-126">Next steps</span></span>|<ul><li><span data-ttu-id="924be-127">コラボレーションバーの展開と構成の計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="924be-127">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="924be-128">サービスの準備</span><span class="sxs-lookup"><span data-stu-id="924be-128">Service readiness</span></span>

<span data-ttu-id="924be-129">コラボレーションバーを展開する前に、Microsoft 365 リソースアカウント、エンドユーザーアカウント、または両方を組み合わせて使用するかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924be-129">Before you deploy your collaboration bars, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="924be-130">Microsoft 365 リソースアカウントは、会議室、プロジェクターなどの特定のリソース専用のメールボックスおよび Teams アカウントです。</span><span class="sxs-lookup"><span data-stu-id="924be-130">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="924be-131">これらのリソースアカウントは、作成時に定義したルールを使って、会議出席依頼に自動的に応答できます。</span><span class="sxs-lookup"><span data-stu-id="924be-131">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="924be-132">プライベート使用のためにコラボレーションバーが特定の個人専用である場合を除き、Microsoft 365 リソースアカウントを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="924be-132">Unless a collaboration bar is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="924be-133">リソースアカウントの使用</span><span class="sxs-lookup"><span data-stu-id="924be-133">Using a resource account</span></span>

<span data-ttu-id="924be-134">Microsoft 365 リソースアカウントを設定する場合は、会議室ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924be-134">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="924be-135">会議室ライセンスには、組織内のユーザーが Outlook または Teams で会議室を予約できるようにするリソースメールボックスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="924be-135">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="924be-136">このライセンスでは、会議参加者間でのビデオおよび音声会議や画面共有も可能です。</span><span class="sxs-lookup"><span data-stu-id="924be-136">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="924be-137">外部の電話番号に対して電話をかけたり、発信したりする必要がある場合は、通話プランまたは Microsoft 365 Business Voice[アドオンライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="924be-137">If you need to receive or make calls to or from an external telephone number, you may need a Calling Plan or Microsoft 365 Business Voice [add-on license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business).</span></span> <span data-ttu-id="924be-138">組織で直接ルーティングを有効にしている場合は、会議室の SKU のみが必要になります。</span><span class="sxs-lookup"><span data-stu-id="924be-138">If you have Direct Routing enabled in your organization, you only need the Meeting Room SKU.</span></span>

<span data-ttu-id="924be-139">リソースアカウントを作成するときに、アカウントに対して自動的に会議出席依頼を承諾または辞退するか、定期的な会議を許可するか、または他のユーザーがリソースを予約できるようにするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="924be-139">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="924be-140">Microsoft 365 リソースアカウントのコラボレーションバーの詳細については、「 [microsoft 365 管理センターを使用してリソースアカウントを作成](resource-account-ui.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="924be-140">For more information about collaboration bars for Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="924be-142">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="924be-142">Decision points</span></span>|<ul><li><span data-ttu-id="924be-143">外部の電話を発信または受信するかどうかを決定し、リソースアカウントのライセンス要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="924be-143">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="924be-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="924be-145">Next steps</span></span>|<ul><li><span data-ttu-id="924be-146">リソースアカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="924be-146">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="924be-147">構成および展開</span><span class="sxs-lookup"><span data-stu-id="924be-147">Configuration and deployment</span></span>

<span data-ttu-id="924be-148">構成と展開の計画は、次の主要領域で構成されています。</span><span class="sxs-lookup"><span data-stu-id="924be-148">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="924be-149">リソースアカウントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="924be-149">Resource account provisioning</span></span>
- <span data-ttu-id="924be-150">デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="924be-150">Device deployment</span></span>
- <span data-ttu-id="924be-151">Microsoft Teams アプリケーションと周辺機器構成のコラボレーションバー</span><span class="sxs-lookup"><span data-stu-id="924be-151">Collaboration bars for Microsoft Teams application and peripheral device configuration</span></span>
- <span data-ttu-id="924be-152"> 試験</span><span class="sxs-lookup"><span data-stu-id="924be-152">Testing</span></span>
- <span data-ttu-id="924be-153">資産管理</span><span class="sxs-lookup"><span data-stu-id="924be-153">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="924be-154">アカウントプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="924be-154">Account provisioning</span></span>

<span data-ttu-id="924be-155">Microsoft 365 リソースアカウントを使用して、ユーザーがコラボレーションバーを利用できるようにする場合は、「 [microsoft 365 管理センターを使用してリソースアカウントを作成](resource-account-ui.md)する」の手順に従って、1つのコラボレーションバーに対して microsoft 365 リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="924be-155">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="924be-156">また、組織が直接ルーティングを使用していない場合は、会議室のライセンスをリソースアカウントに追加する必要があります。また、外部電話番号への通話を発信または受信したい場合は、通話プランまたはビジネスボイスライセンスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924be-156">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Calling Plan or Business Voice license if your organization is not using Direct Routing.</span></span>

<span data-ttu-id="924be-157">プライベートで使用するためにコラボレーションバーを個々のユーザーに割り当てる場合は、追加のアカウントを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="924be-157">If you want to assign collaboration bars to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="924be-158">ユーザーは個人アカウントを使用してコラボレーションバーにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="924be-158">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="924be-159">Microsoft 365 リソースアカウントの表示名をわかりやすく簡単に理解できるようにします。</span><span class="sxs-lookup"><span data-stu-id="924be-159">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="924be-160">これらは、Microsoft Teams のコラボレーションバーを検索して追加するときにユーザーに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="924be-160">These are the names that users will see when searching for and adding collaboration bars for Microsoft Teams to meetings.</span></span> <span data-ttu-id="924be-161">*サイト* - *ルーム名*(*最大会議*室の容量) などの規則を使うことができます。たとえば、curie の4人の人物の会議室には、表示名として「LON-curie (4)」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="924be-161">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="924be-163">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="924be-163">Decision points</span></span>|<ul><li><span data-ttu-id="924be-164">専用リソースアカウントの名前付け規則を決定します。</span><span class="sxs-lookup"><span data-stu-id="924be-164">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="924be-165">個別のアカウントを作成するか、一括プロビジョニングスクリプトを使用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="924be-165">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="924be-167">次の手順</span><span class="sxs-lookup"><span data-stu-id="924be-167">Next steps</span></span>|<ul><li><span data-ttu-id="924be-168">まず、デバイスの展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="924be-168">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="924be-169">デバイスの展開</span><span class="sxs-lookup"><span data-stu-id="924be-169">Device deployment</span></span>

<span data-ttu-id="924be-170">次に、デバイスと割り当てられた周辺機器をルームに配信するための計画を作成してから、インストールと構成に進みます。</span><span class="sxs-lookup"><span data-stu-id="924be-170">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="924be-172">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="924be-172">Decision points</span></span>|<ul><li><span data-ttu-id="924be-173">サイトごとの展開を管理するユーザーを決定する。</span><span class="sxs-lookup"><span data-stu-id="924be-173">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="924be-174">Microsoft Teams on the site のコラボレーションバーをインストールし、構成とテストに着手するリソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="924be-174">Identify the resources who will install the collaboration bars for Microsoft Teams on site and undertake the configuration and testing.</span></span></li></ul>|
| ![次のステップを示すアイコン](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="924be-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="924be-176">Next steps</span></span>|<ul><li><span data-ttu-id="924be-177">デバイスのテストを開始します。</span><span class="sxs-lookup"><span data-stu-id="924be-177">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="924be-178"> 試験</span><span class="sxs-lookup"><span data-stu-id="924be-178">Testing</span></span>

<span data-ttu-id="924be-179">Microsoft Teams のコラボレーションバーが展開されたら、それをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="924be-179">After the collaboration bars for Microsoft Teams have been deployed, you should test them.</span></span> <span data-ttu-id="924be-180">デバイスにサインインし、展開されたデバイスで予期される機能が動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="924be-180">Sign in to the device and check that the expected capabilities are working on the deployed device.</span></span> <span data-ttu-id="924be-181">Microsoft Teams 管理センターの [**デバイス**] タブの [**コラボレーションバー** ] セクションに、デバイスが表示されていることを確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="924be-181">We highly recommend that you verify that the devices are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="924be-182">また、さまざまなテスト通話と会議を行って、品質とパフォーマンスをチェックすることも重要です。</span><span class="sxs-lookup"><span data-stu-id="924be-182">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="924be-183">Microsoft Teams の一般的なロールアウトの一環として、通話品質ダッシュボードの構築ファイル (CQD) を構成し、品質の傾向を監視し、エクスペリエンスレビュープロセスに参加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="924be-183">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="924be-184">詳細については、「[エクスペリエンスの品質レビューガイド](https://aka.ms/qerguide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="924be-184">For more information, see the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

### <a name="asset-management"></a><span data-ttu-id="924be-185">資産管理</span><span class="sxs-lookup"><span data-stu-id="924be-185">Asset management</span></span>

<span data-ttu-id="924be-186">展開の一環として、ルーム名、サインインしたリソースアカウント、および割り当てられた周辺機器を使用して、資産登録を更新します。</span><span class="sxs-lookup"><span data-stu-id="924be-186">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="924be-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="924be-187">Related topics</span></span>

[<span data-ttu-id="924be-188">Microsoft Teams 管理センターを使用して Microsoft Teams のコラボレーションバーのアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="924be-188">Configure accounts for collaboration bars for Microsoft Teams using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
