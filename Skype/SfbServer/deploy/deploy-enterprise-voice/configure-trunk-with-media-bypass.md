---
title: ビジネス サーバーの Skype でのメディア バイ パスを使用してトランクを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: '概要: は、Skype のビジネス サーバー対応メディア バイ パスを持つトランクを構成します。 これは、オプションを選択する、SIP トランク プロバイダーでサポートされていると仮定した、仲介サーバーの数を最小化することができます。'
ms.openlocfilehash: 8fc6ed21af9bb78240c338e25538cfb0519d49d5
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890586"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="15ce8-104">ビジネス サーバーの Skype でのメディア バイ パスを使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-104">Configure a trunk with media bypass in Skype for Business Server</span></span>

<span data-ttu-id="15ce8-105">**の概要:** Skype 対応でビジネスのサーバーのメディア バイ パスには、トランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-105">**Summary:** Configure a trunk with media bypass enabled for Skype for Business Server.</span></span> <span data-ttu-id="15ce8-106">これは、オプションを選択する、SIP トランク プロバイダーでサポートされていると仮定した、仲介サーバーの数を最小化することができます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-106">This will let you minimize the number of Mediation Servers, presuming your SIP trunk provider supports it.</span></span>

<span data-ttu-id="15ce8-107">メディア バイパスを有効にしてトランクを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-107">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="15ce8-108">メディア バイ パスが無効になっていると、トランクを構成するには、 [Skype のビジネス サーバーで使用しないメディアのないトランクの構成](configure-trunk-without-media-bypass.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-108">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md).</span></span>

