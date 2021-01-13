---
title: Skype for Business Server でメディア バイパスを使用せずにトランクを構成する
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
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: '概要: Skype for Business Server でメディア バイパスが有効になっていないトランクを構成します。'
ms.openlocfilehash: c7941087dc2af820969a80cf68e8d01aa4356948
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803977"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="64a02-103">Skype for Business Server でメディア バイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="64a02-103">Configure a trunk without media bypass in Skype for Business Server</span></span>

<span data-ttu-id="64a02-104">**概要:** Skype for Business Server でメディア バイパスを有効にせずにトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="64a02-104">**Summary:** Configure a trunk without media bypass enabled for Skype for Business Server.</span></span>

<span data-ttu-id="64a02-105">メディア バイパスを無効にしてトランクを構成する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64a02-105">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="64a02-106">メディア バイパスを有効にしたトランクを構成する場合は、「Skype for Business Server でメディア バイパスを使用してトランクを構成する [」を参照してください](configure-trunk-with-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="64a02-106">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="64a02-p102">以下で説明するトランク構成とは、トランクに適用される一連のパラメーターをグループ化したものです。これらのパラメーターは、このトランク構成に割り当てられたものです。特定のトランク構成は、グローバルに (つまり特定のサイトまたはプール構成を持っていないすべてのトランクを対象とする)、またはサイトあるいはプールに対してスコープ指定できます。プールレベル トランク構成は、単一のトランクに固有のトランク構成のスコープを指定する目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="64a02-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="64a02-110">メディア バイパスを無効にしてトランクを構成するには</span><span class="sxs-lookup"><span data-stu-id="64a02-110">To configure a trunk without media bypass</span></span>

1. <span data-ttu-id="64a02-111">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="64a02-111">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="64a02-112">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-112">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="64a02-113">[**トランク構成**] ページで、次のいずれかの方法を使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="64a02-113">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="64a02-114">既存のトランク (たとえば、[**グローバル**] トランク) をダブルクリックして [**トランク構成の編集**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="64a02-114">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="64a02-115">[**新規**] をクリックし、新しいトランクのスコープ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="64a02-115">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="64a02-116">**[サイト トランク**]: [サイトの選択]でこのトランク構成のサイトを選択し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-116">**Site trunk**: Choose the site for this trunk configuration in **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="64a02-117">サイトに対してトランク構成が既に作成されている場合、[**サイトの選択**] にはサイトは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="64a02-117">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="64a02-118">このトランク構成は、サイト内のすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="64a02-118">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="64a02-119">[**プール トランク**]: [**サービスの選択**] で、このトランク構成が適用されるトランクの名前を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-119">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="64a02-120">このトランクには、ルート トランク、またはトポロジ ビルダーで定義されている追加のトランクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="64a02-120">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="64a02-121">特定のトランクに対してトランク構成が既に作成されている場合、[**サービスの選択**] にはトランクは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="64a02-121">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="64a02-122">トランク構成のスコープは、選択した後は変更できません。</span><span class="sxs-lookup"><span data-stu-id="64a02-122">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="64a02-123">>名 **フィールド** には、トランク構成に関連付けられているサイトまたはサービスの名前が事前に入力され、変更できません。</span><span class="sxs-lookup"><span data-stu-id="64a02-123">> The **Name** field is pre-populated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="64a02-124">次のいずれかの [**暗号化サポート レベル**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="64a02-124">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="64a02-125">**必須**: 仲介サーバーとゲートウェイまたは PBX (Private Branch eXchange) 間のトラフィックを保護するために、セキュア リアルタイム転送プロトコル (SRTP) 暗号化を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64a02-125">**Required**: Secure Realtime Transport Protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or Private Branch eXchange (PBX).</span></span>

   - <span data-ttu-id="64a02-126">**[省略可能]**:  サービス プロバイダーまたは機器の製造メーカーがサポートしている場合、SRTP 暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="64a02-126">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="64a02-127">**[サポート対象外]**: サービス プロバイダーまたは機器の製造メーカーが SRTP 暗号化をサポートしていないため、SRTP 暗号化は使用されません。</span><span class="sxs-lookup"><span data-stu-id="64a02-127">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

5. <span data-ttu-id="64a02-128">[**メディア バイパスを有効にする**] チェック ボックスがオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="64a02-128">Be sure that the **Enable media bypass** check box is cleared.</span></span>

6. <span data-ttu-id="64a02-129">既知のメディア終端ポイント (たとえば、メディア終端が信号終端と同じ IP を持つ公衆交換電話網 (PSTN) ゲートウェイ) がある場合は、[集中メディア処理] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="64a02-129">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a Public Switched Telephone Network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="64a02-130">トランクに既知のメディア終端ポイントがない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="64a02-130">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

