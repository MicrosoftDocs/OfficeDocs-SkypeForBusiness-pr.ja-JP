---
title: Skype for Business Server でメディアバイパスを使用してトランクを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: '概要: Skype for Business Server でメディアバイパスを有効にしてトランクを構成します。 これにより、SIP トランクのプロバイダーがサポートしている場合に、仲介サーバーの数を最小限に抑えることができるようになります。'
ms.openlocfilehash: 3b51cedfbead08cd70b543e9019c351adcc2a4eb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233672"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="a82ca-104">Skype for Business Server でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="a82ca-104">Configure a trunk with media bypass in Skype for Business Server</span></span>

<span data-ttu-id="a82ca-105">**概要:** Skype for Business Server でメディアバイパスが有効になっているトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-105">**Summary:** Configure a trunk with media bypass enabled for Skype for Business Server.</span></span> <span data-ttu-id="a82ca-106">これにより、SIP トランクのプロバイダーがサポートしている場合に、仲介サーバーの数を最小限に抑えることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-106">This will let you minimize the number of Mediation Servers, presuming your SIP trunk provider supports it.</span></span>

<span data-ttu-id="a82ca-107">メディア バイパスを有効にしてトランクを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-107">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="a82ca-108">メディアのバイパスを無効にしてトランクを構成する方法については、「 [Skype For Business Server でメディアをバイパスせずにトランクを構成](configure-trunk-without-media-bypass.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-108">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md).</span></span>

<span data-ttu-id="a82ca-109">メディアのバイパスは、展開されている仲介サーバーの数を最小化する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a82ca-109">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="a82ca-110">詳細については、「 [Skype For business でメディアバイパスの計画を立てる](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-110">For more information, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span></span>

<span data-ttu-id="a82ca-111">メディアのバイパスを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="a82ca-112">ただし、SIP トランクでメディアバイパスを有効にする前に、認定された SIP トランクのプロバイダーがメディアのバイパスをサポートしており、そのシナリオを正常に有効にするための要件を満たすことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="a82ca-113">具体的には、プロバイダーは、組織の内部ネットワーク内のサーバーの IP アドレスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-113">Specifically, the provider must have the IP addresses of servers in your organization's internal network.</span></span>

> [!NOTE]
> <span data-ttu-id="a82ca-114">メディア バイパスは、すべての公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、およびセッション ボーダー コントローラー (SBC) と相互運用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a82ca-114">Media bypass will not interoperate with every Public Switched Telephone Network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="a82ca-115">マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="a82ca-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners.</span></span> <span data-ttu-id="a82ca-116">メディアのバイパスは、[ [Skype For Business Server のテレフォニーインフラストラクチャ](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)] ページに表示される製品とバージョンでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-116">Media bypass is supported only with products and versions that are listed on the [Telephony Infrastructure for Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span>

<span data-ttu-id="a82ca-p107">以下で説明するトランク構成では、そのトランク構成が割り当てられるトランクに適用される一連のパラメーターがグループ化されています。トランク構成のスコープは、グローバル (サイトまたはプールの構成を持たないすべてのトランクに適用されます)、サイト、またはプールにすることができます。プール レベルのトランク構成は、トランク構成のスコープを 1 つのトランクにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-p107">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="a82ca-120">メディア バイパスを有効にしてトランクを構成するには</span><span class="sxs-lookup"><span data-stu-id="a82ca-120">To configure a trunk with media bypass</span></span>