<span data-ttu-id="15ce8-109">メディア バイ パスは、展開する仲介サーバーの数を最小限に抑えたい場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="15ce8-109">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="15ce8-110">詳細については、[ビジネスの Skype で使用しないメディアの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-110">For more information, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span></span>

<span data-ttu-id="15ce8-111">メディアのバイパスを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="15ce8-112">ただし、SIP トランクのメディア バイ パスを有効にする前に、修飾された SIP トランク プロバイダーがメディア バイ パスがサポートされていて、シナリオを正常に有効にするための要件に対応することが確認します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="15ce8-113">具体的には、プロバイダーでは、組織の内部ネットワーク上のサーバーの IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="15ce8-113">Specifically, the provider must have the IP addresses of servers in your organization's internal network.</span></span>

> [!NOTE]
> <span data-ttu-id="15ce8-114">メディア バイパスは、すべての公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、およびセッション ボーダー コントローラー (SBC) と相互運用できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="15ce8-114">Media bypass will not interoperate with every Public Switched Telephone Network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="15ce8-115">マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="15ce8-115">Microsoft has tested a set of PSTN gateways and SBCs with certified partners.</span></span> <span data-ttu-id="15ce8-116">メディアのバイパスが製品および[Skype のビジネス サーバーのテレフォニー インフラストラクチャ](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)のページに記載されているバージョンでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="15ce8-116">Media bypass is supported only with products and versions that are listed on the [Telephony Infrastructure for Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span>

<span data-ttu-id="15ce8-p107">以下で説明するトランク構成では、そのトランク構成が割り当てられるトランクに適用される一連のパラメーターがグループ化されています。トランク構成のスコープは、グローバル (サイトまたはプールの構成を持たないすべてのトランクに適用されます)、サイト、またはプールにすることができます。プール レベルのトランク構成は、トランク構成のスコープを 1 つのトランクにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-p107">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="15ce8-120">メディア バイパスを有効にしてトランクを構成するには</span><span class="sxs-lookup"><span data-stu-id="15ce8-120">To configure a trunk with media bypass</span></span>

1. <span data-ttu-id="15ce8-121">ビジネス サーバーのコントロール パネルの Skype を開く</span><span class="sxs-lookup"><span data-stu-id="15ce8-121">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="15ce8-122">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-122">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="15ce8-123">[**トランク構成**] ページで、次のいずれかの方法を使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-123">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="15ce8-124">既存のトランク (たとえば、[**グローバル**] トランク) をダブルクリックして [**トランク構成の編集**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-124">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="15ce8-125">[**新規**] をクリックし、新しいトランク構成のスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-125">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="15ce8-p108">[**サイト トランク**]: [**サイトの選択**] で、このトランク構成のサイトを選択し、[**OK**] をクリックします。サイトに対してトランク構成が既に作成されている場合、[**サイトの選択**] にはサイトは表示されませんので注意してください。このトランク構成はサイトのすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-p108">**Site trunk**: Choose the site for this trunk configuration from **Select a Site**, and then click **OK**. Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**. This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="15ce8-129">[**プール トランク**]: このトランク構成を適用するトランクの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-129">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="15ce8-130">このトランクには、ルートのトランクまたはトポロジ ビルダーで定義されている任意の追加トランクを指定できます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-130">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="15ce8-131">[  **サービスの選択**  ] で、[  **OK**  ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-131">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="15ce8-132">トランク構成が既に作成されているトランクは [  **サービスの選択**  ] に表示されません。</span><span class="sxs-lookup"><span data-stu-id="15ce8-132">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="15ce8-133">トランク構成のスコープは、選択後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="15ce8-133">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="15ce8-134">> **[名前**] フィールドでは、トランクの構成の関連するサイトまたはサービスの名前があらかじめ設定されて、変更できません。</span><span class="sxs-lookup"><span data-stu-id="15ce8-134">> The **Name** field is prepopulated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="15ce8-p111">[**サポートされる最大早期ダイアログ数**] に値を指定します。これは公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラー (SBC) が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。既定値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="15ce8-p111">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15ce8-138">この値を変更する前に、サービス プロバイダーまたは機器の製造メーカーに、システムの機能の詳細について問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-138">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

5. <span data-ttu-id="15ce8-139">次のいずれかの [**暗号化サポート レベル**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-139">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="15ce8-140">[**必須**]: 仲介サーバーとゲートウェイまたは構内交換機 (PBX) 間のトラフィック保護に役立てるために、セキュア リアルタイム転送プロトコル (SRTP) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ce8-140">**Required**: Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>

   - <span data-ttu-id="15ce8-141">[**省略可能**]: サービス プロバイダーまたは機器の製造メーカーがサポートしている場合、SRTP 暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-141">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="15ce8-142">[**サポート対象外**]: サービス プロバイダーまたは機器の製造メーカーが SRTP 暗号化をサポートしていないため、SRTP 暗号化は使用されません。</span><span class="sxs-lookup"><span data-stu-id="15ce8-142">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6. <span data-ttu-id="15ce8-143">トランク ピアによる処理で、メディアが仲介サーバーをバイパスするようにする場合は、[**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-143">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="15ce8-144">メディア バイパスが正常に機能するには、PSTN ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラーが一定の機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ce8-144">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="15ce8-145">詳細については、[ビジネスの Skype で使用しないメディアの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-145">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

7. <span data-ttu-id="15ce8-p113">既知のメディア終端ポイント (たとえば、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイ) がある場合は、[**集中メディア処理**] チェック ボックスをオンにします。トランクに既知のメディア終端ポイントがない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-p113">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8. <span data-ttu-id="15ce8-148">トランク ピアでは、仲介サーバーから参照する SIP 要求の受信をサポートする場合は、**ゲートウェイを参照してくださいの送信を有効にする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-148">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15ce8-149">[**メディア バイパスを有効にする**] オプションが選択されている場合にこのオプションを無効にするには、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="15ce8-149">If you disable this option while the **Enable media bypass** option is selected, additional settings are required.</span></span> <span data-ttu-id="15ce8-150">トランク ピアがサポートしていない場合は、仲介サーバーおよびメディア バイ パスから参照する SIP 要求の受信が有効になっているの適切な条件をサポートするために、アクティブな呼び出しの RTCP を無効にする**セット CsTrunkConfiguration**コマンドレットを実行することもする必要があります。メディアをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-150">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the **Set-CsTrunkConfiguration** cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="15ce8-151">ゲートウェイが SIP REFER 要求をサポートしていない場合に転送通話をメディア バイパスするには、[**サードパーティ通話コントロールを使用する参照を有効にする**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-151">Alternatively, you can select **Enable refer using third-party-call control** if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

9. <span data-ttu-id="15ce8-152">(オプション) トランク間ルーティングを有効にするには、このトランク構成に PSTN 使用法レコードを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-152">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="15ce8-153">トランク ビジネス サーバーのエンドポイントは、Skype にも元がないことをすべての着信呼び出しをこのトランク構成に関連付けられている PSTN 使用法が適用されます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-153">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="15ce8-154">トランク構成に関連付けられた PSTN 使用法レコードを管理するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-154">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="15ce8-155">エンタープライズ VoIP 展開で利用可能なすべての PSTN 使用法レコードの一覧から 1 つまたは複数のレコードを選択するに [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-155">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="15ce8-156">このトランク構成に関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-156">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="15ce8-157">PSTN 使用法レコードをこのトランク構成から削除するには、レコードを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-157">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="15ce8-158">新しい PSTN 使用法レコードを定義してこのトランク構成に関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-158">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

    <span data-ttu-id="15ce8-159">a.</span><span class="sxs-lookup"><span data-stu-id="15ce8-159">a.</span></span> <span data-ttu-id="15ce8-160">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-160">Click **New**.</span></span>

    <span data-ttu-id="15ce8-161">b.</span><span class="sxs-lookup"><span data-stu-id="15ce8-161">b.</span></span> <span data-ttu-id="15ce8-162">[**名前**] フィールドに、レコードを説明する一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-162">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15ce8-p119">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"**名前**" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="15ce8-p119">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

    <span data-ttu-id="15ce8-165">c.</span><span class="sxs-lookup"><span data-stu-id="15ce8-165">c.</span></span> <span data-ttu-id="15ce8-166">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="15ce8-166">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

    - <span data-ttu-id="15ce8-167">エンタープライズ VoIP の展開で使用可能なすべてのルートの一覧から 1 つまたは複数のルートを選択するに [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-167">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="15ce8-168">この PSTN 使用法レコードに関連付けるルートを選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-168">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

    - <span data-ttu-id="15ce8-169">PSTN 使用法レコードからルートを削除するには、ルートを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-169">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="15ce8-170">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-170">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="15ce8-171">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="15ce8-171">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

    - <span data-ttu-id="15ce8-172">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択して [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-172">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

    <span data-ttu-id="15ce8-173">d.</span><span class="sxs-lookup"><span data-stu-id="15ce8-173">d.</span></span> <span data-ttu-id="15ce8-174">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-174">Click **OK**.</span></span>

    - <span data-ttu-id="15ce8-175">このトランク構成に既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-175">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

      <span data-ttu-id="15ce8-176">a.</span><span class="sxs-lookup"><span data-stu-id="15ce8-176">a.</span></span> <span data-ttu-id="15ce8-177">編集する PSTN 使用法レコードを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-177">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

      <span data-ttu-id="15ce8-178">b.</span><span class="sxs-lookup"><span data-stu-id="15ce8-178">b.</span></span> <span data-ttu-id="15ce8-179">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="15ce8-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="15ce8-180">エンタープライズ VoIP の展開で使用可能なすべてのルートの一覧から 1 つまたは複数のルートを選択するに [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="15ce8-181">この PSTN 使用法レコードに関連付けるルートを選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

   - <span data-ttu-id="15ce8-182">PSTN 使用法レコードからルートを削除するには、ルートを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

   - <span data-ttu-id="15ce8-183">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="15ce8-184">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="15ce8-184">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="15ce8-185">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択して [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

    <span data-ttu-id="15ce8-186">c.</span><span class="sxs-lookup"><span data-stu-id="15ce8-186">c.</span></span> <span data-ttu-id="15ce8-187">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-187">Click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="15ce8-188">仲介サーバーのピアを構成するトランクに関連付けられている PSTN 使用法レコードに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ce8-188">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="15ce8-189">仲介サーバーのピアが PSTN ゲートウェイまたはセッション ボーダー コント ローラー (SBC) の場合は、トランクの構成が PSTN のコピー先またはその他のダウン ストリーム システムへのルートは、Skype で接続されている PSTN 使用法レコードに関連付けられているではないことは強くお勧めビジネス サーバーです。</span><span class="sxs-lookup"><span data-stu-id="15ce8-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

10. <span data-ttu-id="15ce8-190">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="15ce8-191">リスト内のレコードの位置を変更するには、PSTN 使用法レコードを選択しをクリックしてまたは下向き矢印を。</span><span class="sxs-lookup"><span data-stu-id="15ce8-191">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="15ce8-192">トランク構成内の一覧における PSTN 使用法レコードの順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="15ce8-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="15ce8-193">ビジネス サーバーの Skype では、上から下にリストを走査します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-193">Skype for Business Server traverses the list from top to down.</span></span>

11. <span data-ttu-id="15ce8-194">ネットワーク アドレス変換 (NAT) またはファイアウォールとラッチをサポートしている SBC の背後にあるクライアントに対してバイパス メディアを有効にするには、[**RTP ラッチを有効にする**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ce8-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="15ce8-195">**前方の呼び出し履歴を有効にするに**は、仲介サーバーのゲートウェイ ピアへの呼び出し履歴情報の送信を有効にする選択してください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="15ce8-196">P アサートされた Id (PAI) 呼び出し元の情報を仲介サーバー側とゲートウェイ側の間で転送を有効にするのには**P アサートされた Id のデータの転送を有効にする**を選択する必要があります (その逆) と表示します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="15ce8-197">高速フェールオーバーを有効にするには、[**送信ルーティング フェールオーバー タイマーを有効にする**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ce8-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="15ce8-198">このトランクに関連付けられているゲートウェイは、発信通話を処理しているという通知を 10 秒以内に送信できます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="15ce8-199">仲介サーバーによってこの通知が受信されない場合は、別のトランクへの再ルーティングが発生します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="15ce8-200">ネットワークの待機時間によって応答が遅れる可能性がある場合や、ゲートウェイが 10 秒以内に応答できない場合は、高速フェールオーバーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ce8-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="15ce8-p133">(オプション) トランクの**発信側電話番号変換ルール**を関連付けて構成します。これらの変換ルールは、発信通話の発信側電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-p133">(Optional) Associate and configure **calling number translation rules** for the trunk. These translation rules apply to the calling number for outbound calls</span></span>

   - <span data-ttu-id="15ce8-203">エンタープライズ VoIP 展開で利用可能なすべての変換ルールの一覧から 1 つまたは複数のルールを選択するのには [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="15ce8-204">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="15ce8-205">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="15ce8-206">変換規則についての詳細は、 [Skype のビジネス サーバーの変換規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-206">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

   - <span data-ttu-id="15ce8-207">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

   - <span data-ttu-id="15ce8-208">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-208">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="15ce8-209">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-209">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="15ce8-210">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-210">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="15ce8-p136">(オプション) トランクの**着信側電話番号変換ルール**を関連付けて構成します。これらの変換ルールは、発信通話の着信側電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="15ce8-p136">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

   - <span data-ttu-id="15ce8-213">エンタープライズ VoIP 展開で利用可能なすべての変換ルールの一覧から 1 つまたは複数のルールを選択するのには [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-213">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="15ce8-214">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-214">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="15ce8-215">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-215">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="15ce8-216">変換規則についての詳細は、 [Skype のビジネス サーバーの変換規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-216">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

   - <span data-ttu-id="15ce8-217">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-217">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

   - <span data-ttu-id="15ce8-218">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-218">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

   - <span data-ttu-id="15ce8-219">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-219">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="15ce8-220">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-220">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

17. <span data-ttu-id="15ce8-221">トランクの変換ルールが正しい順序で配置されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-221">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="15ce8-222">位置を変更するルールの一覧で、ルールの名前を強調表示しをクリックして上下矢印。</span><span class="sxs-lookup"><span data-stu-id="15ce8-222">To change a rule's position in the list, highlight the rule name and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="15ce8-223">Skype ビジネス サーバーのでは、ダウン上から変換ルールの一覧を走査し、ダイヤルした番号と一致する最初の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-223">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="15ce8-224">トランクを構成し、その結果ダイヤルされる番号が複数の変換ルールと一致する可能性がある場合は、制限の厳しいルールを制限の緩いルールよりも上に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-224">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="15ce8-225">11 桁の番号と一致する変換ルールと +1425 で始まる 11 桁の数字のみに一致する変換ルールを含める場合は、11 桁の番号と一致する規則が並べ替えられた*下*より制限の厳しいであることを確認など規則です。</span><span class="sxs-lookup"><span data-stu-id="15ce8-225">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

18. <span data-ttu-id="15ce8-226">トランクの構成が終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-226">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="15ce8-227">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15ce8-227">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="15ce8-228">トランクの構成を作成または変更するときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ce8-228">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="15ce8-229">詳細については、操作マニュアルの[発行保留中のビジネス用の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15ce8-229">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

<span data-ttu-id="15ce8-230">トランクを構成した後は、メディアの設定を続けるグローバル ・ メディアとの間を選択することによってバイパスに従って[展開メディアを Skype ビジネス サーバー用のバイパス](deploy-media-bypass.md)の展開に関するドキュメントのオプションを使用しません。</span><span class="sxs-lookup"><span data-stu-id="15ce8-230">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Deploy media bypass in Skype for Business Server](deploy-media-bypass.md) in the Deployment documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="15ce8-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="15ce8-231">See also</span></span>

[<span data-ttu-id="15ce8-232">メディアが Skype のビジネス サーバーのバイパスなしトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-232">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="15ce8-233">ビジネス サーバーの Skype でのメディア バイ パスを展開します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-233">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

[<span data-ttu-id="15ce8-234">変換ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-234">Defining Translation Rules</span></span>](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[<span data-ttu-id="15ce8-235">メディア バイ パスを構成します。</span><span class="sxs-lookup"><span data-stu-id="15ce8-235">Configure Media Bypass</span></span>](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

