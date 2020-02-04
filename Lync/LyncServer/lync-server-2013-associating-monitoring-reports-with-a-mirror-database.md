---
title: 'Lync Server 2013: ミラーデータベースとの監視レポートの関連付け'
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
ms.openlocfilehash: 93e5f10e3e4bd3c063cafcb2fd984098482ebf22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="ab29a-102">Lync Server 2013 でのミラーデータベースと監視レポートの関連付け</span><span class="sxs-lookup"><span data-stu-id="ab29a-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab29a-103">_**最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="ab29a-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="ab29a-104">監視データベースのミラーを構成してあると、フェイルオーバーが発生した場合にそのミラー データベースがプライマリ データベースを引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="ab29a-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="ab29a-105">ただし、Lync Server Monitoring レポートを使用してフェールオーバーが発生した場合は、監視レポートがミラーデータベースに接続されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab29a-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="ab29a-106">これは、監視レポートをインストールするときにプライマリ データベースの場所だけを指定し、ミラー データベースの場所を指定していないためです。</span><span class="sxs-lookup"><span data-stu-id="ab29a-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="ab29a-p102">監視レポートがミラー データベースに自動的にフェイルオーバーされるようにするには、監視レポートが使う 2 つのデータベース (通話詳細記録データ用のデータベースと Quality of Experience (QoE) データ用のデータベース) に、ミラー データベースを "フェイルオーバー パートナー" として追加する必要があります (この手順は、監視レポートをインストールした後で実行する必要があります)。フェイルオーバー パートナー情報は、2 つのデータベースが使用する接続文字列の値を手動で編集することで追加できます。この操作を行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ab29a-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="ab29a-p103">Internet Explorer を使って **SQL Server Reporting Services** のホーム ページを開きます。Reporting Services のホーム ページの URL には、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab29a-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="ab29a-112">プレフィックス **http:**。</span><span class="sxs-lookup"><span data-stu-id="ab29a-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="ab29a-113">Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (**atl-sql-001.litwareinc.com** など)。</span><span class="sxs-lookup"><span data-stu-id="ab29a-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="ab29a-114">文字列 **/レポート\_**。</span><span class="sxs-lookup"><span data-stu-id="ab29a-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="ab29a-115">監視レポートがインストールされているデータベース インスタンスの名前 (**archinst** など)。</span><span class="sxs-lookup"><span data-stu-id="ab29a-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="ab29a-116">たとえば、SQL Server Reporting Services がコンピューター atl-sql-001.litwareinc.com にインストールされており、監視レポートでデータベース インスタンス archinst が使われている場合、ホーム ページの URL は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ab29a-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="ab29a-117">Reporting Services のホームページにアクセスしたら、[ **LyncServerReports**] をクリックし、[**レポート\_のコンテンツ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab29a-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="ab29a-118">この操作を行うと、Lync Server Monitoring レポートの [**レポート\_のコンテンツ**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab29a-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="ab29a-119">[**レポート\_のコンテンツ**] ページで、 **cdrdb**データソースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab29a-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="ab29a-p105">[**CDRDB**] ページの [**プロパティ**] タブで、[**接続文字列**] というテキスト ボックスを探します。現在の接続文字列は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab29a-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="ab29a-122">**データソース = (ローカル)\\アーキテクチャ inst; 最初のカタログ = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="ab29a-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="ab29a-p106">接続文字列を編集して、ミラー データベースのサーバー名とデータベース インスタンスを含めます。たとえば、サーバーの名前が atl-mirror-001 でミラー データベースが archinst インスタンスにある場合、次の構文を使ってミラー データベースを追加および指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab29a-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="ab29a-125">**フェールオーバーパートナー = atl-mirror-\\001: inst**</span><span class="sxs-lookup"><span data-stu-id="ab29a-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="ab29a-126">編集された接続文字列は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ab29a-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="ab29a-127">**データソース = (ローカル)\\アーキテクチャ instフェールオーバーパートナー = atl-ミラー-\\001: inst; 初期カタログ = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="ab29a-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="ab29a-128">接続文字列を更新したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab29a-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="ab29a-129">[ **Cdrdb** ] ページで、[**レポート\_コンテンツ**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab29a-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="ab29a-130">[**QMSDB**] データ ソースをクリックして、QoE データベースの接続文字列を編集します。</span><span class="sxs-lookup"><span data-stu-id="ab29a-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="ab29a-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ab29a-131">For example:</span></span>
    
    <span data-ttu-id="ab29a-132">**データソース = (ローカル)\\アーキテクチャ instフェールオーバーパートナー = atl-mirror-\\001: inst、initial Catalog = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="ab29a-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="ab29a-133">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab29a-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ab29a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab29a-134">See Also</span></span>


[<span data-ttu-id="ab29a-135">Lync Server 2013 監視レポートをインストールする</span><span class="sxs-lookup"><span data-stu-id="ab29a-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="ab29a-136">Lync Server 2013 で監視レポートを使用する</span><span class="sxs-lookup"><span data-stu-id="ab29a-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

