---
title: 'Lync Server 2013: ブランチ サイトの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="fe8a9-102">Lync Server 2013 でのブランチ サイトの展開</span><span class="sxs-lookup"><span data-stu-id="fe8a9-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe8a9-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="fe8a9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="fe8a9-104">ブランチサイトユーザーは、ブランチサイトが関連付けられているセントラルサイトのサーバーから、Lync Server 2013 のほとんどの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="fe8a9-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="fe8a9-105">各ブランチサイトは、1つのセントラルサイトと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="fe8a9-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="fe8a9-106">公衆交換電話網 (PSTN) との間で通話を発信するには、ブランチサイトに次のいずれかを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fe8a9-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="fe8a9-107">PSTN ゲートウェイと、おそらく Meditation Server</span><span class="sxs-lookup"><span data-stu-id="fe8a9-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="fe8a9-108">SIP トランク</span><span class="sxs-lookup"><span data-stu-id="fe8a9-108">A SIP trunk</span></span>

  - <span data-ttu-id="fe8a9-109">構内交換 (PBX) を使用する既存の音声インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="fe8a9-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="fe8a9-110">Survivable Branch アプライアンス</span><span class="sxs-lookup"><span data-stu-id="fe8a9-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="fe8a9-111">Survivable ブランチサーバー</span><span class="sxs-lookup"><span data-stu-id="fe8a9-111">A Survivable Branch Server</span></span>

<span data-ttu-id="fe8a9-112">Survivable Branch Appliance または Survivable ブランチサーバーを使用しているブランチサイトでは、このようなソリューションを使用することなく、広域ネットワークまたはセントラルサイトの障害が発生した場合よりも高い弾力性があります。</span><span class="sxs-lookup"><span data-stu-id="fe8a9-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="fe8a9-113">たとえば、Survivable Branch Appliance または Survivable Branch Server が展開されているサイトでは、ブランチサイトをセントラルサイトに接続しているネットワークがダウンしている場合でも、ユーザーは PSTN 通話の発信と受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fe8a9-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="fe8a9-114">ブランチサイトの回復性を実現するもう1つの方法として、PSTN ゲートウェイまたは SIP トランクを使用して、ブランチサイトでのフルスケールの Lync Server 展開を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="fe8a9-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="fe8a9-115">前提条件などの計画上の考慮事項を含む、組織に適したブランチサイトの展開の詳細については、「 [Lync Server 2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)」および「 [lync でのブランチサイトボイスの回復性の計画」を参照してください。](lync-server-2013-planning-for-branch-site-voice-resiliency.md)計画ドキュメントのサーバー2013</span><span class="sxs-lookup"><span data-stu-id="fe8a9-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fe8a9-116">このセクション中</span><span class="sxs-lookup"><span data-stu-id="fe8a9-116">In This Section</span></span>

  - [<span data-ttu-id="fe8a9-117">Lync Server 2013 におけるブランチ サイトでの PSTN 接続の提供</span><span class="sxs-lookup"><span data-stu-id="fe8a9-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="fe8a9-118">Lync Server 2013 を使用した存続可能ブランチ アプライアンスまたはサーバーの展開</span><span class="sxs-lookup"><span data-stu-id="fe8a9-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