7. <span data-ttu-id="64a02-131">トランク ピアが仲介サーバーからの SIP REFER 要求の受信をサポートしている場合は、[ゲートウェイへの参照の送信を有効にする] チェック ボックス **を** オンにします。</span><span class="sxs-lookup"><span data-stu-id="64a02-131">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

8. <span data-ttu-id="64a02-132">(省略可) トランク間ルーティングを有効にするには、このトランク構成に PSTN 使用法レコードを関連付けして、構成します。</span><span class="sxs-lookup"><span data-stu-id="64a02-132">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="64a02-133">このトランク構成に関連付けられた PSTN 使用法は、Skype for Business Server エンドポイントから発信されていないトランク経由のすべての着信呼び出しに適用されます。</span><span class="sxs-lookup"><span data-stu-id="64a02-133">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="64a02-134">トランク構成に関連付けられた PSTN 使用法レコードを管理するには、以下の方法の 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="64a02-134">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="64a02-135">展開で使用できるすべての PSTN 使用法レコードの一覧から 1 つ以上のレコードエンタープライズ VoIP選択] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="64a02-135">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="64a02-136">このトランク構成に関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-136">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="64a02-137">PSTN 使用法レコードをこのトランク構成から削除するには、レコードを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-137">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="64a02-138">新しい PSTN 使用法レコードを定義してこのトランク構成に関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="64a02-138">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="64a02-139">a. </span><span class="sxs-lookup"><span data-stu-id="64a02-139">a.</span></span> <span data-ttu-id="64a02-140">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-140">Click **New**.</span></span>

     <span data-ttu-id="64a02-141">b.</span><span class="sxs-lookup"><span data-stu-id="64a02-141">b.</span></span> <span data-ttu-id="64a02-142">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="64a02-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="64a02-p111">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[**名前**] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="64a02-p111">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="64a02-145">c.</span><span class="sxs-lookup"><span data-stu-id="64a02-145">c.</span></span> <span data-ttu-id="64a02-146">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="64a02-146">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="64a02-147">展開で使用可能なすべてのルートの一覧から 1 つ以上のルートを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="64a02-147">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="64a02-148">この PSTN 使用法レコードに関連付けるルートを強調表示して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-148">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="64a02-149">PSTN 使用法レコードからルートを削除するには、ルートを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-149">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="64a02-150">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-150">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="64a02-151">詳細については [、「Skype for Business でのボイス ルートの作成または変更」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="64a02-151">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="64a02-152">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-152">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="64a02-153">d. </span><span class="sxs-lookup"><span data-stu-id="64a02-153">d.</span></span> <span data-ttu-id="64a02-154">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-154">Click **OK**.</span></span>

   - <span data-ttu-id="64a02-155">このトランク構成にすでに関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="64a02-155">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="64a02-156">a. </span><span class="sxs-lookup"><span data-stu-id="64a02-156">a.</span></span> <span data-ttu-id="64a02-157">編集する PSTN 使用法レコードを選択して、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-157">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

     <span data-ttu-id="64a02-158">b.</span><span class="sxs-lookup"><span data-stu-id="64a02-158">b.</span></span> <span data-ttu-id="64a02-159">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="64a02-159">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="64a02-160">展開で使用可能なすべてのルートの一覧から 1 つ以上のルートを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="64a02-160">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="64a02-161">この PSTN 使用法レコードに関連付けるルートを強調表示して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-161">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="64a02-162">PSTN 使用法レコードからルートを削除するには、ルートを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-162">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="64a02-163">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-163">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="64a02-164">詳細については [、「Skype for Business でのボイス ルートの作成または変更」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="64a02-164">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="64a02-165">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-165">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="64a02-166">c.</span><span class="sxs-lookup"><span data-stu-id="64a02-166">c.</span></span> <span data-ttu-id="64a02-167">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-167">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="64a02-168">構成するトランクに関連付けられている仲介サーバー ピアに従って PSTN 使用法レコードを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="64a02-168">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="64a02-169">仲介サーバー ピアが PSTN ゲートウェイまたはセッション ボーダー コントローラー (SBC) である場合は、トランク構成を、PSTN 宛先または Skype for Business Server 経由で接続された他のダウンストリーム システムにルーティングする PSTN 使用法レコードに関連付けないでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64a02-169">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

9. <span data-ttu-id="64a02-170">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="64a02-170">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="64a02-171">リスト内でのレコードの位置を変更するには、PSTN 使用法レコードを選択し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-171">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="64a02-172">トランク構成の PSTN 使用法レコードのリスト内の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="64a02-172">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="64a02-173">Skype for Business Server は、一覧を上から下へスキャンします。</span><span class="sxs-lookup"><span data-stu-id="64a02-173">Skype for Business Server traverses the list from top to down.</span></span>

10. <span data-ttu-id="64a02-174">[**RTP ラッチを有効にする**] は、NAT またはファイアウォール背後のクライアントと、ラッチングをサポートする SBC のバイパス メディアを有効にする場合に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64a02-174">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

11. <span data-ttu-id="64a02-175">**仲介サーバーのゲートウェイ** ピアへの通話履歴情報の送信を有効にするには、[転送通話履歴を有効にする] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64a02-175">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

12. <span data-ttu-id="64a02-176">**P-Asserted-Identity** の転送データを有効にして、仲介サーバー側とゲートウェイ側 (またはその逆) の間で PAI 呼び出し元情報を転送できる必要があります (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="64a02-176">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

13. <span data-ttu-id="64a02-177">[**送信ルーティング フェールオーバー タイマーを有効にする**] は、高速なフェールオーバーを有効にする場合に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64a02-177">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="64a02-178">このトランクに関連付けられたゲートウェイは、発信を処理している 10 秒中に通知をすることができます。</span><span class="sxs-lookup"><span data-stu-id="64a02-178">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="64a02-179">この通知を仲介サーバーが受信しない場合は、別のトランクへの再ルーティングが行われます。</span><span class="sxs-lookup"><span data-stu-id="64a02-179">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="64a02-180">待機時間により反応時間が遅くなるネットワーク、または、応答するのに 10 秒以上かかるゲートウェイでは、高速のフェールオーバーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64a02-180">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

14. <span data-ttu-id="64a02-181">(省略可) トランクの **発信通話番号変換ルール** を関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="64a02-181">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="64a02-182">これらの変換ルールは、発信電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64a02-182">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="64a02-183">展開で使用できるすべての変換ルールの一覧から 1 つ以上のルールを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="64a02-183">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="64a02-184">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-184">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="64a02-185">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-185">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="64a02-186">変換ルールの詳細については [、「Skype for Business Server の変換ルール」を参照してください](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="64a02-186">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="64a02-187">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-187">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="64a02-188">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-188">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="64a02-189">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-189">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="64a02-190">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があることから、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="64a02-190">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

15. <span data-ttu-id="64a02-p128">(省略可) トランクの **発信先通話番号変換ルール** を関連付けて構成します。これらの変換ルールは、発信電話の発信先の電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64a02-p128">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="64a02-193">展開で使用できるすべての変換ルールの一覧から 1 つ以上のルールを選択するには、[選択] エンタープライズ VoIPクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="64a02-193">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="64a02-194">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-194">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="64a02-195">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-195">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="64a02-196">変換ルールの詳細については [、「Skype for Business Server の変換ルール」を参照してください](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="64a02-196">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="64a02-197">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-197">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="64a02-198">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-198">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="64a02-199">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-199">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="64a02-200">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があることから、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="64a02-200">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="64a02-201">トランクの変換ルールが正しい順序で並べ替えされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="64a02-201">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="64a02-202">一覧内でのルールの位置を変更するには、ルール名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-202">To change a rule's position in the list, highlight the rule name, and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="64a02-203">Skype for Business Server は、変換ルールの一覧を上から下にスキャンし、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="64a02-203">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="64a02-204">トランクを構成し、その結果ダイヤルされる番号が複数の変換ルールと一致する可能性がある場合は、制限の厳しいルールを制限の緩いルールよりも上に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="64a02-204">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="64a02-205">たとえば、任意の 11 桁の番号と一致する変換ルール、および +1425 で始まる 11 桁の番号のみと一致する変換ルールを含める場合は、任意の 11 桁の番号に一致するルールが、より制限の厳しいルールの下に並べ替わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="64a02-205">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

17. <span data-ttu-id="64a02-206">トランクの構成が終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-206">When you are finished configuring the trunk, click **OK**.</span></span>

18. <span data-ttu-id="64a02-207">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64a02-207">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="64a02-208">トランクの構成を作成または変更するときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64a02-208">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="64a02-209">詳細については、「操作」のドキュメント [の「Skype for Business](voice-route-config-changes.md) での音声ルーティング構成に対する保留中の変更の公開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64a02-209">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="64a02-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="64a02-210">See also</span></span>

[<span data-ttu-id="64a02-211">Skype for Business Server でメディア バイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="64a02-211">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="64a02-212">変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="64a02-212">Defining Translation Rules</span></span>](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

