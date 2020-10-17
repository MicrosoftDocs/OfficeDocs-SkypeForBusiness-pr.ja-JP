---
title: 'Lync Server 2013: 展開の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3600df130f0159df0945edb25d72059bb4bcb8a9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522664"
---
# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="d067b-102">Lync Server 2013 の展開の概要</span><span class="sxs-lookup"><span data-stu-id="d067b-102">Deployment overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d067b-103">_**トピックの最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="d067b-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="d067b-104">Lync Server 2013 Enterprise Edition と Lync Server 2013 Standard Edition の主な違いは、Standard Edition は Enterprise Edition に含まれる高可用性機能をサポートしていないことです。</span><span class="sxs-lookup"><span data-stu-id="d067b-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="d067b-105">高可用性を実現するには、複数のフロントエンドサーバーをプールに展開し、SQL Server を実行しているサーバーをミラー化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d067b-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="d067b-106">Enterprise Edition では、スタンドアロンの仲介サーバーを併置するか、定義するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d067b-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="d067b-107">監視サーバーとアーカイブサーバーは、SQL Server を実行しているスタンドアロンサーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d067b-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="d067b-108">または、フロントエンドサーバーおよびプールのデータベースサーバー上で実行されている SQL Server のインスタンスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="d067b-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="d067b-109">Lync Server 2013 Standard Edition を実行しているサーバーは、組織の主要展開から地理的に削除された小規模な組織とリモートの場所を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d067b-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="d067b-110">障害が発生した場合にフェールオーバーに使用する2つの Standard Edition サーバーサーバーは、最大5000ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="d067b-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="d067b-111">Enterprise Edition のフロントエンドサーバーと同様に、Standard Edition サーバーをプールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d067b-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="d067b-112">また、Standard Edition が使用する SQL Server データベースは、SQL Server Express を実行する併置されたサーバーであり、Standard Edition サーバーのワークロードを処理するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="d067b-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="d067b-113">これは、すべての役割が Standard Edition サーバー上に存在する必要があるということではありません。</span><span class="sxs-lookup"><span data-stu-id="d067b-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="d067b-114">スタンドアロンの仲介サーバーとエッジサーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d067b-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="d067b-115">中央管理ストアの SQL Server データベース、および Lync Server 2013 のための目的は、SQL Server を実行しているサーバーに併置された Standard Edition サーバー上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d067b-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="d067b-116">監視サーバーとアーカイブサーバーは、スタンドアロンサーバーと SQL Server データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="d067b-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

