---
title: 'Lync Server 2013: メディアバイパスを構成して仲介サーバーを常にバイパスする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76cf44ee24c94b4a243fe84db1f3bbf7a28ba2e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="ccda6-102">Lync Server 2013 でメディアバイパスを構成して仲介サーバーを常にバイパスする</span><span class="sxs-lookup"><span data-stu-id="ccda6-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccda6-103">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="ccda6-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ccda6-104">このトピックは、メディアに仲介サーバーをバイパスさせたい特定のサイトまたはサービスのピア (公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC)) へのすべてのトランク接続に、すでにメディア バイパスを構成したことを前提にしています。</span><span class="sxs-lookup"><span data-stu-id="ccda6-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="ccda6-105">通話受付管理もまた有効である状態で、常に仲介サーバーをバイパスするようにメディアを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ccda6-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="ccda6-106">これらの設定は互換性がありません。そのため、Lync Server コントロールパネルのユーザーインターフェイスでは [相互排他的] 設定になります。</span><span class="sxs-lookup"><span data-stu-id="ccda6-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="ccda6-107">仲介サーバーへのピアに関連付けられた個別のトランク接続に対してメディア バイパスを有効にするのに加え、メディア バイパスのグローバル設定もまた構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccda6-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="ccda6-108">このトピックの手順を使用してメディアバイパスのグローバル設定を構成する場合、Lync エンドポイントと、トランク接続でメディアバイパスを構成したすべてのピアとの間の接続が良好であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ccda6-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="ccda6-109">Lync Server エンドポイントと、それぞれのトランク接続がメディアバイパスが有効になっている仲介サーバーへの接続が良好ではない場合は、次の場合にサイトと地域の情報を使用するようにグローバルメディアバイパス設定を構成する必要があります。メディアバイパスの採用。</span><span class="sxs-lookup"><span data-stu-id="ccda6-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="ccda6-110">これにより、メディアが仲介サーバーをバイパスするか判定する際に、よりよく制御できます。</span><span class="sxs-lookup"><span data-stu-id="ccda6-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="ccda6-111">そのためには、「 [Configure media バイパス global settings In Lync server 2013」](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)の手順を使用して、サイトと地域の情報を使用し、[サブネットを lync server 2013 のネットワークサイトに関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)ます。</span><span class="sxs-lookup"><span data-stu-id="ccda6-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="ccda6-112">仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには</span><span class="sxs-lookup"><span data-stu-id="ccda6-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="ccda6-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ccda6-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ccda6-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccda6-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="ccda6-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccda6-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="ccda6-116">リスト内の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccda6-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="ccda6-117">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ccda6-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="ccda6-118">[**常にバイパスする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccda6-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="ccda6-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccda6-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ccda6-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccda6-120">See Also</span></span>


[<span data-ttu-id="ccda6-121">Lync Server 2013 でメディアバイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="ccda6-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="ccda6-122">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="ccda6-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="ccda6-123">Lync Server 2013 のメディアバイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="ccda6-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="ccda6-124">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="ccda6-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

