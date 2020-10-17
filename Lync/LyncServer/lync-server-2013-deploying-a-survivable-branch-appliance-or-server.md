---
title: 'Lync Server 2013: 存続可能ブランチアプライアンスまたはサーバーの展開'
description: 'Lync Server 2013: 存続可能ブランチアプライアンスまたはサーバーの展開。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558593"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="ffda1-103">Lync Server 2013 を使用した存続可能ブランチアプライアンスまたはサーバーの展開</span><span class="sxs-lookup"><span data-stu-id="ffda1-103">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffda1-104">_**トピックの最終更新日:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="ffda1-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="ffda1-105">弾性エンタープライズ Voip は、ブランチサイトの復元 (つまり、セントラルサイトへのリンクが利用できなくなった場合に、ブランチサイトのユーザーに継続的なエンタープライズ Voip サービスを提供する機能) を指します。</span><span class="sxs-lookup"><span data-stu-id="ffda1-105">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="ffda1-106">小規模および中規模のブランチサイト (25 ~ 1000 ユーザーのブランチサイト) では、存続可能 Branch Appliance を展開することをお勧めします。このアプライアンスは、組み込みの PSTN ゲートウェイまたは電話サービスプロバイダーへの SIP トランクを使用して、公衆交換電話網 (PSTN) 通話を終了します。</span><span class="sxs-lookup"><span data-stu-id="ffda1-106">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ffda1-107">存続可能 Branch Appliance は、Windows Server 2008 R2 オペレーティングシステム、Lync Server 2013 レジストラー、仲介サーバーソフトウェア、および PSTN ゲートウェイをすべて単一のアプライアンスシャーシに搭載するブレードサーバーを含むサードパーティ製のデバイスです。</span><span class="sxs-lookup"><span data-stu-id="ffda1-107">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="ffda1-108">1000 ~ 5000 ユーザーが存在し、回復可能な WAN がないブランチサイトでは、PSTN ゲートウェイまたは電話サービスプロバイダーへの SIP トランクのどちらかに接続された存続可能ブランチサーバーをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffda1-108">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ffda1-109">存続可能ブランチサーバーは、レジストラーと仲介サーバーソフトウェアがインストールされている Windows Server ベースのコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="ffda1-109">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ffda1-110">5000ユーザーと専用の Lync Server 管理者がいるブランチサイトでは、中央サイトとは別の完全な Lync Server 2013 の展開をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffda1-110">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="ffda1-111">前提条件と計画の考慮事項を含む、組織内のブランチサイトに最適な復元ソリューションを選択する方法の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 のブランチサイトの復元要件</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffda1-111">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ffda1-112">Lync Server 存続可能 Branch アプライアンスに所属しているユーザーは、新しいチャットルームを作成したり、既存のルームのルームカードを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ffda1-112">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ffda1-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ffda1-113">In This Section</span></span>

  - [<span data-ttu-id="ffda1-114">Lync Server 2013 を使用した存続可能ブランチアプライアンスまたはサーバーの展開-中央サイトのタスク</span><span class="sxs-lookup"><span data-stu-id="ffda1-114">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="ffda1-115">Lync Server 2013-ブランチサイトタスクを使用して存続可能ブランチアプライアンスまたはサーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="ffda1-115">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="ffda1-116">Lync Server 2013 でブランチサイトの復元のユーザーを構成する</span><span class="sxs-lookup"><span data-stu-id="ffda1-116">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="ffda1-117">Lync Server 2013 の存続可能ブランチアプライアンスまたはサーバー上のホームユーザー</span><span class="sxs-lookup"><span data-stu-id="ffda1-117">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="ffda1-118">付録: 存続可能 Branch アプライアンスおよび Lync Server 2013 のサーバー</span><span class="sxs-lookup"><span data-stu-id="ffda1-118">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ffda1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffda1-119">See Also</span></span>


[<span data-ttu-id="ffda1-120">Lync Server 2013 の展開 </span><span class="sxs-lookup"><span data-stu-id="ffda1-120">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

