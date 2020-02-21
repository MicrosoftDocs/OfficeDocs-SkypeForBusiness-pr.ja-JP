---
title: 'Lync Server 2013: 監視用のコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 072dbc882940bc0f28217bcf7c41663bf9ed3708
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="99adb-102">Lync Server 2013 で監視するためのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="99adb-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99adb-103">_**トピックの最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="99adb-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="99adb-104">ユニファイドデータ収集エージェントは各フロントエンドサーバーに自動的にインストールされ、アクティブ化されるため、監視サーバーとして動作するようにサーバーを構成する必要はありません。各フロントエンドサーバーは、既に監視サーバーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="99adb-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="99adb-105">ただし、監視データのバックエンドデータストアとして機能するデータベースをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99adb-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="99adb-106">Microsoft Lync Server 2013 では、監視用のバックエンドストアとして次のいずれかのデータベースを使用できます。</span><span class="sxs-lookup"><span data-stu-id="99adb-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="99adb-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="99adb-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="99adb-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="99adb-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="99adb-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="99adb-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="99adb-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="99adb-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="99adb-111">これらのデータベースの64ビット版を使用する必要があることに注意してください。32ビットバージョンの SQL Server を監視用のバックエンドストアとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="99adb-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="99adb-112">同様に、Lync Server 2013 では、SQL Server 2008 または SQL Server 2012 の Express Edition はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="99adb-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="99adb-113">Lync Server 2013 のデータベース要件の詳細については、「Lync server 2013 サポートガイド」の「 [Lync server 2013 のデータベースソフトウェアサポート](lync-server-2013-database-software-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99adb-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="99adb-114">監視を展開して構成する前に、SQL Server をインストールして構成しておく必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="99adb-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="99adb-115">ただし、SQL Server 自体を展開する必要はありません。事前に監視データベースをセットアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="99adb-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="99adb-116">その代わりに、Lync Server トポロジを公開すると、これらのデータベースが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="99adb-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="99adb-117">監視データは、SQL Server インスタンスを他の種類のデータと共有できます。</span><span class="sxs-lookup"><span data-stu-id="99adb-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="99adb-118">通常、通話詳細記録データベース (LcsCdr) と Qquality of Experience データベース (QoEMetrics) は同じ SQL インスタンスを共有します。また、2つの監視データベースがアーカイブデータベース (LcsLog) と同じ SQL インスタンスに存在することもよくあります。</span><span class="sxs-lookup"><span data-stu-id="99adb-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="99adb-119">SQL Server インスタンスに関する実際の要件については、SQL Server のいずれか1つのインスタンスが以下のように制限されます。</span><span class="sxs-lookup"><span data-stu-id="99adb-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="99adb-120">Lync Server 2013 バックエンドデータベースの1つのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="99adb-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="99adb-121">(一般的な規則として、監視データベースをバックエンドデータベースと同じ SQL インスタンスまたは同じコンピューター上に共存させることはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="99adb-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="99adb-122">技術的には可能ですが、バックエンドデータベースに必要な空きディスク領域を使用して監視データベースのリスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="99adb-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="99adb-123">呼び出し詳細記録データベースの1つのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="99adb-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="99adb-124">Qoe (Quality of Experience) データベースの1つのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="99adb-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="99adb-125">アーカイブデータベースの1つのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="99adb-125">One instance of the archiving database.</span></span>

<span data-ttu-id="99adb-126">つまり、1つの SQL Server インスタンスに LcsCdr データベースのインスタンスを2つ持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="99adb-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="99adb-127">LcsCdr データベースのインスタンスが複数必要な場合は、SQL Server の複数のインスタンスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99adb-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="99adb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="99adb-128">See Also</span></span>


[<span data-ttu-id="99adb-129">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="99adb-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

