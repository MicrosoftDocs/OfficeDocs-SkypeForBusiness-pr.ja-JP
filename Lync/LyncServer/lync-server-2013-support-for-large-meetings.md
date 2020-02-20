---
title: Lync Server 2013 の大規模会議のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9524867cd96df5ce7930bf0739911318f04331e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="e3f22-102">Lync Server 2013 での大規模会議のサポート</span><span class="sxs-lookup"><span data-stu-id="e3f22-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3f22-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e3f22-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e3f22-104">Lync Server 2013 は、PowerPoint プレゼンテーションの共有を含む、音声ビデオ (A/V) 会議を使用した最大1000参加者との会議をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="e3f22-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="e3f22-105">このサポートには、大規模な会議をサポートするように構成され、一度に 1 つの大規模な会議のみ開催するような方法で管理される専用プールが必要です。</span><span class="sxs-lookup"><span data-stu-id="e3f22-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="e3f22-106">このセクションでは、専用の Lync Server 2013 プールを使用して大規模な会議をサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3f22-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="e3f22-107">スケーラビリティの考慮事項と、トポロジ、ハードウェア、ソフトウェア、および構成の要件を含む専用プールの実装要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3f22-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="e3f22-108">また、大規模な会議のサポートに関するベストプラクティスの推奨事項、Lync Server エンジニアリングチームが実施したサーバーのスケーラビリティテストの概要、およびサポートについてよく寄せられる質問への回答を提供します。大規模な会議の場合。</span><span class="sxs-lookup"><span data-stu-id="e3f22-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e3f22-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e3f22-109">In This Section</span></span>

  - [<span data-ttu-id="e3f22-110">Lync Server 2013 での会議のスケーラビリティの概要</span><span class="sxs-lookup"><span data-stu-id="e3f22-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="e3f22-111">Lync Server 2013 を使用した大規模会議のサポート</span><span class="sxs-lookup"><span data-stu-id="e3f22-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="e3f22-112">Lync Server 2013 の大規模会議のサポートに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="e3f22-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

