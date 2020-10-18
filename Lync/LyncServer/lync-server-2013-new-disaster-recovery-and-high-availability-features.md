---
title: 'Lync Server 2013: 新しい障害復旧および高可用性機能'
description: 'Lync Server 2013: 新しい障害復旧および高可用性機能。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92816f61b66d9eed76c16286aaa6c7392dca7708
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578863"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="1401d-103">Lync Server 2013 の新しい障害復旧および高可用性機能</span><span class="sxs-lookup"><span data-stu-id="1401d-103">New disaster recovery and high availability features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1401d-104">_**トピックの最終更新日:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="1401d-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="1401d-105">Lync Server 2010 の場合と同様に、Lync Server 2013 の主な高可用性 (HA) スキームは、プーリングによるサーバーの冗長性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="1401d-105">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="1401d-106">あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="1401d-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="1401d-107">これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1401d-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="1401d-108">Lync Server 2013 は、2つのデータセンターにあるフロントエンドプールをペアにすることによって、新しい障害復旧手段を追加します。</span><span class="sxs-lookup"><span data-stu-id="1401d-108">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="1401d-109">ペアになっているプールのいずれかがダウンすると、管理者はそのプールのユーザーをペアの他のプールにフェールオーバーして、サービスの継続を提供できます。</span><span class="sxs-lookup"><span data-stu-id="1401d-109">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="1401d-110">この機能には、記憶域ネットワークや共有ディスクなど、高価なネットワークやハードウェアソリューションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1401d-110">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="1401d-111">Lync Server 2013 では、バックエンドサーバーの高可用性も追加されます。</span><span class="sxs-lookup"><span data-stu-id="1401d-111">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="1401d-112">これは、フロントエンドプール用に2台のバックエンドサーバーを展開し、バックエンドサーバーで実行されているすべての Lync データベースの同期 SQL ミラーリングをセットアップするオプションのトポロジです。</span><span class="sxs-lookup"><span data-stu-id="1401d-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="1401d-113">ミラーの監視を展開するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1401d-113">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1401d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1401d-114">See Also</span></span>


[<span data-ttu-id="1401d-115">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="1401d-115">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

