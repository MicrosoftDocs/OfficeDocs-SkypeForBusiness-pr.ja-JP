---
title: 'Lync Server 2013: XMPP フェデレーションに使用するエッジプールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aee795b6f4dd1f3ff1077fb739cad9709b2c8ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="e84da-102">Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="e84da-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e84da-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e84da-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e84da-p101">組織内に XMPP フェデレーションに使用するプールとして指定されたエッジ プールが 1 つあるとします。このプールがダウンした場合、XMPP フェデレーションを再び機能させるには、XMPP フェデレーションをフェールオーバーして別のエッジ プールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e84da-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="e84da-106">エッジ プールを初めてインストールし、XMPP フェデレーションを有効にするときに、1 つのエッジ プールではなく、すべてのエッジ プールで XMPP フェデレーションの外部 DNS SRV レコードを設定することで障害復旧プロセスを簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="e84da-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="e84da-107">これらの SRV レコードには、それぞれ異なる優先順位が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e84da-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="e84da-108">すべての XMPP フェデレーション トラフィックは、優先順位が最も高い SRV レコードを使用してプールを通過します。</span><span class="sxs-lookup"><span data-stu-id="e84da-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="e84da-109">XMPP フェデレーションの有効化およびセットアップの詳細については、「 [Lync Server 2013 での xmpp フェデレーションの設定](lync-server-2013-setting-up-xmpp-federation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e84da-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="e84da-110">次の手順では、EdgePool1 は XMPP フェデレーションをホストしていた元のプールを表し、EdgePool2 は XMPP フェデレーションをこれからホストするプールを表します。</span><span class="sxs-lookup"><span data-stu-id="e84da-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="e84da-111">XMPP フェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="e84da-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="e84da-112">(現在ダウンしているエッジ プール以外の) 別のエッジ プールをまだ展開していない場合は、そのプールを展開します。</span><span class="sxs-lookup"><span data-stu-id="e84da-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="e84da-113">詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e84da-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="e84da-114">XMPP フェデレーションをホストする新しいエッジ プール (EdgePool2) の各エッジ サーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e84da-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="e84da-115">XMPP フェデレーション ルートを変更して EdgePool2 を指すようにするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e84da-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="e84da-116">この例で、Site2 は XMPP フェデレーション ルートをこれからホストするエッジ プールを含むサイトを表します。また、EdgeServer2.contoso.com はそのプール内のエッジ サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="e84da-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="e84da-117">外部 DNS サーバーで、XMPP フェデレーションの DNS A レコードを変更して、EdgeServer2.contoso.com を指すようにします。</span><span class="sxs-lookup"><span data-stu-id="e84da-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="e84da-p104">XMPP フェデレーションをホストする新しいエッジ プールに解決される、XMPP フェデレーションの DNS SRV レコードがまだない場合は、次の例に示すように、このレコードを追加する必要があります。この SRV レコードには、ポート値 5269 が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e84da-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="e84da-120">XMPP フェデレーションをホストする新しいエッジ プールで、ポート 5269 が外部に開いていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e84da-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="e84da-121">XMPP フェデレーションをホストする新しいエッジ プール内のすべてのエッジ サーバーでサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e84da-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

