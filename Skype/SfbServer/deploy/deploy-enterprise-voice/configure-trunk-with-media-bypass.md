---
title: Skype for Business Server でメディア バイパスを使用してトランクを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: '概要: Skype for Business Server でメディア バイパスを有効にしたトランクを構成します。 これにより、SIP トランク プロバイダーが仲介サーバーをサポートしていると仮定して、仲介サーバーの数を最小限に抑える可能性があります。'
ms.openlocfilehash: 66cb30a3de3680f562596bbbaa5b04ce1d1fbe98
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804067"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="1cb3f-104">Skype for Business Server でメディア バイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="1cb3f-104">Configure a trunk with media bypass in Skype for Business Server</span></span>

<span data-ttu-id="1cb3f-105">**概要:** Skype for Business Server でメディア バイパスを有効にしたトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-105">**Summary:** Configure a trunk with media bypass enabled for Skype for Business Server.</span></span> <span data-ttu-id="1cb3f-106">これにより、SIP トランク プロバイダーが仲介サーバーをサポートしていると仮定して、仲介サーバーの数を最小限に抑える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-106">This will let you minimize the number of Mediation Servers, presuming your SIP trunk provider supports it.</span></span>

<span data-ttu-id="1cb3f-107">メディア バイパスを有効にしたトランクを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-107">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="1cb3f-108">メディア バイパスを無効にしたトランクを構成するには、「Skype for Business Server でメディア バイパスを使用せずにトランクを構成する」 [を参照してください](configure-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-108">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md).</span></span>

<span data-ttu-id="1cb3f-109">メディア バイパスは、展開される仲介サーバーの数を最小限に抑える場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-109">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="1cb3f-110">詳細については [、「Skype for Business でメディア バイパスを計画する」を参照してください。](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="1cb3f-110">For more information, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span></span>

<span data-ttu-id="1cb3f-111">メディア バイパスを有効にすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="1cb3f-112">ただし、SIP トランクでメディア バイパスを有効にする前に、認定 SIP トランク プロバイダーがメディア バイパスをサポートし、シナリオを正常に有効にするための要件に対応できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="1cb3f-113">具体的には、プロバイダーは、組織の内部ネットワーク内のサーバーの IP アドレスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-113">Specifically, the provider must have the IP addresses of servers in your organization's internal network.</span></span>

