---
title: 'Lync Server 2013: メディアバイパスを構成して、仲介サーバーを常にバイパスする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="763f3-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span><span class="sxs-lookup"><span data-stu-id="763f3-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="763f3-103">_**最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="763f3-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="763f3-104">このトピックでは、特定のピアに対して、ピア (公衆交換電話網 (PSTN) ゲートウェイ、IP PBX、または、インターネットテレフォニーサービスプロバイダー (ITSP) でのセッション境界コントローラー (SBC)) へのトランク接続に対してメディアバイパスを既に構成していることを前提としています。メディアを仲介サーバーでバイパスするサイトまたはサービス。</span><span class="sxs-lookup"><span data-stu-id="763f3-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="763f3-105">通話受付制御を有効にしている間も、常に仲介サーバーをバイパスするようにメディアを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="763f3-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="763f3-106">これらの設定は互換性がないため、Lync Server コントロールパネルのユーザーインターフェイスでは [相互排他] 設定になります。</span><span class="sxs-lookup"><span data-stu-id="763f3-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="763f3-107">ピアに関連付けられた個々のトランク接続でメディアバイパスを仲介サーバーに有効にすることに加えて、メディアバイパスのグローバル設定を構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="763f3-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="763f3-108">このトピックの手順を使用してメディアのバイパスのグローバル設定を構成する場合、Lync のエンドポイントと、トランク接続でメディアをバイパスするように構成されているすべてのピアとの間に接続が適切であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="763f3-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="763f3-109">Lync Server のエンドポイント間の接続が適切ではなく、各トランク接続がメディアバイパスで有効になっている仲介サーバーへのすべてのピアがある場合は、サイトと地域の情報を使用するようにグローバルメディアバイパス設定を構成する必要があります。メディアバイパスの採用。</span><span class="sxs-lookup"><span data-stu-id="763f3-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="763f3-110">これにより、メディアが仲介サーバーをバイパスするタイミングをより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="763f3-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="763f3-111">これを行うには、「 [Lync server 2013 の [メディアを無視してグローバル設定を構成](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)する」の手順に従って、サイトと地域の情報を使用し、[サブネットを lync server 2013 のネットワークサイトに関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)ます。</span><span class="sxs-lookup"><span data-stu-id="763f3-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="763f3-112">仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには</span><span class="sxs-lookup"><span data-stu-id="763f3-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="763f3-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="763f3-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="763f3-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="763f3-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="763f3-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="763f3-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="763f3-116">リスト内の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="763f3-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="763f3-117">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="763f3-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="763f3-118">[**常にバイパスする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="763f3-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="763f3-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="763f3-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="763f3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="763f3-120">See Also</span></span>


[<span data-ttu-id="763f3-121">Lync Server 2013 メディア バイパスの構成</span><span class="sxs-lookup"><span data-stu-id="763f3-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="763f3-122">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="763f3-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="763f3-123">Lync Server 2013 のメディア バイパスと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="763f3-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="763f3-124">Lync Server 2013 でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="763f3-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

