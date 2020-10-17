---
title: Lync Server 2013 会議の負荷分散
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f7b2d759ec9370bbf7eeeb2844edd3511ba0f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499204"
---
# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="7a60f-102">Lync Server 2013 での会議の負荷分散</span><span class="sxs-lookup"><span data-stu-id="7a60f-102">Conferencing load distribution in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a60f-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7a60f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7a60f-104">その他の専用会議ソリューションとは異なり、Lync Server アーキテクチャは共有ハードウェアモデルです。</span><span class="sxs-lookup"><span data-stu-id="7a60f-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="7a60f-105">つまり、それぞれ異なるリアルタイム通信をサポートする多数のソフトウェア コンポーネントが同じハードウェアを共有します。</span><span class="sxs-lookup"><span data-stu-id="7a60f-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="7a60f-106">各種リアルタイム通信によって、サーバーに一定の負荷がかかります。</span><span class="sxs-lookup"><span data-stu-id="7a60f-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="7a60f-107">たとえば、フロントエンドサーバーでは、セッション開始プロトコル (SIP) ルーティングコンポーネント、web アプリケーション (アドレス帳検索など)、Web 会議サービス、音声ビデオ会議サービス、エンタープライズ Voip アプリケーション (会議アテンダントアプリケーションや応答グループアプリケーションなど)、仲介サーバーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7a60f-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="7a60f-108">フロントエンドサーバー上のデータベースのセットは、ユーザー、連絡先、プレゼンス、会議、音声ルーティングデータの格納と処理も行います。</span><span class="sxs-lookup"><span data-stu-id="7a60f-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="7a60f-109">このハードウェア共有により、コンポーネント、サービス、プロセスの間で CPU リソースとメモリ リソースの競合が発生するので、電話会議ワークロード以外のワークロードがサーバーの拡張に直接影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="7a60f-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="7a60f-110">他のハードウェアポートベースの電話会議ソリューションと比較して、Lync Server 会議アーキテクチャは予約なしモデルです。</span><span class="sxs-lookup"><span data-stu-id="7a60f-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="7a60f-111">ユーザーが会議をスケジュールすると、Lync Server は会議データベースにレコードを作成しますが、会議データを保存しますが、スケジュールされた会議のハードウェアリソースは事前に予約しません。</span><span class="sxs-lookup"><span data-stu-id="7a60f-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="7a60f-112">代わりに、Lync Server には負荷分散ロジックが組み込まれており、プール内のすべてのフロントエンドサーバー間で負荷が均等に分散されるように、フロントエンドサーバーに電話会議リソースを動的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7a60f-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="7a60f-113">これにより、ハードウェア リソースが効果的にプロビジョニングされて使用されますが、大規模な会議 (特に、適切に計画されていない大規模な会議) のサポートが困難になります。</span><span class="sxs-lookup"><span data-stu-id="7a60f-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="7a60f-114">たとえば、Lync Server 2013 プールが最上位の容量に近い時間に稼働している場合、各フロントエンドサーバーは約125の平均サイズの会議をホストすることがあります。</span><span class="sxs-lookup"><span data-stu-id="7a60f-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="7a60f-115">別の小規模な会議を追加しても問題はありませんが、フロントエンドサーバーが他の125会議と同時にこのような大規模な会議をサポートすることができない可能性があるため、1000ユーザーの会議を追加することは問題になります。</span><span class="sxs-lookup"><span data-stu-id="7a60f-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

