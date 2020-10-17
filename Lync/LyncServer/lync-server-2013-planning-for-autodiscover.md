---
title: 'Lync Server 2013: 自動検出の計画'
description: 'Lync Server 2013: 自動検出の計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544633"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="39346-103">Lync Server 2013 での自動検出の計画</span><span class="sxs-lookup"><span data-stu-id="39346-103">Planning for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39346-104">_**トピックの最終更新日:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="39346-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="39346-105">Lync server 2010 の累積的な更新プログラムで、Lync Server の自動検出が導入されました。11月2011。</span><span class="sxs-lookup"><span data-stu-id="39346-105">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="39346-106">この自動検出の初期実装の主な目的は、Lync Mobile が Mobility service (Mcx) を特定する手段を提供することでした。</span><span class="sxs-lookup"><span data-stu-id="39346-106">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="39346-107">Lync Server 2013 の自動検出サービスは、サーバーとユーザーのサービスを検索するためにすべてのクライアントが使用するサービスになりました。</span><span class="sxs-lookup"><span data-stu-id="39346-107">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="39346-108">Microsoft Lync Server 2013 自動検出サービスは、ディレクターおよびフロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="39346-108">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="39346-109">自動検出とクライアントへの通知についてのより技術的な知識については、「 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013 の自動検出につい</A>て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39346-109">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="39346-110">モビリティは依然として別個のシナリオであり、Mobility service ではまだ特別な計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="39346-110">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="39346-111">詳細については、「 <A href="lync-server-2013-planning-for-mobility.md">Lync Server 2013 でのモビリティの計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39346-111">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="39346-112">Lync Server 2010 で自動検出が導入された場合、既存のサーバー展開に対する証明書の変更を必要とするサービスを実装するために必要な妥協が行われました。</span><span class="sxs-lookup"><span data-stu-id="39346-112">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="39346-113">HTTPS のポート TCP 443、または HTTP のポート TCP 80 経由で自動検出を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="39346-113">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="39346-114">HTTPS を使用することを決定した場合は、必要な `lyncdiscover.<domain>` および DNS レコードを格納するために、リバースプロキシ、ディレクター、フロントエンドサーバーの証明書を再発行する必要がありました `lyncdiscoverinternal.<domain>` 。</span><span class="sxs-lookup"><span data-stu-id="39346-114">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="39346-115">HTTP を使用することを決定した場合は、証明書の既存の名前を使用するために DNS の CNAME (またはエイリアス) レコードを使用して、証明書の再発行を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="39346-115">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="39346-116">HTTP を使用することは、初期通信が暗号化されていなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="39346-116">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="39346-117">Lync Server 2013 はすべてのクライアントに対して自動検出を使用するため、主なシナリオは、HTTPS のみを使用して lyncdiscover で証明書を作成することです。\<domain\></span><span class="sxs-lookup"><span data-stu-id="39346-117">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\></span></span> <span data-ttu-id="39346-118">リバースプロキシ、ディレクター、フロントエンドサーバーの構成の一部として。</span><span class="sxs-lookup"><span data-stu-id="39346-118">as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="39346-119">Lync Server 2010 からアップグレードされた展開に自動検出を実装する場合、HTTP を使用して証明書の再発行を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="39346-119">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="39346-120">両方のシナリオのガイダンスについては、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="39346-120">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="39346-121">外部 web サービス公開ルールで使用される証明書のサブジェクトの別名リストには、lyncdiscover が含まれている必要があり<EM>ます。 &lt;組織 &gt; </EM>内の各 SIP ドメインの microsoft.rtc.management.xds.sipdomain エントリ。</span><span class="sxs-lookup"><span data-stu-id="39346-121">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="39346-122">ディレクター、フロントエンドサーバー、およびリバースプロキシで必要とされるサブジェクトの別名エントリの詳細については、「 <A href="lync-server-2013-certificate-summary-autodiscover.md">証明書の概要-Lync Server 2013 での自動検出</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39346-122">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="39346-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="39346-123">In This Section</span></span>

  - [<span data-ttu-id="39346-124">証明書の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="39346-124">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="39346-125">ポートの概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="39346-125">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="39346-126">DNS の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="39346-126">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="39346-127">Lync Server 2013 でのハイブリッドおよびスプリットドメインの自動検出</span><span class="sxs-lookup"><span data-stu-id="39346-127">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

