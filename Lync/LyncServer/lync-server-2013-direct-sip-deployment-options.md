---
title: 'Lync Server 2013: 直接 SIP 展開のオプション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521e1665361e15fffdf1e058731d04bc2eb9aa4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="01235-102">Lync Server 2013 の直接 SIP 展開のオプション</span><span class="sxs-lookup"><span data-stu-id="01235-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01235-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="01235-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="01235-104">ここでは、直接 SIP 接続を展開するトポロジの例について説明します。</span><span class="sxs-lookup"><span data-stu-id="01235-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="01235-105">Lync Server スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="01235-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="01235-106">このセクションに記載されているいずれかの展開を組織が使用している場合は、一部またはすべての組織の単独テレフォニーソリューションとして Lync Server 2013 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="01235-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="01235-107">このセクションでは、次の展開について詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="01235-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="01235-108">**増分展開:** このオプションでは、既存の構内交換業者 (PBX) インフラストラクチャがあり、組織内の小規模なグループまたはチームにエンタープライズ Voip を段階的に導入することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="01235-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="01235-109">**Lync Server VoIP のみの展開:** このオプションは、従来のテレフォニーインフラストラクチャを持たないサイトでエンタープライズ voip を展開することを検討していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="01235-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="01235-110">増分展開</span><span class="sxs-lookup"><span data-stu-id="01235-110">Incremental Deployment</span></span>

<span data-ttu-id="01235-111">増分展開では、Lync Server 2013 は個別のチームまたは部署の単独テレフォニーソリューションですが、組織内の残りのユーザーは引き続き PBX を使用します。</span><span class="sxs-lookup"><span data-stu-id="01235-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="01235-112">この段階的な展開戦略では、管理されたパイロットプログラムを使用して、企業に IP テレフォニーを導入することができます。</span><span class="sxs-lookup"><span data-stu-id="01235-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="01235-113">Microsoft ユニファイドコミュニケーションが最適に提供する必要があるワークグループはエンタープライズ Voip に移行されますが、他のユーザーは既存の PBX に保持されます。</span><span class="sxs-lookup"><span data-stu-id="01235-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="01235-114">必要に応じて、他のワークグループをエンタープライズ Voip に移行できます。</span><span class="sxs-lookup"><span data-stu-id="01235-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="01235-115">[増分] オプションは、共通の通信要件を持つユーザーグループを明確に定義していて、集中管理を行う場合にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01235-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="01235-116">このオプションは、地理的な地域に散らばっている teams または部署がある場合にも効果的です。長距離の料金を節約することが重要です。</span><span class="sxs-lookup"><span data-stu-id="01235-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="01235-117">実際、このオプションは、メンバーが世界中に散在している可能性がある仮想チームを作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01235-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="01235-118">変化するビジネス要件に迅速に対応するために、このようなチームを作成、変更、または消滅させることができます。</span><span class="sxs-lookup"><span data-stu-id="01235-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="01235-119">次の図は、PBX の背後にエンタープライズ Voip を展開するための一般的なトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="01235-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="01235-120">これは、増分展開で推奨されるトポロジです。</span><span class="sxs-lookup"><span data-stu-id="01235-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="01235-121">**増分展開オプション**</span><span class="sxs-lookup"><span data-stu-id="01235-121">**Incremental deployment option**</span></span>

