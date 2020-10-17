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
ms.openlocfilehash: ec067e84c87321374ed1d9beb98c086633f3e28c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515334"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="1dd1a-102">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="1dd1a-102">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dd1a-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="1dd1a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1dd1a-104">このトピックでは、メディアが仲介サーバーをバイパスする特定のサイトまたはサービスについて、ピア (公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはインターネットテレフォニーサービスプロバイダーのセッションボーダーコントローラー (SBC) のいずれかのトランクに対してメディアバイパスが既に構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="1dd1a-105">ピアに関連付けられた個々のトランク接続に対してメディアバイパスを有効にすることに加えて、メディアバイパスをグローバルに有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="1dd1a-106">グローバルメディアバイパス設定では、PSTN への通話に対してメディアバイパスを常に試行するか、またはメディアバイパスをネットワークサイトおよびネットワーク地域にマッピングすることによって使用されるかを指定できます。これは、通話受付管理、もう1つの高度な音声機能によって行われる処理に似ています。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="1dd1a-107">メディアバイパスと通話受付管理の両方が有効になっている場合、メディアバイパスを使用するかどうかを決定するときに、通話受付管理に指定されているネットワーク地域、ネットワークサイト、およびサブネット情報が自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="1dd1a-108">これは、通話受付管理が有効になっている場合に、PSTN への通話に対してメディアバイパスを常に試行することを指定できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="1dd1a-109">このトピックでは、Lync Server コントロールパネルおよび Lync Server 管理シェルを使用して、グローバルメディアバイパス設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1dd1a-110">こうした手順を使用してメディア バイパスを構成する場合は、クライアントと仲介サーバー ピア (PSTN ゲートウェイ、IP-PBX、または SIP トランキング プロバイダーでの SBC など) の間の接続状態が良好であることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="1dd1a-111">リンクに帯域幅制限があると、メディア バイパスを通話に適用できません。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="1dd1a-112">メディア バイパスは、あらゆる PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="1dd1a-113">Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="1dd1a-114">メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at の製品およびバージョンのみです <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="1dd1a-115">次のステップ:  グローバル メディア バイパス設定の選択</span><span class="sxs-lookup"><span data-stu-id="1dd1a-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="1dd1a-116">特定のサイトまたはサービス用のピアへのトランク接続でメディア パイパスを有効にした後、次のコンテンツをどちらかに使用します。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="1dd1a-117">「 [Configure media バイパス In Lync server 2013](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)」で説明されているように、常にメディアバイパスを有効にして、仲介サーバーをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="1dd1a-118">または、「 [configure media バイパス global settings In Lync Server 2013 in site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)」の説明に従って、サイトと地域の情報を使用するようにメディアバイパスを構成します。</span><span class="sxs-lookup"><span data-stu-id="1dd1a-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1dd1a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dd1a-119">See Also</span></span>


[<span data-ttu-id="1dd1a-120">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="1dd1a-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="1dd1a-121">Lync Server 2013 でのサブネットとネットワークサイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="1dd1a-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="1dd1a-122">Lync Server 2013 でメディアバイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="1dd1a-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="1dd1a-123">Lync Server 2013 のメディアバイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="1dd1a-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

