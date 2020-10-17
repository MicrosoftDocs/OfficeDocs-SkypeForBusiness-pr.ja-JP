---
title: 'Lync Server 2013: 監視レポートとミラーデータベースの関連付け'
description: 'Lync Server 2013: 監視レポートとミラーデータベースの関連付け。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64b37901e7939b5e904dec73caac2d3483e2d71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568803"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="9fa28-103">Lync Server 2013 での監視レポートとミラーデータベースの関連付け</span><span class="sxs-lookup"><span data-stu-id="9fa28-103">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fa28-104">_**トピックの最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="9fa28-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="9fa28-105">監視データベースのミラーを構成すると、フェールオーバーが発生した場合に、ミラーデータベースがプライマリデータベースとして引き継がれます。</span><span class="sxs-lookup"><span data-stu-id="9fa28-105">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="9fa28-106">ただし、Lync Server の監視レポートを使用し、フェールオーバーが発生した場合は、監視レポートがミラーデータベースに接続されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9fa28-106">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="9fa28-107">これは、監視レポートをインストールするときに、プライマリデータベースの場所のみを指定するからです。ミラーデータベースの場所を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9fa28-107">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="9fa28-108">ミラーデータベースに自動的にフェールオーバーするように監視レポートを取得するには、監視レポートで使用される2つのデータベースに対してミラーデータベースを "フェールオーバーパートナー" として追加する必要があります (1 つは通話詳細レコードデータ用、もう1つは QoE (Quality of Experience) データ)。</span><span class="sxs-lookup"><span data-stu-id="9fa28-108">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="9fa28-109">(この手順は、監視レポートをインストールした後に実行する必要があります。)フェールオーバーパートナー情報を追加するには、これら2つのデータベースで使用される接続文字列値を手動で編集します。</span><span class="sxs-lookup"><span data-stu-id="9fa28-109">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="9fa28-110">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9fa28-110">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="9fa28-111">Internet Explorer を使用して、 **SQL Server Reporting Services** のホームページを開きます。</span><span class="sxs-lookup"><span data-stu-id="9fa28-111">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="9fa28-112">Reporting Services のホームページの URL には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9fa28-112">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="9fa28-113">**Http:** プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="9fa28-113">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="9fa28-114">Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (たとえば、 **atl-sql-001.litwareinc.com**)。</span><span class="sxs-lookup"><span data-stu-id="9fa28-114">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="9fa28-115">文字列 \*\*/レポート \_ \*\*。</span><span class="sxs-lookup"><span data-stu-id="9fa28-115">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="9fa28-116">監視レポートがインストールされているデータベースインスタンスの名前 (例: **arch inst**)。</span><span class="sxs-lookup"><span data-stu-id="9fa28-116">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="9fa28-117">たとえば、コンピューター atl-sql-001.litwareinc.com に SQL Server Reporting Services がインストールされており、監視レポートでデータベースインスタンスアーキテクチャを使用している場合、ホームページの URL は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9fa28-117">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="9fa28-118">Reporting Services のホームページにアクセスした後、[ **LyncServerReports**] をクリックしてから、[ **レポートの \_ コンテンツ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fa28-118">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="9fa28-119">これにより、Lync Server 監視レポートの [ **レポートの \_ コンテンツ** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9fa28-119">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="9fa28-120">[ **レポートの \_ コンテンツ** ] ページで、 **cdrdb** データソースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fa28-120">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="9fa28-121">**Cdrdb**ページの [**プロパティ**] タブで、[**接続文字列**] というラベルのテキストボックスを検索します。</span><span class="sxs-lookup"><span data-stu-id="9fa28-121">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="9fa28-122">現在の接続文字列は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9fa28-122">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="9fa28-123">**データソース = (ローカル) \\ アーキテクチャ inst; 最初のカタログ = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="9fa28-123">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="9fa28-124">接続文字列を編集して、ミラーデータベースのサーバー名とデータベースインスタンスを含めます。</span><span class="sxs-lookup"><span data-stu-id="9fa28-124">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="9fa28-125">たとえば、サーバーが atl-ws-01 という名前で、ミラーデータベースが arch inst インスタンス内にある場合は、次の構文を使用してミラーデータベースを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fa28-125">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="9fa28-126">**フェールオーバーパートナー = atl-ミラー- \\ 001**</span><span class="sxs-lookup"><span data-stu-id="9fa28-126">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="9fa28-127">編集された接続文字列は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9fa28-127">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="9fa28-128">**データソース = (ローカル) \\ アーキテクチャ instフェールオーバーパートナー = atl-ミラー-001、 \\ 初期カタログ = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="9fa28-128">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="9fa28-129">接続文字列を更新した後、[ **適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fa28-129">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="9fa28-130">[ **Cdrdb** ] ページで、[ **レポート \_ コンテンツ** ] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fa28-130">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="9fa28-131">**Qmsdb**データソースをクリックし、qmsdb データベースの接続文字列を編集します。</span><span class="sxs-lookup"><span data-stu-id="9fa28-131">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="9fa28-132">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9fa28-132">For example:</span></span>
    
    <span data-ttu-id="9fa28-133">**データソース = (ローカル) \\ アーキテクチャ instフェールオーバーパートナー = atl-ミラー-001 ( \\ 初期カタログ = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="9fa28-133">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="9fa28-134">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fa28-134">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9fa28-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fa28-135">See Also</span></span>


[<span data-ttu-id="9fa28-136">Lync Server 2013 監視レポートのインストール</span><span class="sxs-lookup"><span data-stu-id="9fa28-136">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="9fa28-137">Lync Server 2013 での監視レポートの使用</span><span class="sxs-lookup"><span data-stu-id="9fa28-137">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

