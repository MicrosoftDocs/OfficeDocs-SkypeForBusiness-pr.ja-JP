---
title: 'Lync Server 2013: ハイブリッドおよびスプリットドメイン自動検出'
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
ms.openlocfilehash: d181887ad031a1873b289600de3f59b9d3131dd0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="8cec9-102">Lync Server 2013 でのハイブリッドおよびスプリットドメインの自動検出</span><span class="sxs-lookup"><span data-stu-id="8cec9-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cec9-103">_**トピックの最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="8cec9-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="8cec9-104">共有 SIP アドレススペース (*分割ドメイン*展開または*ハイブリッド*展開とも呼ばれる) は、ユーザーがオンプレミス展開とオンライン環境の間で展開される構成です。</span><span class="sxs-lookup"><span data-stu-id="8cec9-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="8cec9-105">必要な結果は、自分のホームサーバーが配置されている場所 (オンプレミスまたはオンライン) に関係なく、ユーザーが展開にログインして、ホームサーバーの場所にリダイレクトされることです。</span><span class="sxs-lookup"><span data-stu-id="8cec9-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="8cec9-106">これを実現するために、Lync Server 2013 の自動検出機能を使用して、オンラインユーザーをオンライントポロジにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="8cec9-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="8cec9-107">これを行うには、Lync Server 管理シェル、 **get-help**コマンドレット、および**Set-CsHostingProvider**コマンドレットを使用して、自動検出の UNIFORM resource locator (URL) を構成します。</span><span class="sxs-lookup"><span data-stu-id="8cec9-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="8cec9-108">分割ドメイン展開でのモビリティ</span><span class="sxs-lookup"><span data-stu-id="8cec9-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="8cec9-109">次の展開属性を収集して記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cec9-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="8cec9-110">Lync Server 管理シェルで、と入力します。</span><span class="sxs-lookup"><span data-stu-id="8cec9-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="8cec9-111">結果で、属性**Proxyfqdn**を持つオンラインプロバイダーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="8cec9-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="8cec9-112">たとえば、sipfed.online.lync.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="8cec9-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="8cec9-113">ProxyFQDN の値を記録します。</span><span class="sxs-lookup"><span data-stu-id="8cec9-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="8cec9-114">オンプレミスの Lync Server コントロールパネルでフェデレーションを有効にし、オンラインプロバイダーとのフェデレーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="8cec9-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="8cec9-115">オンライン プロバイダーに対してフェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cec9-115">Enable federation for the online provider.</span></span> <span data-ttu-id="8cec9-116">既定では、すべてのオンラインユーザーがドメインフェデレーションに対して有効になっており、すべてのドメインと通信できます。</span><span class="sxs-lookup"><span data-stu-id="8cec9-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="8cec9-117">禁止ドメインと許可ドメインを定義する場合は、明示的に許可または明示的に禁止するドメインを決定します。</span><span class="sxs-lookup"><span data-stu-id="8cec9-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="8cec9-118">オンラインフェデレーションの場合は、ファイアウォール例外、証明書、および DNS ホスト (IPv6 を使用する場合は A または AAAA) のレコードを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cec9-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="8cec9-119">また、フェデレーション ポリシーを構成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8cec9-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="8cec9-120">詳細については、「 [Planning For Lync Server 2013 And Office Communications server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cec9-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

