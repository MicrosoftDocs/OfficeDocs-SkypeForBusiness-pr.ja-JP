---
title: 'Lync Server 2013: ブランチサイトの SIP トランキング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 161964bc7a183672323ac277eae4f3a7ce0d2b82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="47040-102">Lync Server 2013 でのブランチサイト SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="47040-102">Branch site SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47040-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="47040-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="47040-104">場合によっては、選択したブランチサイトでの分散 SIP トランキングの実装が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="47040-104">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="47040-105">ブランチサイトに SIP トランクが必要かどうかを判断するには、「 [Lync Server 2013 での sip トランキングの実装方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47040-105">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="47040-106">ブランチサイトでの SIP トランクの展開でサポートされるトポロジオプションの詳細については、「 [Lync Server 2013 の「ブランチサイトの復元ソリューション](lync-server-2013-branch-site-resiliency-solutions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47040-106">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="47040-107">ブランチ サイト SIP トランク要件例の分析</span><span class="sxs-lookup"><span data-stu-id="47040-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="47040-108">ブランチサイトの SIP トランクを展開することを決定した場合は、サイト固有のコスト分析を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47040-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="47040-109">たとえば、Redmond、ワシントン、ニューヨークのブランチサイトに中央サイトがあるエンタープライズは、ニューヨークサイトからローカルサービスプロバイダへの SIP トランクを実装するかどうかを判断する分析を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="47040-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="47040-110">ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。</span><span class="sxs-lookup"><span data-stu-id="47040-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="47040-111">中央サイトでブランチサイトの終了を完了しました。</span><span class="sxs-lookup"><span data-stu-id="47040-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="47040-112">たとえば、Redmond の中央サイトは、ニューヨークのブランチサイト用の電話番号をホストできます。</span><span class="sxs-lookup"><span data-stu-id="47040-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="47040-113">分散 SIP トランクを実装するコストがこれらの呼び出しのコストを下回っている場合は、ニューヨークブランチサイトで SIP トランクを実装することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="47040-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="47040-114">その他のブランチ サイト SIP トランク要件</span><span class="sxs-lookup"><span data-stu-id="47040-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="47040-115">ゲートウェイの代わりに SIP トランクを展開する方法の選択は、各オプションの公衆交換電話網 (PSTN) 長距離通話料金の違いに基づいています。</span><span class="sxs-lookup"><span data-stu-id="47040-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="47040-116">ブランチサイトの SIP トランクを展開する場合は、復元および帯域幅の要件も決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47040-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="47040-117">ブランチサイトと中央サイトの間のリンクが復元性があり、十分な帯域幅がある場合は、SIP トランクまたはゲートウェイを展開できます。</span><span class="sxs-lookup"><span data-stu-id="47040-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="47040-118">ブランチサイトで存続可能ブランチアプライアンスを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="47040-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="47040-119">ブランチサイトと中央サイトの間のリンクが復元できない場合は、存続可能 Branch Appliance を展開するか、ゲートウェイまたは SIP トランクを使用してブランチサイトに存続可能ブランチサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="47040-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

