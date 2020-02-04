---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたはサーバーの展開'
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
ms.openlocfilehash: ca6fae79854356951701eaf6040fb436e787acd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="02cc5-102">Lync Server 2013 を使用した存続可能ブランチ アプライアンスまたはサーバーの展開</span><span class="sxs-lookup"><span data-stu-id="02cc5-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02cc5-103">_**最終更新日:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="02cc5-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="02cc5-104">耐障害性のあるエンタープライズボイスとは、ブランチサイトの回復性 (セントラルサイトへのリンクが利用できなくなった場合に、継続的なエンタープライズボイスサービスを提供して、サイトのユーザーをブランチサイトユーザーに提供することを意味します)。</span><span class="sxs-lookup"><span data-stu-id="02cc5-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="02cc5-105">小規模または中規模のブランチサイト (25 ~ 1000 ユーザーの支店) の場合は、Survivable Branch Appliance を導入することをお勧めします。このアプライアンスは、内蔵の PSTN ゲートウェイまたは SIP トランクを電話に接続することで、公衆交換電話網 (PSTN) 通話を終了します。サービスプロバイダ。</span><span class="sxs-lookup"><span data-stu-id="02cc5-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="02cc5-106">Survivable Branch Appliance は、Windows Server 2008 R2 オペレーティングシステムを実行しているブレードサーバー、Lync Server 2013 レジストラー、仲介サーバーソフトウェア、PSTN ゲートウェイがすべて1つのアプライアンスシャーシに含まれているサードパーティ製のデバイスです。</span><span class="sxs-lookup"><span data-stu-id="02cc5-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="02cc5-107">1000 5000 を使用している支社と、回復できる WAN がないブランチサイトの場合は、PSTN ゲートウェイまたは電話サービスプロバイダーへの SIP トランクのどちらかに接続された Survivable Branch Server をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02cc5-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="02cc5-108">Survivable Branch Server は、レジストラーと仲介サーバーソフトウェアがインストールされている Windows Server ベースのコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="02cc5-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02cc5-109">5000ユーザーと専用の Lync Server 管理者がいる支店サイトの場合は、中央サイトとは別の Lync Server 2013 の展開をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02cc5-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="02cc5-110">組織内のブランチサイトに最適な復元策を選択する方法について詳しくは、「計画のための前提条件と計画の考慮事項」を参照して<A href="lync-server-2013-branch-site-resiliency-requirements.md">2013</A>ください。</span><span class="sxs-lookup"><span data-stu-id="02cc5-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="02cc5-111">Lync Server Survivable Branch Appliance をホームとして使用しているユーザーは、新しいチャットルームを作成したり、既存のルームの会議室カードを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="02cc5-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02cc5-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="02cc5-112">In This Section</span></span>

  - [<span data-ttu-id="02cc5-113">Lync Server 2013 による存続可能ブランチ アプライアンスまたはサーバーの展開 - 中央サイトのタスク</span><span class="sxs-lookup"><span data-stu-id="02cc5-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="02cc5-114">Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの展開 - ブランチ サイトのタスク</span><span class="sxs-lookup"><span data-stu-id="02cc5-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="02cc5-115">Lync Server 2013 でブランチ サイト復元を実現するためのユーザーの構成</span><span class="sxs-lookup"><span data-stu-id="02cc5-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="02cc5-116">Lync Server 2013 で存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる</span><span class="sxs-lookup"><span data-stu-id="02cc5-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="02cc5-117">付録: Lync Server 2013 の存続可能ブランチ アプライアンスとサーバー</span><span class="sxs-lookup"><span data-stu-id="02cc5-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02cc5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="02cc5-118">See Also</span></span>


[<span data-ttu-id="02cc5-119">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="02cc5-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

