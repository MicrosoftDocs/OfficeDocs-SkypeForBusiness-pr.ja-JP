---
title: 'Lync Server 2013: 新しい障害復旧および高可用性機能'
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
ms.openlocfilehash: 366b58f05e8567659dc630042494f1ede25cf338
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="498c2-102">Lync Server 2013 の新しい障害復旧および高可用性機能</span><span class="sxs-lookup"><span data-stu-id="498c2-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="498c2-103">_**トピックの最終更新日:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="498c2-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="498c2-104">Lync Server 2010 の場合と同様に、Lync Server 2013 の主な高可用性 (HA) スキームは、プーリングによるサーバーの冗長性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="498c2-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="498c2-105">あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="498c2-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="498c2-106">これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="498c2-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="498c2-107">Lync Server 2013 は、2つのデータセンターにあるフロントエンドプールをペアにすることによって、新しい障害復旧手段を追加します。</span><span class="sxs-lookup"><span data-stu-id="498c2-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="498c2-108">ペアになっているプールのいずれかがダウンすると、管理者はそのプールのユーザーをペアの他のプールにフェールオーバーして、サービスの継続を提供できます。</span><span class="sxs-lookup"><span data-stu-id="498c2-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="498c2-109">この機能には、記憶域ネットワークや共有ディスクなど、高価なネットワークやハードウェアソリューションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="498c2-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="498c2-110">Lync Server 2013 では、バックエンドサーバーの高可用性も追加されます。</span><span class="sxs-lookup"><span data-stu-id="498c2-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="498c2-111">これは、フロントエンドプール用に2台のバックエンドサーバーを展開し、バックエンドサーバーで実行されているすべての Lync データベースの同期 SQL ミラーリングをセットアップするオプションのトポロジです。</span><span class="sxs-lookup"><span data-stu-id="498c2-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="498c2-112">ミラーの監視を展開するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="498c2-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="498c2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="498c2-113">See Also</span></span>


[<span data-ttu-id="498c2-114">Lync Server 2013 での高可用性および障害復旧の計画</span><span class="sxs-lookup"><span data-stu-id="498c2-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

