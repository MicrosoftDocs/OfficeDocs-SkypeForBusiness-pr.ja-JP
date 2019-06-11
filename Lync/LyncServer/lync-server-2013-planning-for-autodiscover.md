---
title: 'Lync Server 2013: 自動検出の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="ff257-102">Lync Server 2013 での自動検出の計画</span><span class="sxs-lookup"><span data-stu-id="ff257-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff257-103">_**最終更新日:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="ff257-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="ff257-104">自動検出は、Lync server 2010 向けの累積的な更新プログラム (2011 年11月) で Lync Server に導入されました。</span><span class="sxs-lookup"><span data-stu-id="ff257-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="ff257-105">自動検出の最初の実装の主な目的は、モバイルサービス (Mcx) を見つけるために Lync Mobile の手段を提供することでした。</span><span class="sxs-lookup"><span data-stu-id="ff257-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="ff257-106">Lync Server 2013 の自動検出サービスは、すべてのクライアントがサーバーおよびユーザーサービスを検索するために使用するサービスになりました。</span><span class="sxs-lookup"><span data-stu-id="ff257-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="ff257-107">Microsoft Lync Server 2013 自動検出サービスは、取締役およびフロントエンドサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ff257-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ff257-108">自動検出とクライアントへの伝達についての技術的な理解については、「 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013 での自動検出につい</A>て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff257-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="ff257-109">機動性は、依然として個別のシナリオであり、モビリティサービスでは引き続き特別な計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="ff257-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="ff257-110">詳細については、「 <A href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff257-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ff257-111">Lync Server 2010 で自動検出が導入された場合、既存のサーバー展開に対して証明書の変更が必要になるサービスを実装するために必要な侵害がありました。</span><span class="sxs-lookup"><span data-stu-id="ff257-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="ff257-112">自動検出は、HTTPS のポート TCP 443 または HTTP のポート TCP 80 経由で使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ff257-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="ff257-113">HTTPS を使用することに決められた場合、リバースプロキシ、監督、フロントエンドサーバー上の証明書は、必要な`lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` DNS レコードと DNS レコードに対応するために再発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff257-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="ff257-114">HTTP を使用すると判断された場合は、証明書の既存の名前を使用するために DNS CNAME (エイリアス) レコードを使用することで、証明書の再発行を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="ff257-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="ff257-115">HTTP では、最初の通信が暗号化されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ff257-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="ff257-116">Lync Server 2013 ではすべてのクライアントに対して自動検出が使用されるため、主なシナリオとしては、HTTPS のみを使用し、lyncdiscover で証明書を作成することをお勧めします。\<リバース\>プロキシ、ディレクター、フロントエンドサーバーの構成の一部としてのドメイン。</span><span class="sxs-lookup"><span data-stu-id="ff257-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="ff257-117">自動検出を Lync Server 2010 からアップグレードされた展開に実装する場合は、HTTP を使用して、証明書の再発行を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="ff257-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="ff257-118">両方のシナリオに関するガイダンスについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="ff257-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff257-119">外部 web サービス公開ルールによって使用される証明書のサブジェクト代替名リストには、lyncdiscover が含まれている必要があり<EM>ます。&lt;組織&gt; </EM>内の各 SIP ドメインの sipdomain エントリ。</span><span class="sxs-lookup"><span data-stu-id="ff257-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="ff257-120">ディレクター、フロントエンドサーバー、リバースプロキシに必要な件名の代替名エントリの詳細については、「<A href="lync-server-2013-certificate-summary-autodiscover.md">証明書の概要-Lync Server 2013 での自動検出</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff257-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff257-121">このセクション中</span><span class="sxs-lookup"><span data-stu-id="ff257-121">In This Section</span></span>

  - [<span data-ttu-id="ff257-122">証明書の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="ff257-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="ff257-123">ポートの概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="ff257-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="ff257-124">DNS 概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="ff257-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="ff257-125">ハイブリッドおよび分割ドメイン-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="ff257-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

