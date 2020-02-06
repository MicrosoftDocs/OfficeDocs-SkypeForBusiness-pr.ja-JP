---
title: Skype for Business Server のミラーデータベースに監視レポートを関連付ける
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '概要: Skype for Business Server で使用されているミラーデータベースに監視レポートを関連付ける方法について説明します。'
ms.openlocfilehash: 77e852860239ae6f87fce2b49fb6fa9f9d7c0834
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41789935"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="15367-103">Skype for Business Server のミラーデータベースに監視レポートを関連付ける</span><span class="sxs-lookup"><span data-stu-id="15367-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="15367-104">**概要:** Skype for Business Server で使用されているミラーデータベースで監視レポートを関連付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15367-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="15367-105">ミラー データベースを使用する監視レポート</span><span class="sxs-lookup"><span data-stu-id="15367-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="15367-106">監視データベースのミラーを構成してあると、フェイルオーバーが発生した場合にそのミラー データベースがプライマリ データベースを引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="15367-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="15367-107">ただし、Skype for Business Server Monitoring レポートを使用してフェールオーバーが発生した場合は、監視レポートがミラーデータベースに接続されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="15367-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="15367-108">これは、監視レポートをインストールするときにプライマリ データベースの場所だけを指定し、ミラー データベースの場所を指定していないためです。</span><span class="sxs-lookup"><span data-stu-id="15367-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="15367-p102">監視レポートがミラー データベースに自動的にフェイルオーバーされるようにするには、監視レポートが使う 2 つのデータベース (通話詳細記録データ用のデータベースと Quality of Experience (QoE) データ用のデータベース) に、ミラー データベースを "フェイルオーバー パートナー" として追加する必要があります (この手順は、監視レポートをインストールした後で実行する必要があります)。フェイルオーバー パートナー情報は、2 つのデータベースが使用する接続文字列の値を手動で編集することで追加できます。この操作を行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="15367-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="15367-p103">Internet Explorer を使って **SQL Server Reporting Services** のホーム ページを開きます。Reporting Services のホーム ページの URL には、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="15367-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="15367-114">プレフィックス **http:**。</span><span class="sxs-lookup"><span data-stu-id="15367-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="15367-115">Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (**atl-sql-001.litwareinc.com** など)。</span><span class="sxs-lookup"><span data-stu-id="15367-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="15367-116">文字列 **/Reports_**。</span><span class="sxs-lookup"><span data-stu-id="15367-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="15367-117">監視レポートがインストールされているデータベース インスタンスの名前 (**archinst** など)。</span><span class="sxs-lookup"><span data-stu-id="15367-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="15367-118">たとえば、SQL Server Reporting Services がコンピューター atl-sql-001.litwareinc.com にインストールされており、監視レポートでデータベース インスタンス archinst が使われている場合、ホーム ページの URL は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="15367-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="15367-119">Reporting Services ホーム ページにアクセスしたら、[**ServerReports**]、[**Reports_Content**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="15367-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="15367-120">これにより、Skype for Business Server Monitoring レポートの [ **Reports_Content** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="15367-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="15367-121">[**Reports_Content**] ページで、[**CDRDB**] データ ソースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15367-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="15367-p105">[**CDRDB**] ページの [**プロパティ**] タブで、[**接続文字列**] というテキスト ボックスを探します。現在の接続文字列は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15367-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="15367-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="15367-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="15367-p106">接続文字列を編集して、ミラー データベースのサーバー名とデータベース インスタンスを含めます。たとえば、サーバーの名前が atl-mirror-001 でミラー データベースが archinst インスタンスにある場合、次の構文を使ってミラー データベースを追加および指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15367-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="15367-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="15367-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="15367-128">編集された接続文字列は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="15367-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="15367-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="15367-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="15367-130">接続文字列を更新したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15367-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="15367-p107">[**CDRDB**] ページで、[**Reports_Content**] をクリックします。[**QMSDB**] データ ソースをクリックして、QoE データベースの接続文字列を編集します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="15367-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="15367-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="15367-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="15367-135">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15367-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="15367-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="15367-136">See also</span></span>

[<span data-ttu-id="15367-137">Skype for Business Server で監視レポートをインストールする</span><span class="sxs-lookup"><span data-stu-id="15367-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="15367-138">Skype for Business Server で監視レポートを使用する</span><span class="sxs-lookup"><span data-stu-id="15367-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
