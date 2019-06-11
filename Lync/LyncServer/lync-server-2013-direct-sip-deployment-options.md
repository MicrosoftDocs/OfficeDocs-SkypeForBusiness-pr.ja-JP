---
title: 'Lync Server 2013: 直接 SIP 展開のオプション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="edc5f-102">Lync Server 2013 の直接 SIP 展開のオプション</span><span class="sxs-lookup"><span data-stu-id="edc5f-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edc5f-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="edc5f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="edc5f-104">このトピックでは、直接 SIP 接続を展開するためのトポロジの例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="edc5f-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="edc5f-105">Lync Server スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="edc5f-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="edc5f-106">このセクションで説明されている展開のいずれかを使用している組織では、Lync Server 2013 を1つまたは複数の組織の唯一のテレフォニーソリューションとして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="edc5f-107">このセクションでは、次の展開について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="edc5f-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="edc5f-108">**段階的展開:** このオプションは、既存の構内交換会社 (PBX) インフラストラクチャを使用していて、組織内の小規模なグループまたはチームにエンタープライズボイスを段階的に導入することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="edc5f-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="edc5f-109">**Lync Server の VoIP のみの展開:** このオプションは、従来のテレフォニーインフラストラクチャを使用していないサイトでのエンタープライズ voip の展開を検討していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="edc5f-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="edc5f-110">段階的な展開</span><span class="sxs-lookup"><span data-stu-id="edc5f-110">Incremental Deployment</span></span>

<span data-ttu-id="edc5f-111">段階的展開では、Lync Server 2013 は個々のチームまたは部署向けの唯一のテレフォニーソリューションであり、組織内の他のユーザーは引き続き PBX を使用しています。</span><span class="sxs-lookup"><span data-stu-id="edc5f-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="edc5f-112">この段階的展開戦略では、管理されたパイロットプログラムを通じて、企業に IP テレフォニーを導入する方法が1つあります。</span><span class="sxs-lookup"><span data-stu-id="edc5f-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="edc5f-113">Microsoft ユニファイドコミュニケーションで利用するのに最適な通信が必要なワークグループは、他のユーザーが既存の PBX に移動しても、エンタープライズ Voip に移行されます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="edc5f-114">必要に応じて、追加のワークグループをエンタープライズ Voip に移行できます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="edc5f-115">通信要件が共通であり、一元管理に対応しているユーザーグループが明確に定義されている場合は、増分オプションをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="edc5f-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="edc5f-116">このオプションは、地理的な広い範囲を超えるチームまたは部門を使用していて、長距離通話料金の節約が重要である場合にも有効です。</span><span class="sxs-lookup"><span data-stu-id="edc5f-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="edc5f-117">実際には、このオプションは、世界中でメンバーが散在している可能性のある仮想チームを作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="edc5f-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="edc5f-118">このようなチームを作成、変更、または解除して、変化するビジネス要件に迅速に対応することができます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="edc5f-119">次の図は、PBX でのエンタープライズボイスの展開のための一般的なトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="edc5f-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="edc5f-120">これは、段階的展開に推奨されるトポロジです。</span><span class="sxs-lookup"><span data-stu-id="edc5f-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="edc5f-121">**段階的な展開オプション**</span><span class="sxs-lookup"><span data-stu-id="edc5f-121">**Incremental deployment option**</span></span>