1. <span data-ttu-id="a82ca-121">Skype for Business Server コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="a82ca-121">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="a82ca-122">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-122">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="a82ca-123">[**トランク構成**] ページで、次のいずれかの方法を使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-123">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="a82ca-124">既存のトランク (たとえば、[**グローバル**] トランク) をダブルクリックして [**トランク構成の編集**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-124">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="a82ca-125">[**新規**] をクリックし、新しいトランク構成のスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-125">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="a82ca-p108">[**サイト トランク**]: [**サイトの選択**] で、このトランク構成のサイトを選択し、[**OK**] をクリックします。サイトに対してトランク構成が既に作成されている場合、[**サイトの選択**] にはサイトは表示されませんので注意してください。このトランク構成はサイトのすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-p108">**Site trunk**: Choose the site for this trunk configuration from **Select a Site**, and then click **OK**. Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**. This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="a82ca-129">[**プール トランク**]: このトランク構成を適用するトランクの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-129">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="a82ca-130">このトランクは、トポロジービルダーで定義されているルートトランクまたは追加の trunks にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-130">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="a82ca-131">[  **サービスの選択**  ] で、[  **OK**  ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-131">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="a82ca-132">トランク構成が既に作成されているトランクは [  **サービスの選択**  ] に表示されません。</span><span class="sxs-lookup"><span data-stu-id="a82ca-132">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a82ca-133">トランク構成のスコープは、選択後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a82ca-133">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="a82ca-134">> **Name**フィールドには、トランク構成に関連するサイトまたはサービスの名前があらかじめ設定されているため、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a82ca-134">> The **Name** field is prepopulated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="a82ca-p111">[**サポートされる最大早期ダイアログ数**] に値を指定します。これは公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラー (SBC) が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。既定値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="a82ca-p111">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a82ca-138">この値を変更する前に、サービス プロバイダーまたは機器の製造メーカーに、システムの機能の詳細について問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-138">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

5. <span data-ttu-id="a82ca-139">次のいずれかの [**暗号化サポート レベル**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-139">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="a82ca-140">[**必須**]: 仲介サーバーとゲートウェイまたは構内交換機 (PBX) 間のトラフィック保護に役立てるために、セキュア リアルタイム転送プロトコル (SRTP) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-140">**Required**: Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>

   - <span data-ttu-id="a82ca-141">[**省略可能**]: サービス プロバイダーまたは機器の製造メーカーがサポートしている場合、SRTP 暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-141">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="a82ca-142">[**サポート対象外**]: サービス プロバイダーまたは機器の製造メーカーが SRTP 暗号化をサポートしていないため、SRTP 暗号化は使用されません。</span><span class="sxs-lookup"><span data-stu-id="a82ca-142">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6. <span data-ttu-id="a82ca-143">トランク ピアによる処理で、メディアが仲介サーバーをバイパスするようにする場合は、[**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-143">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a82ca-144">メディア バイパスが正常に機能するには、PSTN ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラーが一定の機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-144">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="a82ca-145">詳細については、「 [Skype For business のメディアバイパスの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-145">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

7. <span data-ttu-id="a82ca-p113">既知のメディア終端ポイント (たとえば、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイ) がある場合は、[**集中メディア処理**] チェック ボックスをオンにします。トランクに既知のメディア終端ポイントがない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-p113">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8. <span data-ttu-id="a82ca-148">トランクピアが仲介サーバーからの SIP 参照要求の受信をサポートしている場合は、[**ゲートウェイへの参照を有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-148">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a82ca-149">[**メディア バイパスを有効にする**] オプションが選択されている場合にこのオプションを無効にするには、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="a82ca-149">If you disable this option while the **Enable media bypass** option is selected, additional settings are required.</span></span> <span data-ttu-id="a82ca-150">トランク ピアが仲介サーバーからの SIP REFER 要求の受信をサポートしておらず、メディア バイパスが有効な場合は、メディア バイパスの適正な状態をサポートするため、**Set-CsTrunkConfiguration** コマンドレットを実行して、アクティブな通話と保留通話の RTCP を無効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-150">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the **Set-CsTrunkConfiguration** cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="a82ca-151">ゲートウェイが SIP REFER 要求をサポートしていない場合に転送通話をメディア バイパスするには、[**サードパーティ通話コントロールを使用する参照を有効にする**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-151">Alternatively, you can select **Enable refer using third-party-call control** if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

9. <span data-ttu-id="a82ca-152">(オプション) トランク間ルーティングを有効にするには、このトランク構成に PSTN 使用法レコードを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-152">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="a82ca-153">このトランク構成に関連付けられている PSTN 使用状況は、Skype for Business Server エンドポイントから送信されていないトランク経由のすべての着信に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-153">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="a82ca-154">トランク構成に関連付けられた PSTN 使用法レコードを管理するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-154">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="a82ca-155">エンタープライズ Voip 展開で利用できるすべての PSTN 利用状況レコードの一覧から1つまたは複数のレコードを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-155">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a82ca-156">このトランク構成に関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-156">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="a82ca-157">PSTN 使用法レコードをこのトランク構成から削除するには、レコードを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-157">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="a82ca-158">新しい PSTN 使用法レコードを定義してこのトランク構成に関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-158">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="a82ca-159">a.</span><span class="sxs-lookup"><span data-stu-id="a82ca-159">a.</span></span> <span data-ttu-id="a82ca-160">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-160">Click **New**.</span></span>

     <span data-ttu-id="a82ca-161">b.</span><span class="sxs-lookup"><span data-stu-id="a82ca-161">b.</span></span> <span data-ttu-id="a82ca-162">[**名前**] フィールドに、レコードを説明する一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-162">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a82ca-p119">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"**名前**" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="a82ca-p119">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="a82ca-165">c.</span><span class="sxs-lookup"><span data-stu-id="a82ca-165">c.</span></span> <span data-ttu-id="a82ca-166">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="a82ca-166">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="a82ca-167">エンタープライズ Voip 展開で利用可能なすべてのルートの一覧から1つ以上のルートを選ぶには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-167">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a82ca-168">この PSTN 使用状況レコードと関連付けるルートを強調表示し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-168">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="a82ca-169">PSTN 使用法レコードからルートを削除するには、ルートを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-169">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="a82ca-170">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-170">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a82ca-171">詳細については、「 [Skype For business での音声ルートの作成または変更](create-or-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-171">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="a82ca-172">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択して [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-172">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="a82ca-173">d.</span><span class="sxs-lookup"><span data-stu-id="a82ca-173">d.</span></span> <span data-ttu-id="a82ca-174">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-174">Click **OK**.</span></span>

     - <span data-ttu-id="a82ca-175">このトランク構成に既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-175">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

       <span data-ttu-id="a82ca-176">a.</span><span class="sxs-lookup"><span data-stu-id="a82ca-176">a.</span></span> <span data-ttu-id="a82ca-177">編集する PSTN 使用法レコードを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-177">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

       <span data-ttu-id="a82ca-178">b.</span><span class="sxs-lookup"><span data-stu-id="a82ca-178">b.</span></span> <span data-ttu-id="a82ca-179">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="a82ca-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="a82ca-180">エンタープライズ Voip 展開で利用可能なすべてのルートの一覧から1つ以上のルートを選ぶには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a82ca-181">この PSTN 使用状況レコードと関連付けるルートを強調表示し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

   - <span data-ttu-id="a82ca-182">PSTN 使用法レコードからルートを削除するには、ルートを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="a82ca-183">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="a82ca-184">詳細については、「 [Skype For business での音声ルートの作成または変更](create-or-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-184">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="a82ca-185">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択して [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="a82ca-186">c.</span><span class="sxs-lookup"><span data-stu-id="a82ca-186">c.</span></span> <span data-ttu-id="a82ca-187">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-187">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="a82ca-188">構成されるトランクに関連付けられている仲介サーバーピアに応じて PSTN 使用状況レコードを関連付けることが重要です。</span><span class="sxs-lookup"><span data-stu-id="a82ca-188">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="a82ca-189">仲介サーバーのピアが PSTN ゲートウェイまたはセッション境界コントローラー (SBC) である場合は、pstn の接続先または Skype 経由で接続されたその他の下流システムにルーティングする PSTN 使用状況レコードに、トランク構成が関連付けられていないことを強くお勧めします。Business Server の場合。</span><span class="sxs-lookup"><span data-stu-id="a82ca-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

10. <span data-ttu-id="a82ca-190">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="a82ca-191">リスト内のレコードの位置を変更するには、[PSTN 使用状況] レコードを選択し、上向き矢印または下向き矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-191">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a82ca-192">トランク構成内の一覧における PSTN 使用法レコードの順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="a82ca-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="a82ca-193">Skype for Business Server は、リストを上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-193">Skype for Business Server traverses the list from top to down.</span></span>

11. <span data-ttu-id="a82ca-194">ネットワーク アドレス変換 (NAT) またはファイアウォールとラッチをサポートしている SBC の背後にあるクライアントに対してバイパス メディアを有効にするには、[**RTP ラッチを有効にする**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="a82ca-195">仲介サーバーのゲートウェイピアへの通話履歴情報の送信を有効にするには、[転送中の**通話履歴を有効**にする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="a82ca-196">[**転送を有効に**する]-[指定した id データを有効にする] をオンにすると、仲介サーバー側とゲートウェイ側の間で転送される p-identity (pai) 呼び出しオリジネータの情報が表示されます (その逆も可能)。</span><span class="sxs-lookup"><span data-stu-id="a82ca-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="a82ca-197">高速フェールオーバーを有効にするには、[**送信ルーティング フェールオーバー タイマーを有効にする**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="a82ca-198">このトランクに関連付けられているゲートウェイは、発信通話を処理しているという通知を 10 秒以内に送信できます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="a82ca-199">この通知が仲介サーバーによって受信されない場合は、別のトランクへの再ルーティングが行われます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="a82ca-200">ネットワークの待機時間によって応答が遅れる可能性がある場合や、ゲートウェイが 10 秒以内に応答できない場合は、高速フェールオーバーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="a82ca-201">(オプション) トランクの**発信側電話番号変換ルール**を関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="a82ca-202">これらの変換ルールは、発信通話の発信側電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-202">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="a82ca-203">エンタープライズ Voip 展開で利用できるすべての翻訳ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a82ca-204">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="a82ca-205">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="a82ca-206">翻訳ルールの詳細については、「 [Skype For Business Server の翻訳ルール](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-206">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="a82ca-207">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="a82ca-208">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-208">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="a82ca-209">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-209">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="a82ca-210">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-210">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="a82ca-p136">(オプション) トランクの**着信側電話番号変換ルール**を関連付けて構成します。これらの変換ルールは、発信通話の着信側電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a82ca-p136">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="a82ca-213">エンタープライズ Voip 展開で利用できるすべての翻訳ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-213">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a82ca-214">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-214">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="a82ca-215">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-215">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="a82ca-216">翻訳ルールの詳細については、「 [Skype For Business Server の翻訳ルール](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-216">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="a82ca-217">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-217">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="a82ca-218">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-218">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="a82ca-219">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-219">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="a82ca-220">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-220">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

17. <span data-ttu-id="a82ca-221">トランクの翻訳ルールが正しい順序で配置されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-221">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="a82ca-222">リスト内のルールの位置を変更するには、ルール名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-222">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a82ca-223">Skype for Business Server は、翻訳ルールリストを上から下に移動し、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-223">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="a82ca-224">トランクを構成し、その結果ダイヤルされる番号が複数の変換ルールと一致する可能性がある場合は、制限の厳しいルールを制限の緩いルールよりも上に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-224">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="a82ca-225">たとえば、11桁の番号に一致する翻訳ルールと、+ 1425 で始まる11桁の番号のみを一致する翻訳ルールを含めた場合は、11桁の数字と一致するルールがより制限された順\*\* に並べ替えられていることを確認してください。ルール.</span><span class="sxs-lookup"><span data-stu-id="a82ca-225">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

18. <span data-ttu-id="a82ca-226">トランクの構成が終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-226">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="a82ca-227">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a82ca-227">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a82ca-228">トランクの構成を作成または変更するときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a82ca-228">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="a82ca-229">詳細については、「 [Skype For business の音声ルーティング構成に保留中の変更を発行する](voice-route-config-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ca-229">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

<span data-ttu-id="a82ca-230">トランクを構成した後、展開ドキュメントの「 [Skype For Business Server でのメディアバイパスの展開](deploy-media-bypass.md)」の説明に従って、[グローバルメディアバイパス] オプションを選択して、メディアバイパスの構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="a82ca-230">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Deploy media bypass in Skype for Business Server](deploy-media-bypass.md) in the Deployment documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="a82ca-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="a82ca-231">See also</span></span>

[<span data-ttu-id="a82ca-232">Skype for Business Server でメディアをバイパスせずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="a82ca-232">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="a82ca-233">Skype for Business Server でメディアバイパスを展開する</span><span class="sxs-lookup"><span data-stu-id="a82ca-233">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

[<span data-ttu-id="a82ca-234">翻訳ルールを定義する</span><span class="sxs-lookup"><span data-stu-id="a82ca-234">Defining Translation Rules</span></span>](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[<span data-ttu-id="a82ca-235">メディアバイパスの構成</span><span class="sxs-lookup"><span data-stu-id="a82ca-235">Configure Media Bypass</span></span>](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

