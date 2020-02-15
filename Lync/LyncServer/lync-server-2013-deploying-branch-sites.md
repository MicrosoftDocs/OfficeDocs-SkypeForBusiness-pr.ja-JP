---
title: 'Lync Server 2013: ブランチサイトの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edacf70cf4a8b899857864c400fa92f78bb0d94b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="89ce9-102">Lync Server 2013 でのブランチサイトの展開</span><span class="sxs-lookup"><span data-stu-id="89ce9-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89ce9-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="89ce9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="89ce9-104">ブランチサイトユーザーは、ブランチサイトが関連付けられている中央サイトのサーバーから Lync Server 2013 の機能の大部分を取得します。</span><span class="sxs-lookup"><span data-stu-id="89ce9-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="89ce9-105">各ブランチ サイトは、1 つだけのセントラル サイトに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="89ce9-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="89ce9-106">公衆交換電話網 (PSTN) へ、または公衆交換電話網 (PSTN) からの通話を提供するため、ブランチ サイトは次のいずれかを含みます。</span><span class="sxs-lookup"><span data-stu-id="89ce9-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="89ce9-107">PSTN ゲートウェイおよび場合によっては仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="89ce9-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="89ce9-108">SIP トランク</span><span class="sxs-lookup"><span data-stu-id="89ce9-108">A SIP trunk</span></span>

  - <span data-ttu-id="89ce9-109">構内交換機 (PBX) と既存の音声インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="89ce9-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="89ce9-110">存続可能ブランチアプライアンス</span><span class="sxs-lookup"><span data-stu-id="89ce9-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="89ce9-111">存続可能ブランチサーバー</span><span class="sxs-lookup"><span data-stu-id="89ce9-111">A Survivable Branch Server</span></span>

<span data-ttu-id="89ce9-112">存続可能 Branch Appliance または存続可能ブランチサーバーを使用するブランチサイトでは、これらのソリューションのいずれも含まれていないブランチサイトと比べて、広域ネットワークまたは中央サイトの障害が発生する時間での復元が向上します。</span><span class="sxs-lookup"><span data-stu-id="89ce9-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="89ce9-113">たとえば、存続可能 Branch Appliance または存続可能 Branch Server が展開されているサイトでは、ブランチサイトを中央サイトに接続しているネットワークがダウンしている場合でも、ユーザーは PSTN 通話を発信および受信できます。</span><span class="sxs-lookup"><span data-stu-id="89ce9-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="89ce9-114">ブランチサイトの復元を実現するもう1つの方法は、ブランチサイトでのフルスケールの Lync Server 展開を使用した PSTN ゲートウェイまたは SIP トランクの使用です。</span><span class="sxs-lookup"><span data-stu-id="89ce9-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="89ce9-115">前提条件やその他の計画に関する考慮事項など、組織に適したブランチサイト展開の詳細については、「計画」のドキュメントの「lync server [2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)」および「 [lync server 2013 でのブランチサイト音声の復元の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ce9-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89ce9-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="89ce9-116">In This Section</span></span>

  - [<span data-ttu-id="89ce9-117">Lync Server 2013 のブランチサイトでの PSTN 接続の提供</span><span class="sxs-lookup"><span data-stu-id="89ce9-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="89ce9-118">Lync Server 2013 を使用した存続可能ブランチアプライアンスまたはサーバーの展開</span><span class="sxs-lookup"><span data-stu-id="89ce9-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

