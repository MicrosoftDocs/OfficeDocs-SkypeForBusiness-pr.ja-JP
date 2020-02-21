---
title: 'Lync Server 2013: 新しいエンタープライズ Voip 機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c18c766fbb1116ecad92e7122892abbb0d983d5c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="9f0a5-102">Lync Server 2013 の新しいエンタープライズ Voip 機能</span><span class="sxs-lookup"><span data-stu-id="9f0a5-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f0a5-103">_**トピックの最終更新日:** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="9f0a5-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="9f0a5-104">Lync Server 2013 には、エンタープライズ Voip を強化するための、いくつかの新しいルーティングおよび通話管理機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="9f0a5-105">Lync Server 2013 は、仲介サーバーとゲートウェイ間での複数のトランクをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="9f0a5-106">*トランク*とは、ポート番号と仲介サーバーとポート番号およびゲートウェイとの間の論理的な関連付けのことです。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="9f0a5-107">これは、仲介サーバーが異なるゲートウェイに対して複数のトランクを持つことができ、ゲートウェイが異なる仲介サーバーに対して複数のトランクを持つことができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="9f0a5-108">トランク間ルーティングを使用すると、Lync Server 2013 が ip-pbx を公衆交換電話網 (PSTN) ゲートウェイに接続したり、複数の ip-pbx システムを相互接続したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="9f0a5-109">Lync Server 2013 は、異なるテレフォニーシステム間の glue (つまり相互接続) として機能します。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="9f0a5-110">Microsoft Lync Server 2013 は、着信の転送、同時呼び出し、ボイスメール処理、および発信者番号表示の領域を改善します。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="9f0a5-111">これらの機能により、エンタープライズ Voip の呼び出しの利便性が向上します。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="9f0a5-112">Lync Server 2013 には、エンタープライズ Voip の次のような新しい拡張機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="9f0a5-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="9f0a5-113">Lync Server 2013 の新しい通話機能</span><span class="sxs-lookup"><span data-stu-id="9f0a5-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="9f0a5-114">Lync Server 2013 の新しい発信者番号の機能</span><span class="sxs-lookup"><span data-stu-id="9f0a5-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="9f0a5-115">Lync Server 2013 の新しいボイスメール機能</span><span class="sxs-lookup"><span data-stu-id="9f0a5-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="9f0a5-116">Lync Server 2013 の新しいトランク機能</span><span class="sxs-lookup"><span data-stu-id="9f0a5-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="9f0a5-117">Lync Server 2013 の新しいトランク間機能</span><span class="sxs-lookup"><span data-stu-id="9f0a5-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="9f0a5-118">Lync Server 2013 の新しい通話管理機能</span><span class="sxs-lookup"><span data-stu-id="9f0a5-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

