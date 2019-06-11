---
title: 'Lync Server 2013: 監視のためのコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0c848b3c404bc9bce3b54d6ed52157d1b9da679
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="6ad6e-102">Lync Server 2013 における監視のためのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="6ad6e-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ad6e-103">_**最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="6ad6e-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="6ad6e-104">統合データ収集エージェントは、各フロントエンドサーバーに自動的にインストールされてアクティブ化されるため、監視サーバーとして動作するようにサーバーを構成する必要はありません。各フロントエンドサーバーは、既に監視サーバーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="6ad6e-105">ただし、監視データのバックエンドデータストアとして機能するようにデータベースをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="6ad6e-106">Microsoft Lync Server 2013 では、監視のバックエンドストアとして次のデータベースのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="6ad6e-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="6ad6e-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="6ad6e-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6ad6e-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="6ad6e-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="6ad6e-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="6ad6e-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6ad6e-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="6ad6e-111">これらのデータベースの64ビット版を使用する必要があることに注意してください。32ビットバージョンの SQL Server は、監視用のバックエンドストアとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="6ad6e-112">同様に、Lync Server 2013 は、SQL Server 2008 または SQL Server 2012 の Express エディションをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="6ad6e-113">Lync Server 2013 のデータベース要件の詳細については、「lync Server 2013 サポートガイド」の「 [Lync server 2013 でのデータベースソフトウェアのサポート](lync-server-2013-database-software-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="6ad6e-114">監視を展開して構成する前に、SQL Server をインストールして構成する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="6ad6e-115">ただし、SQL Server 自体のみを展開する必要があります。事前に監視データベースを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="6ad6e-116">代わりに、Lync Server トポロジを公開すると、これらのデータベースが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="6ad6e-p104">監視データと他の種類のデータで 1 つの SQL Server インスタンスを共有することができます。一般には、通話詳細記録データベース (LcsCdr) と Quality of Experience データベース (QoEMetrics) で同じ SQL インスタンスを共有します。また、2 つの監視データベースを、アーカイブ データベース (LcsLog) として同じ SQL インスタンスに配置するのも一般的です。SQL Server インスタンスに関する実際の唯一の要件は、SQL Server のどのインスタンスについても、次の制限が設けられることです。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-p104">Monitoring data can share a SQL Server instance with other types of data. Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog). About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="6ad6e-120">Lync Server 2013 バックエンドデータベースの1つのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="6ad6e-121">(一般的な規則として、監視データベースを同一の SQL インスタンスまたは同じコンピューター上のバックエンドデータベースとの間で併置することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="6ad6e-122">技術的には可能ですが、バックエンドデータベースに必要なディスク領域を使用して、監視データベースのリスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="6ad6e-123">通話詳細記録データベースは 1 インスタンス。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="6ad6e-124">Quality of Experience データベースは 1 インスタンス。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="6ad6e-125">アーカイブ データベースは 1 インスタンス。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-125">One instance of the archiving database.</span></span>

<span data-ttu-id="6ad6e-126">つまり、同じ SQL Server の同じインスタンス内に、複数の LcsCdr データベースのインスタンスを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="6ad6e-127">LcsCdr データベースの複数のインスタンスが必要な場合は、SQL Server の複数のインスタンスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ad6e-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6ad6e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ad6e-128">See Also</span></span>


[<span data-ttu-id="6ad6e-129">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="6ad6e-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