> [!NOTE]
> <span data-ttu-id="1cb3f-114">メディア バイパスは、すべての公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、およびセッション ボーダー コントローラー (SBC) と相互運用できるとは言えな。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-114">Media bypass will not interoperate with every Public Switched Telephone Network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="1cb3f-115">Microsoft は、認定パートナーと一連の PSTN ゲートウェイと SPC をテストしました。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners.</span></span> <span data-ttu-id="1cb3f-116">メディア バイパスは [、Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) のテレフォニー インフラストラクチャ ページに表示される製品とバージョンでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-116">Media bypass is supported only with products and versions that are listed on the [Telephony Infrastructure for Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span>

<span data-ttu-id="1cb3f-117">以下に示すトランク構成は、このトランク構成が割り当てられたトランクに適用される一連のパラメーターをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-117">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="1cb3f-118">特定のトランク構成は、グローバル (より具体的なサイトまたはプール構成を持たないすべてのトランク)、サイト、またはプールにスコープを設定できます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-118">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="1cb3f-119">プール レベルのトランク構成は、特定のトランク構成のスコープを 1 つのトランクに設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-119">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="1cb3f-120">メディア バイパスを使用してトランクを構成するには</span><span class="sxs-lookup"><span data-stu-id="1cb3f-120">To configure a trunk with media bypass</span></span>

1. <span data-ttu-id="1cb3f-121">Skype for Business Server コントロール パネルを開く</span><span class="sxs-lookup"><span data-stu-id="1cb3f-121">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="1cb3f-122">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-122">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="1cb3f-123">[**トランク構成**] ページで、次のいずれかの方法を使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-123">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="1cb3f-124">既存のトランク (たとえば、[**グローバル**] トランク) をダブルクリックして [**トランク構成の編集**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-124">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="1cb3f-125">[**新規**] をクリックし、新しいトランクのスコープ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-125">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="1cb3f-126">**[サイト トランク**]: [サイトの選択]からこのトランク構成のサイトを選択し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-126">**Site trunk**: Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="1cb3f-127">サイトに対してトランク構成が既に作成されている場合、[**サイトの選択**] にはサイトは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-127">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="1cb3f-128">このトランク構成は、サイト内のすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-128">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="1cb3f-129">**[プール トランク**]: このトランク構成が適用されるトランクの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-129">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="1cb3f-130">このトランクは、ルート トランク、またはトポロジ ビルダーで定義されている追加のトランクにできます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-130">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="1cb3f-131">[サービス **の選択] で** **[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-131">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="1cb3f-132">特定のトランクに対してトランク構成が既に作成されている場合、[**サービスの選択**] にはトランクは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-132">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="1cb3f-133">トランク構成のスコープは、選択した後は変更できません。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-133">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="1cb3f-134">>名 **フィールド** には、トランク構成に関連付けられているサイトまたはサービスの名前が事前に入力され、変更できません。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-134">> The **Name** field is prepopulated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="1cb3f-135">サポートされる最大早期ダイアログ **で値を指定します**。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-135">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="1cb3f-136">これは、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラー (SBC) が仲介サーバーに送信した INVITE に対して受信できるフォークされた応答の最大数です。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-136">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="1cb3f-137">既定値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-137">The default value is 20.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1cb3f-138">この値を変更する前に、サービス プロバイダーまたは機器の製造メーカーに、システムの機能の詳細について問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-138">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

5. <span data-ttu-id="1cb3f-139">次のいずれかの [**暗号化サポート レベル**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-139">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="1cb3f-140">[**必須**]: 仲介サーバーとゲートウェイまたは構内交換機 (PBX) 間のトラフィック保護に使用する目的で、セキュア リアルタイム転送プロトコル (SRTP) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-140">**Required**: Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>

   - <span data-ttu-id="1cb3f-141">**[省略可能]**:  サービス プロバイダーまたは機器の製造メーカーがサポートしている場合、SRTP 暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-141">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="1cb3f-142">**[サポート対象外]**: サービス プロバイダーまたは機器の製造メーカーが SRTP 暗号化をサポートしていないため、SRTP 暗号化は使用されません。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-142">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6. <span data-ttu-id="1cb3f-143">トランク ピアによる処理で、メディアが仲介サーバーをバイパスするようにする場合は、**[メディア バイパスを有効にする]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-143">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1cb3f-144">メディア バイパスが正常に機能するには、PSTN ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラーが一定の機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-144">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="1cb3f-145">詳細については [、「Skype for Business でメディア バイパスを計画する」を参照してください](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-145">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

7. <span data-ttu-id="1cb3f-p113">既知のメディア終端ポイント (たとえば、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイ) がある場合は、**[集中メディア処理]** チェック ボックスをオンにします。 トランクに既知のメディア終端ポイントがない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-p113">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8. <span data-ttu-id="1cb3f-148">トランク ピアが仲介サーバーからの SIP REFER 要求の受信をサポートしている場合は、[ゲートウェイへの参照の送信を有効にする] チェック ボックス **を** オンにします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-148">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1cb3f-149">**[メディア バイパスを有効にする]** オプションが選択されている場合にこのオプションを無効にするには、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-149">If you disable this option while the **Enable media bypass** option is selected, additional settings are required.</span></span> <span data-ttu-id="1cb3f-150">トランク ピアが仲介サーバーからの SIP REFER 要求の受信をサポートしておらず、メディア バイパスが有効な場合は、メディア バイパスの適正な状態をサポートするため、**Set-CsTrunkConfiguration** コマンドレットを実行して、アクティブな通話と保留通話の RTCP を無効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-150">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the **Set-CsTrunkConfiguration** cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="1cb3f-151">または、転送された通話をメディアバイパスにし、ゲートウェイが SIP REFER 要求をサポートしていない場合は、[サード パーティ通話コントロールを使用して参照を有効にする] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-151">Alternatively, you can select **Enable refer using third-party-call control** if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

9. <span data-ttu-id="1cb3f-152">(省略可) トランク間ルーティングを有効にするには、このトランク構成に PSTN 使用法レコードを関連付けして、構成します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-152">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="1cb3f-153">このトランク構成に関連付けられた PSTN 使用法は、Skype for Business Server エンドポイントからの発信元ではないトランク経由のすべての着信呼び出しに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-153">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="1cb3f-154">トランク構成に関連付けられた PSTN 使用法レコードを管理するには、以下の方法の 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-154">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="1cb3f-155">展開で使用できるすべての PSTN 使用法レコードの一覧から 1 つ以上のレコードエンタープライズ VoIP選択] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-155">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="1cb3f-156">このトランク構成に関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-156">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="1cb3f-157">PSTN 使用法レコードをこのトランク構成から削除するには、レコードを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-157">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="1cb3f-158">新しい PSTN 使用法レコードを定義してこのトランク構成に関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-158">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="1cb3f-159">a. </span><span class="sxs-lookup"><span data-stu-id="1cb3f-159">a.</span></span> <span data-ttu-id="1cb3f-160">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-160">Click **New**.</span></span>

     <span data-ttu-id="1cb3f-161">b.</span><span class="sxs-lookup"><span data-stu-id="1cb3f-161">b.</span></span> <span data-ttu-id="1cb3f-162">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-162">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1cb3f-p119">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[**名前**] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-p119">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="1cb3f-165">c.</span><span class="sxs-lookup"><span data-stu-id="1cb3f-165">c.</span></span> <span data-ttu-id="1cb3f-166">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-166">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="1cb3f-167">展開で使用可能なすべてのルートの一覧から 1 つ以上のルートを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-167">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="1cb3f-168">この PSTN 使用法レコードに関連付けるルートを強調表示して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-168">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="1cb3f-169">PSTN 使用法レコードからルートを削除するには、ルートを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-169">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="1cb3f-170">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-170">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="1cb3f-171">詳細については [、「Skype for Business でのボイス ルートの作成または変更」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-171">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="1cb3f-172">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-172">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="1cb3f-173">d. </span><span class="sxs-lookup"><span data-stu-id="1cb3f-173">d.</span></span> <span data-ttu-id="1cb3f-174">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-174">Click **OK**.</span></span>

     - <span data-ttu-id="1cb3f-175">このトランク構成にすでに関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-175">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

       <span data-ttu-id="1cb3f-176">a. </span><span class="sxs-lookup"><span data-stu-id="1cb3f-176">a.</span></span> <span data-ttu-id="1cb3f-177">編集する PSTN 使用法レコードを選択して、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-177">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

       <span data-ttu-id="1cb3f-178">b.</span><span class="sxs-lookup"><span data-stu-id="1cb3f-178">b.</span></span> <span data-ttu-id="1cb3f-179">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="1cb3f-180">展開で使用可能なすべてのルートの一覧から 1 つ以上のルートを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="1cb3f-181">この PSTN 使用法レコードに関連付けるルートを強調表示して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

   - <span data-ttu-id="1cb3f-182">PSTN 使用法レコードからルートを削除するには、ルートを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="1cb3f-183">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="1cb3f-184">詳細については [、「Skype for Business でのボイス ルートの作成または変更」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-184">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="1cb3f-185">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="1cb3f-186">c.</span><span class="sxs-lookup"><span data-stu-id="1cb3f-186">c.</span></span> <span data-ttu-id="1cb3f-187">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-187">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="1cb3f-188">構成するトランクに関連付けられている仲介サーバー ピアに従って PSTN 使用法レコードを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-188">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="1cb3f-189">仲介サーバー ピアが PSTN ゲートウェイまたはセッション ボーダー コントローラー (SBC) である場合は、トランク構成を、PSTN 宛先または Skype for Business Server 経由で接続された他のダウンストリーム システムにルーティングする PSTN 使用法レコードに関連付けないでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

10. <span data-ttu-id="1cb3f-190">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="1cb3f-191">リスト内でのレコードの位置を変更するには、PSTN 使用法レコードを選択し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-191">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1cb3f-192">トランク構成の PSTN 使用法レコードのリスト内の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="1cb3f-193">Skype for Business Server は、一覧を上から下へスキャンします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-193">Skype for Business Server traverses the list from top to down.</span></span>

11. <span data-ttu-id="1cb3f-194">**RTP ラッチを有効** にして、ネットワーク アドレス変換 (NAT) またはファイアウォールの背後にあるクライアントと、ラッチをサポートする SBC のバイパス メディアを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="1cb3f-195">**仲介サーバーのゲートウェイ** ピアへの通話履歴情報の送信を有効にするには、[転送通話履歴を有効にする] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="1cb3f-196">**P-Asserted-Identity (P-Asserted-Identity)** の転送データを有効にして、P-Asserted-Identity (PAI) 呼び出し元の情報を仲介サーバー側とゲートウェイ側 (またはその逆) 間で転送する (存在する場合) 有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="1cb3f-197">[**送信ルーティング フェールオーバー タイマーを有効にする**] は、高速なフェールオーバーを有効にする場合に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="1cb3f-198">このトランクに関連付けられたゲートウェイは、発信を処理している 10 秒中に通知をすることができます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="1cb3f-199">この通知を仲介サーバーが受信しない場合は、別のトランクへの再ルーティングが行われます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="1cb3f-200">待機時間により反応時間が遅くなるネットワーク、または、応答するのに 10 秒以上かかるゲートウェイでは、高速のフェールオーバーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="1cb3f-201">(省略可) トランクの **発信通話番号変換ルール** を関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="1cb3f-202">これらの変換ルールは、発信電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-202">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="1cb3f-203">展開で使用できるすべての変換ルールの一覧から 1 つ以上のルールを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="1cb3f-204">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="1cb3f-205">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="1cb3f-206">変換ルールの詳細については [、「Skype for Business Server の変換ルール」を参照してください](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-206">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="1cb3f-207">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="1cb3f-208">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-208">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="1cb3f-209">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-209">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="1cb3f-210">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があることから、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-210">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="1cb3f-p136">(省略可) トランクの **発信先通話番号変換ルール** を関連付けて構成します。これらの変換ルールは、発信電話の発信先の電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-p136">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="1cb3f-213">展開で使用できるすべての変換ルールの一覧から 1 つ以上のルールを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-213">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="1cb3f-214">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-214">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="1cb3f-215">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-215">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="1cb3f-216">変換ルールの詳細については [、「Skype for Business Server の変換ルール」を参照してください](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-216">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="1cb3f-217">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-217">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="1cb3f-218">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-218">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="1cb3f-219">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-219">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="1cb3f-220">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があることから、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-220">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

17. <span data-ttu-id="1cb3f-221">トランクの変換ルールが正しい順序で並べ替えされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-221">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="1cb3f-222">一覧内でのルールの位置を変更するには、ルール名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-222">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1cb3f-223">Skype for Business Server は、変換ルールの一覧を上から下にスキャンし、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-223">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="1cb3f-224">トランクを構成し、その結果ダイヤルされる番号が複数の変換ルールと一致する可能性がある場合は、制限の厳しいルールを制限の緩いルールよりも上に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-224">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="1cb3f-225">たとえば、任意の 11 桁の番号と一致する変換ルール、および +1425 で始まる 11 桁の番号のみと一致する変換ルールを含める場合は、任意の 11 桁の番号に一致するルールが、より制限の厳しいルールの下に並べ替わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-225">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

18. <span data-ttu-id="1cb3f-226">トランクの構成が終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-226">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="1cb3f-227">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-227">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1cb3f-228">トランクの構成を作成または変更するときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-228">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1cb3f-229">詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-229">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

<span data-ttu-id="1cb3f-230">トランクの構成が完了したら、「展開」のドキュメントの [「Skype for Business Server](deploy-media-bypass.md) でのメディア バイパスの展開」の説明に従って、グローバル メディア バイパス オプションを選択して、メディア バイパスの構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="1cb3f-230">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Deploy media bypass in Skype for Business Server](deploy-media-bypass.md) in the Deployment documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="1cb3f-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cb3f-231">See also</span></span>

[<span data-ttu-id="1cb3f-232">Skype for Business Server でメディア バイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="1cb3f-232">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="1cb3f-233">Skype for Business Server でのメディア バイパスの展開</span><span class="sxs-lookup"><span data-stu-id="1cb3f-233">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

[<span data-ttu-id="1cb3f-234">変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="1cb3f-234">Defining Translation Rules</span></span>](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[<span data-ttu-id="1cb3f-235">メディア バイパスの構成</span><span class="sxs-lookup"><span data-stu-id="1cb3f-235">Configure Media Bypass</span></span>](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

