---
title: 'Lync Server 2013: 大規模会議のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c98166b42f48e328809960279b9934b87670101b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="6e741-102">Lync Server 2013 での大規模会議のサポート</span><span class="sxs-lookup"><span data-stu-id="6e741-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e741-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6e741-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6e741-104">Lync Server 2013 は、PowerPoint プレゼンテーションの共有など、音声/ビデオ (A/V) 会議を使用して、最大1000の参加者との会議をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="6e741-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="6e741-105">このサポートには、大規模な会議をサポートするように構成され、一度に 1 つの大規模な会議のみ開催するような方法で管理される専用プールが必要です。</span><span class="sxs-lookup"><span data-stu-id="6e741-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="6e741-106">このセクションでは、専用の Lync Server 2013 プールを使用して大規模な会議をサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e741-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="6e741-107">スケーラビリティの考慮事項、およびトポロジ、ハードウェア、ソフトウェア、構成の要件を含む、専用プールの実装要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e741-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="6e741-108">さらに、大規模な会議のサポートに関するベストプラクティスの推奨事項、Lync Server エンジニアリングチームが実施したサーバーのスケーラビリティテストの概要、サポートについてよく寄せられる質問に対する回答を紹介します。大規模な会議の場合。</span><span class="sxs-lookup"><span data-stu-id="6e741-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e741-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="6e741-109">In This Section</span></span>

  - [<span data-ttu-id="6e741-110">Lync Server 2013 での会議のスケーラビリティの概要</span><span class="sxs-lookup"><span data-stu-id="6e741-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="6e741-111">Lync Server 2013 を使用した大規模な会議のサポート</span><span class="sxs-lookup"><span data-stu-id="6e741-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="6e741-112">Lync Server 2013 の大規模な会議のサポートについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="6e741-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