<span data-ttu-id="01235-122">![部門別移行オプションの図](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門別移行オプションの図")</span><span class="sxs-lookup"><span data-stu-id="01235-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01235-123">Lync Server の展開を認定された直接 SIP パートナーに接続している場合は、仲介サーバーと PBX との間の公衆交換電話網 (PSTN) ゲートウェイは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="01235-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="01235-124">認定された直接 SIP パートナーの一覧については、「Microsoft 統合コミュニケーション」 <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>() を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01235-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="01235-125">この図に示されているメディアパスは、メディアバイパスが有効になっています (推奨構成)。</span><span class="sxs-lookup"><span data-stu-id="01235-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="01235-126">メディアバイパスを無効にすることを選択すると、メディアパスが仲介サーバーを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="01235-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="01235-127">このトポロジでは、選択した部門またはワークグループがエンタープライズ Voip に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="01235-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="01235-128">PSTN ゲートウェイは、VoIP (Voice over Internet Protocol) 対応ワークグループを PBX にリンクします。</span><span class="sxs-lookup"><span data-stu-id="01235-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="01235-129">エンタープライズ Voip が有効になっているユーザー (リモートワーカーを含む) は、IP ネットワークを介して通信します。</span><span class="sxs-lookup"><span data-stu-id="01235-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="01235-130">エンタープライズ voip ユーザーから PSTN への通話、およびエンタープライズ Voip が有効になっていない同僚は、適切な PSTN ゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="01235-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="01235-131">PBX システム上にある同僚または PSTN 上の発信者からの通話は、PSTN ゲートウェイにルーティングされ、通話をルーティングのために Lync Server に転送します。</span><span class="sxs-lookup"><span data-stu-id="01235-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="01235-132">エンタープライズ Voip を既存の PBX インフラストラクチャに接続する場合は、次の2つの構成が推奨されます。これは、pbx の背後にある PBX とエンタープライズ Voip の背後にあるエンタープライズ voip です。</span><span class="sxs-lookup"><span data-stu-id="01235-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="01235-133">PBX の背後のエンタープライズ Voip</span><span class="sxs-lookup"><span data-stu-id="01235-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="01235-134">エンタープライズ Voip が PBX の背後に展開されると、PSTN からのすべての通話が PBX で到着し、PSTN ゲートウェイにエンタープライズ Voip ユーザーへの通話をルーティングし、pbx ユーザーを pbx に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="01235-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="01235-135">PBX の前面のエンタープライズ Voip</span><span class="sxs-lookup"><span data-stu-id="01235-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="01235-136">エンタープライズ Voip が PBX の前に展開されている場合、すべての通話は PSTN ゲートウェイに到着します。これにより、エンタープライズ Voip ユーザーの通話が Lync Server にルーティングされ、pbx ユーザーが PBX に電話をかけられます。</span><span class="sxs-lookup"><span data-stu-id="01235-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="01235-137">エンタープライズ Voip および PBX ユーザーの両方の PSTN への通話は、IP ネットワークを介して、最も費用効率のよい PSTN ゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="01235-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="01235-138">次の表に、この構成の長所と短所を示します。</span><span class="sxs-lookup"><span data-stu-id="01235-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="01235-139">エンタープライズ Voip を PBX の前面に展開する場合の利点と欠点</span><span class="sxs-lookup"><span data-stu-id="01235-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01235-140">メリット</span><span class="sxs-lookup"><span data-stu-id="01235-140">Advantages</span></span></th>
<th><span data-ttu-id="01235-141">デメリット</span><span class="sxs-lookup"><span data-stu-id="01235-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01235-142">PBX では、エンタープライズ Voip が有効になっていないユーザーも引き続き提供されます。</span><span class="sxs-lookup"><span data-stu-id="01235-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="01235-143">既存のゲートウェイでは、必要な機能や容量がサポートされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="01235-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01235-144">PBX は以前のすべてのデバイスを処理します。</span><span class="sxs-lookup"><span data-stu-id="01235-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="01235-145">PBX から仲介サーバーへのゲートウェイからのトランクが必要です。</span><span class="sxs-lookup"><span data-stu-id="01235-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="01235-146">サービスプロバイダーからさらにトランクが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="01235-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01235-147">エンタープライズ Voip ユーザーは同じ電話番号を保持します。</span><span class="sxs-lookup"><span data-stu-id="01235-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="01235-148">Lync Server VoIP のみの展開</span><span class="sxs-lookup"><span data-stu-id="01235-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="01235-149">エンタープライズ Voip では、新しいビジネスと既存のビジネス向けの新しい office サイトも提供しており、PBX の統合または大量の展開と保守を気にせずに、完全な機能を備えた VoIP ソリューションを実装する機会があります。ip-pbx インフラストラクチャのコスト。</span><span class="sxs-lookup"><span data-stu-id="01235-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="01235-150">このソリューションは、オンサイトワーカーとリモートワーカーの両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="01235-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="01235-151">この展開では、すべての呼び出しが IP ネットワークを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="01235-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="01235-152">PSTN への通話は、適切な PSTN ゲートウェイにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="01235-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="01235-153">Lync 2013 または Lync Phone Edition は、softphone として機能します。</span><span class="sxs-lookup"><span data-stu-id="01235-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="01235-154">ユーザーが管理する PBX 電話がないため、リモート通話コントロールは使用できず、不要です。</span><span class="sxs-lookup"><span data-stu-id="01235-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="01235-155">ボイスメールおよび自動応答サービスは、「Exchange ユニファイドメッセージング (UM) のオプションの展開によって利用できます。</span><span class="sxs-lookup"><span data-stu-id="01235-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01235-156">Lync Server 2013 をサポートするために必要なネットワークインフラストラクチャに加えて、VoIP のみの展開では、fax マシンとアナログデバイスをサポートするために、小規模の認定されたゲートウェイを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01235-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="01235-157">次の図は、VoIP のみの展開の一般的なトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="01235-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="01235-158">**VoIP のみの展開オプション**</span><span class="sxs-lookup"><span data-stu-id="01235-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="01235-159">![Greenfield の展開オプション](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfield の展開オプション")</span><span class="sxs-lookup"><span data-stu-id="01235-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01235-160">この図に示されているメディアパスは、メディアバイパスが有効になっています (推奨構成)。</span><span class="sxs-lookup"><span data-stu-id="01235-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="01235-161">メディアバイパスを無効にすることを選択すると、メディアパスが仲介サーバーを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="01235-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

