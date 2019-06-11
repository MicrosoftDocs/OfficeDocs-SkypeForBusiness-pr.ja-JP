---
title: 'Lync Server 2013: XMPP フェデレーションに使用するエッジ プールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="a774c-102">Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="a774c-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a774c-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a774c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a774c-104">組織では、1つのエッジプールがプールとして指定されています。</span><span class="sxs-lookup"><span data-stu-id="a774c-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="a774c-105">このプールがダウンした場合は、xmpp フェデレーションを再度使用する前に、別のエッジプールを使用するために XMPP フェデレーションをフェイルオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a774c-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="a774c-106">最初に Edge プールをインストールして XMPP フェデレーションを有効にすると、1つの代わりに XMPP のすべてのエッジプールの外部 DNS SRV レコードを設定することで、障害回復プロセスを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="a774c-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="a774c-107">各 SRV レコードには、異なる優先順位を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a774c-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="a774c-108">すべての XMPP フェデレーショントラフィックは、最も優先度の高い SRV レコードを持つプールを通過します。</span><span class="sxs-lookup"><span data-stu-id="a774c-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="a774c-109">XMPP フェデレーションを有効にしてセットアップする方法について詳しくは、「 [Lync Server 2013 での XMPP フェデレーションの](lync-server-2013-setting-up-xmpp-federation.md)セットアップ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a774c-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="a774c-110">次の手順では、EdgePool1 は最初に XMPP フェデレーションをホストしたプールであり、EdgePool2 は XMPP フェデレーションをホストするプールです。</span><span class="sxs-lookup"><span data-stu-id="a774c-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="a774c-111">XMPP フェデレーションに使用されるエッジプールのフェイルオーバー</span><span class="sxs-lookup"><span data-stu-id="a774c-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="a774c-112">(現在ダウンしている) 別の Edge プールをまだ展開していない場合は、そのプールを展開します。</span><span class="sxs-lookup"><span data-stu-id="a774c-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="a774c-113">詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a774c-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="a774c-114">新しいエッジプールの各エッジサーバーで XMPP federation (EdgePool2) をホストするために、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a774c-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="a774c-115">XMPP フェデレーションルートを EdgePool2 に再ポイントするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a774c-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="a774c-116">この例では、Site2 は、XMPP フェデレーションルートをホストするエッジプールが含まれているサイトで、EdgeServer2.contoso.com はそのプールのエッジサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="a774c-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="a774c-117">外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードを EdgeServer2.contoso.com に変更します。</span><span class="sxs-lookup"><span data-stu-id="a774c-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="a774c-118">Xmpp フェデレーション用の DNS SRV レコードをまだ持っていない場合は、次の例のように、それを追加する必要があります。これは、現在 XMPP フェデレーションをホストしています。</span><span class="sxs-lookup"><span data-stu-id="a774c-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="a774c-119">この SRV レコードには、5269のポート値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a774c-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="a774c-120">XMPP フェデレーションをホストしている Edge プールのポート5269が外部で開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a774c-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="a774c-121">Edge プール内のすべてのエッジサーバーでサービスを開始します。これで、XMPP フェデレーションがホストされます。</span><span class="sxs-lookup"><span data-stu-id="a774c-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

