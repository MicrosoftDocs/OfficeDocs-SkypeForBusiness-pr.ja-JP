---
title: 'Lync Server 2013: ハイブリッドおよび分割ドメイン-自動検出'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="69bef-102">ハイブリッドおよび分割ドメイン-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="69bef-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69bef-103">_**最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="69bef-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="69bef-104">共有 SIP アドレス空間 (*分割ドメイン*展開とも呼ばれます) または*ハイブリッド*展開とも呼ばれる構成で、ユーザーがオンプレミスの展開とオンライン環境を通じて展開されます。</span><span class="sxs-lookup"><span data-stu-id="69bef-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="69bef-105">必要な結果は、ホームサーバーが配置されている場所 (オンプレミスまたはオンライン) に関係なく、展開にログインし、ホームサーバーの場所にリダイレクトされることです。</span><span class="sxs-lookup"><span data-stu-id="69bef-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="69bef-106">これを実現するために、Lync Server 2013 の自動検出機能を使用して、オンラインユーザーをオンライントポロジにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="69bef-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="69bef-107">これを行うには、Lync Server 管理シェル、 **Get-CsHostingProvider**コマンドレット、 **Set-cshostingprovider**コマンドレットを使用して、自動検出の UNIFORM resource locator (URL) を構成します。</span><span class="sxs-lookup"><span data-stu-id="69bef-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="69bef-108">分離ドメイン展開のモビリティ</span><span class="sxs-lookup"><span data-stu-id="69bef-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="69bef-109">次の展開された属性を収集して記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bef-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="69bef-110">Lync Server 管理シェルで、「</span><span class="sxs-lookup"><span data-stu-id="69bef-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="69bef-111">結果で、属性**Proxyfqdn**を含むオンラインプロバイダーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="69bef-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="69bef-112">たとえば、sipfed.online.lync.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="69bef-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="69bef-113">ProxyFQDN の値を記録します。</span><span class="sxs-lookup"><span data-stu-id="69bef-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="69bef-114">オンプレミスの Lync Server コントロールパネルでフェデレーションを有効にして、オンラインプロバイダーとのフェデレーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="69bef-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="69bef-115">オンラインプロバイダーのフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="69bef-115">Enable federation for the online provider.</span></span> <span data-ttu-id="69bef-116">既定では、すべてのオンラインユーザーがドメインフェデレーションを有効にしており、すべてのドメインと通信できます。</span><span class="sxs-lookup"><span data-stu-id="69bef-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="69bef-117">ブロックされるドメインと許可ドメインを定義する場合は、明示的に許可する、または明示的にブロックするドメインを決定します。</span><span class="sxs-lookup"><span data-stu-id="69bef-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="69bef-118">オンラインフェデレーションの場合、ファイアウォールの例外、証明書、DNS ホスト (IPv6 を使用している場合は AAAA) を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bef-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="69bef-119">さらに、フェデレーションポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69bef-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="69bef-120">詳細については、「 [Lync server 2013 と Office Communications server フェデレーションの計画](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69bef-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

