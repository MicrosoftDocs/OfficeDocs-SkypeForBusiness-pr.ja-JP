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
ms.openlocfilehash: 5b6a5f0d7a6a89b30b0ef08f8631b06fb9047616
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="60fb2-102">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="60fb2-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60fb2-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="60fb2-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60fb2-104">このトピックでは、特定のサイトまたはサービスについて、ピア (公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはインターネットテレフォニーサービスプロバイダーのセッションボーダーコントローラー (SBC) のいずれかのトランクに対してメディアバイパスが既に構成されていることを前提としています。メディアが仲介サーバーをバイパスする必要がある。</span><span class="sxs-lookup"><span data-stu-id="60fb2-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="60fb2-105">ピアに関連付けられた個々のトランク接続に対してメディアバイパスを有効にすることに加えて、メディアバイパスをグローバルに有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="60fb2-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="60fb2-106">グローバルメディアバイパスの設定では、PSTN への通話に対してメディアバイパスを常に試行するか、またはメディアバイパスを使用して、ネットワークサイトおよびネットワーク地域へのサブネットのマッピングを使用するかどうかを指定できます。これは、通話受付管理による処理と同様です。高度な音声機能。</span><span class="sxs-lookup"><span data-stu-id="60fb2-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="60fb2-107">メディアバイパスと通話受付管理の両方が有効になっている場合、メディアバイパスを使用するかどうかを決定するときに、通話受付管理に指定されているネットワーク地域、ネットワークサイト、およびサブネット情報が自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="60fb2-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="60fb2-108">これは、通話受付管理が有効になっている場合に、PSTN への通話に対してメディアバイパスを常に試行することを指定できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="60fb2-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="60fb2-109">このトピックでは、Lync Server コントロールパネルおよび Lync Server 管理シェルを使用して、グローバルメディアバイパス設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="60fb2-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60fb2-110">こうした手順を使用してメディア バイパスを構成する場合は、クライアントと仲介サーバー ピア (PSTN ゲートウェイ、IP-PBX、または SIP トランキング プロバイダーでの SBC など) の間の接続状態が良好であることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="60fb2-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="60fb2-111">リンクに帯域幅制限があると、メディア バイパスを通話に適用できません。</span><span class="sxs-lookup"><span data-stu-id="60fb2-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="60fb2-112">メディア バイパスは、あらゆる PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="60fb2-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="60fb2-113">Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="60fb2-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="60fb2-114">メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>の製品およびバージョンのみです。</span><span class="sxs-lookup"><span data-stu-id="60fb2-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="60fb2-115">次のステップ:  グローバル メディア バイパス設定の選択</span><span class="sxs-lookup"><span data-stu-id="60fb2-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="60fb2-116">特定のサイトまたはサービス用のピアへのトランク接続でメディア パイパスを有効にした後、次のコンテンツをどちらかに使用します。</span><span class="sxs-lookup"><span data-stu-id="60fb2-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="60fb2-117">「 [Configure media バイパス In Lync server 2013](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)」で説明されているように、常にメディアバイパスを有効にして、仲介サーバーをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="60fb2-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="60fb2-118">または、「 [configure media バイパス global settings In Lync Server 2013 in site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)」の説明に従って、サイトと地域の情報を使用するようにメディアバイパスを構成します。</span><span class="sxs-lookup"><span data-stu-id="60fb2-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60fb2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="60fb2-119">See Also</span></span>


[<span data-ttu-id="60fb2-120">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="60fb2-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="60fb2-121">Lync Server 2013 でのサブネットとネットワークサイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="60fb2-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="60fb2-122">Lync Server 2013 でメディアバイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="60fb2-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="60fb2-123">Lync Server 2013 のメディアバイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="60fb2-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