<span data-ttu-id="edc5f-122">![部門の移行オプションの図](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門の移行オプションの図")</span><span class="sxs-lookup"><span data-stu-id="edc5f-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="edc5f-123">Lync Server の展開を認定された直接 SIP パートナーに接続している場合は、仲介サーバーと PBX の間の公衆交換電話網 (PSTN) ゲートウェイは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="edc5f-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="edc5f-124">認定された直接 SIP パートナーのリストについては、Microsoft ユニファイドコミュニケーションの<A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>オープンな相互運用性プログラムの web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edc5f-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="edc5f-125">この図に示されているメディアパスでは、メディアのバイパスが有効になっています (推奨される構成)。</span><span class="sxs-lookup"><span data-stu-id="edc5f-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="edc5f-126">メディアのバイパスを無効にすると、メディアパスは仲介サーバー経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="edc5f-127">このトポロジでは、選択した部署またはワークグループがエンタープライズ Voip に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="edc5f-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="edc5f-128">PSTN ゲートウェイは、Voice over Internet Protocol (VoIP) 対応ワークグループを PBX にリンクします。</span><span class="sxs-lookup"><span data-stu-id="edc5f-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="edc5f-129">リモートワーカーなどのエンタープライズ Voip を有効にしているユーザーは、IP ネットワーク経由で通信できます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="edc5f-130">エンタープライズボイスユーザーから PSTN への通話、およびエンタープライズ Voip を有効にしていない同僚が、適切な PSTN ゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="edc5f-131">PBX システムまたは PSTN 上の発信者からの通話は PSTN ゲートウェイにルーティングされます。これにより、ルーティング用の Lync Server への通話が転送されます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="edc5f-132">相互運用性を確保するために、エンタープライズボイスを既存の PBX インフラストラクチャに接続するための推奨される構成が2つあります。 pbx でのエンタープライズ voip と、pbx の前のエンタープライズボイス。</span><span class="sxs-lookup"><span data-stu-id="edc5f-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="edc5f-133">PBX 経由のエンタープライズ Voip</span><span class="sxs-lookup"><span data-stu-id="edc5f-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="edc5f-134">エンタープライズ Voip が PBX を介して展開されると、PSTN からのすべての通話が PBX に到着し、PSTN ゲートウェイへのエンタープライズボイスユーザーへの通話のルーティング、および pbx ユーザーへの着信が pbx に転送されます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="edc5f-135">PBX の前のエンタープライズボイス</span><span class="sxs-lookup"><span data-stu-id="edc5f-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="edc5f-136">エンタープライズボイスが PBX の前に展開されている場合、すべての通話が PSTN ゲートウェイに到着します。これにより、エンタープライズボイスユーザーの通話が Lync Server に転送され、pbx ユーザーが pbx に発信します。</span><span class="sxs-lookup"><span data-stu-id="edc5f-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="edc5f-137">エンタープライズボイスと PBX ユーザーの両方からの PSTN への通話は、IP ネットワーク経由で、最もコスト効率の高い PSTN ゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="edc5f-138">次の表は、この構成の長所と短所を示しています。</span><span class="sxs-lookup"><span data-stu-id="edc5f-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="edc5f-139">PBX の前にエンタープライズボイスを展開する場合の長所と短所</span><span class="sxs-lookup"><span data-stu-id="edc5f-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edc5f-140">利点</span><span class="sxs-lookup"><span data-stu-id="edc5f-140">Advantages</span></span></th>
<th><span data-ttu-id="edc5f-141">不都合</span><span class="sxs-lookup"><span data-stu-id="edc5f-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edc5f-142">PBX では、エンタープライズ Voip を有効にしていないユーザーの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="edc5f-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="edc5f-143">既存のゲートウェイは、必要な機能や容量をサポートしていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="edc5f-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edc5f-144">PBX は、以前のすべてのデバイスを処理します。</span><span class="sxs-lookup"><span data-stu-id="edc5f-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="edc5f-145">PBX と仲介サーバーのゲートウェイからのトランクが必要です。</span><span class="sxs-lookup"><span data-stu-id="edc5f-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="edc5f-146">サービスプロバイダからさらに trunks が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="edc5f-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edc5f-147">エンタープライズボイスのユーザーは、同じ電話番号をそのまま使うことができます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="edc5f-148">Lync Server の VoIP のみの展開</span><span class="sxs-lookup"><span data-stu-id="edc5f-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="edc5f-149">エンタープライズ Voip では、新しいビジネスと、既存のビジネス向けの新しい office サイトも提供され、PBX の統合または大量の展開とメンテナンスを気にせずに、完全な機能を備えた VoIP ソリューションを導入する機会があります。IP PBX インフラストラクチャのコスト。</span><span class="sxs-lookup"><span data-stu-id="edc5f-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="edc5f-150">このソリューションは、オンサイトとリモートの両方のワーカーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="edc5f-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="edc5f-151">この展開では、すべての通話が IP ネットワーク経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="edc5f-152">PSTN への通話は、適切な PSTN ゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="edc5f-153">Lync 2013 または Lync Phone Edition は、softphone として機能します。</span><span class="sxs-lookup"><span data-stu-id="edc5f-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="edc5f-154">リモート通話コントロールは、ユーザーが制御できる PBX 電話がないため、不要になります。</span><span class="sxs-lookup"><span data-stu-id="edc5f-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="edc5f-155">ボイスメールと自動応答サービスは、オプションの展開である Exchange ユニファイドメッセージング (UM) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="edc5f-156">VoIP のみの展開では、Lync Server 2013 をサポートするために必要なネットワークインフラストラクチャに加えて、小型の認定されたゲートウェイを使用して、fax 機器とアナログデバイスをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="edc5f-157">次の図は、VoIP のみの展開の一般的なトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="edc5f-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="edc5f-158">**VoIP のみの展開オプション**</span><span class="sxs-lookup"><span data-stu-id="edc5f-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="edc5f-159">![Greenfidle 展開オプション](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 展開オプション")</span><span class="sxs-lookup"><span data-stu-id="edc5f-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="edc5f-160">この図に示されているメディアパスでは、メディアのバイパスが有効になっています (推奨される構成)。</span><span class="sxs-lookup"><span data-stu-id="edc5f-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="edc5f-161">メディアのバイパスを無効にすると、メディアパスは仲介サーバー経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="edc5f-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

