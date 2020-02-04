---
title: 'Lync Server 2013: グローバルメディアバイパスオプション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653c47cd993bac8ada899f62fa3be6700cd34c33
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="21a32-102">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="21a32-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21a32-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="21a32-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21a32-104">このトピックでは、特定のサイトまたはサービスのために、ピア (公衆交換電話網 (PSTN) ゲートウェイ、IP PBX、または、インターネットテレフォニーサービスプロバイダーのセッション境界コントローラー (SBC) に対して、trunks でメディアバイパスを既に構成していることを前提としています。メディアが仲介サーバーをバイパスする必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="21a32-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="21a32-p101">ピアに関連付けられている個々のトランク接続でメディア パイパスを有効にするほか、メディア バイパスをグローバルに有効にする必要もあります。グローバルなメディア バイパス設定では、PSTN への呼び出しで常にメディア バイパスを試行するか、ネットワーク サイトおよびネットワーク地域へのサブネットのマッピングを使用するメディア パイパスを採用するかを指定できます。後者の方法は、もう 1 つの高度な音声機能である通話受付管理での方法と似ています。メディア バイパスと通話受付管理が両方有効な場合は、ネットワーク地域、ネットワーク サイト、および通話受付管理用に指定されるサブネット情報が、メディア バイパスを使用するかどうかを決定する際に自動的に使用されます。つまり、通話受付管理が有効な場合は、PSTN の呼び出しで常にメディア バイパスを試行するよう指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="21a32-p101">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally. Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature. When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass. This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="21a32-109">このトピックでは、Lync Server コントロールパネルと Lync Server 管理シェルを使用して、グローバルメディアのバイパス設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21a32-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="21a32-110">こうした手順を使用してメディア バイパスを構成する場合は、クライアントと仲介サーバー ピア (PSTN ゲートウェイ、IP-PBX、SIP トランキング プロバイダーでの SBC など) の間の接続状態が良好であることが前提です。</span><span class="sxs-lookup"><span data-stu-id="21a32-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="21a32-111">リンクに帯域幅制限があると、メディア バイパスを通話に適用できません。</span><span class="sxs-lookup"><span data-stu-id="21a32-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="21a32-112">メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="21a32-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="21a32-113">マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="21a32-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="21a32-114">メディアのバイパスは、統合された通信のオープンな相互運用性プログラム– Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>の製品とバージョンでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="21a32-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="21a32-115">次の手順: グローバルメディアバイパス設定を選ぶ</span><span class="sxs-lookup"><span data-stu-id="21a32-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="21a32-116">特定のサイトまたはサービスのピアへのトランク接続でメディアバイパスを有効にした後、次のコンテンツを使用します。</span><span class="sxs-lookup"><span data-stu-id="21a32-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="21a32-117">「 [Lync server 2013 でメディアのバイパスを構成する](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)」で説明されているように、常にメディアのバイパスを有効にして、仲介サーバーをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="21a32-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="21a32-118">または、「サイトと地域の情報を[使用するため](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)に、メディアのバイパスを構成する」の説明2013に従って、サイトと地域の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="21a32-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21a32-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="21a32-119">See Also</span></span>


[<span data-ttu-id="21a32-120">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21a32-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="21a32-121">Lync Server 2013 でのネットワーク サイトとサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="21a32-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="21a32-122">Lync Server 2013 メディア バイパスの構成</span><span class="sxs-lookup"><span data-stu-id="21a32-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="21a32-123">Lync Server 2013 のメディア バイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="21a32-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

