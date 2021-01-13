---
title: Skype for Business Server で監視レポートをミラー データベースに関連付ける
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '概要: 監視レポートを Skype for Business Server で使用されるミラー データベースに関連付ける方法について学習します。'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802167"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="d8f25-103">Skype for Business Server で監視レポートをミラー データベースに関連付ける</span><span class="sxs-lookup"><span data-stu-id="d8f25-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="d8f25-104">**概要:** 監視レポートを Skype for Business Server で使用されるミラー データベースに関連付ける方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="d8f25-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="d8f25-105">ミラー データベースを使用してレポートを監視する</span><span class="sxs-lookup"><span data-stu-id="d8f25-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="d8f25-106">監視データベースのミラーを構成すると、フェールオーバーが発生した場合、そのミラー データベースがプライマリ データベースとして引き継がれします。</span><span class="sxs-lookup"><span data-stu-id="d8f25-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="d8f25-107">ただし、Skype for Business Server 監視レポートを使用してフェールオーバーが発生した場合は、監視レポートがミラー データベースに接続していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8f25-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="d8f25-108">これは、監視レポートをインストールするときに、プライマリ データベースの場所のみを指定するためです。ミラー データベースの場所を指定しない。</span><span class="sxs-lookup"><span data-stu-id="d8f25-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="d8f25-109">監視レポートをミラー データベースに自動的にフェールオーバーするには、監視レポートで使用される 2 つのデータベース (通話詳細記録データ用のデータベースと QoE (Quality of Experience) データ用のデータベース) にミラー データベースを "フェールオーバー パートナー" として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f25-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="d8f25-110">(この手順は、監視レポートのインストール後に実行する必要があります)。フェールオーバー パートナー情報を追加するには、これら 2 つのデータベースで使用される接続文字列の値を手動で編集します。</span><span class="sxs-lookup"><span data-stu-id="d8f25-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="d8f25-111">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8f25-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="d8f25-112">このInternet Explorer使用して、Reporting **Services SQL Serverページを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="d8f25-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="d8f25-113">Reporting Services ホーム ページの URL には、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8f25-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="d8f25-114">**http: プレフィックス**。</span><span class="sxs-lookup"><span data-stu-id="d8f25-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="d8f25-115">Reporting Services がインストールされているコンピューターの完全修飾ドメイン名 (FQDN) (例: **atl-sql-001.litwareinc.com)。**</span><span class="sxs-lookup"><span data-stu-id="d8f25-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="d8f25-116">The character string **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="d8f25-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="d8f25-117">監視レポートがインストールされているデータベース インスタンスの名前 **(archinst** など)。</span><span class="sxs-lookup"><span data-stu-id="d8f25-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="d8f25-118">たとえば、SQL Server Reporting Services がコンピューター atl-sql-001.litwareinc.com にインストールされ、監視レポートでデータベース インスタンス archinst が使用されている場合、ホーム ページの URL は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d8f25-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="d8f25-119">Reporting Services ホーム ページにアクセスしたら **、[ServerReports]** をクリックし、[レポート] **Reports_Content。**</span><span class="sxs-lookup"><span data-stu-id="d8f25-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="d8f25-120">そうすると、Skype for Business Server **Reports_Content** レポートのページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8f25-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="d8f25-121">[次 **Reports_Content** ページで **、CDRDB** データ ソースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8f25-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="d8f25-122">**CDRDB ページの**[プロパティ]**タブで、[** 接続文字列] というラベルの付いたテキスト ボックス **を探します**。</span><span class="sxs-lookup"><span data-stu-id="d8f25-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="d8f25-123">現在の接続文字列は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8f25-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="d8f25-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="d8f25-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="d8f25-125">接続文字列を編集して、ミラー データベースのサーバー名とデータベース インスタンスを含める。</span><span class="sxs-lookup"><span data-stu-id="d8f25-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="d8f25-126">たとえば、サーバーの名前が atl-mirror-001 で、ミラー データベースが archinst インスタンス内にある場合は、次の構文を使用してミラー データベースを指定するために追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f25-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="d8f25-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="d8f25-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="d8f25-128">編集した接続文字列は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8f25-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="d8f25-129">Data source=(local)\archinst;フェールオーバー パートナー=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="d8f25-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="d8f25-130">接続文字列を更新した後、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d8f25-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="d8f25-131">**CDRDB ページで**、次のリンク **Reports_Content** クリックします。</span><span class="sxs-lookup"><span data-stu-id="d8f25-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="d8f25-132">**[QOSDB データ** ソース] をクリックし、QoE データベースの接続文字列を編集します。</span><span class="sxs-lookup"><span data-stu-id="d8f25-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="d8f25-133">例:</span><span class="sxs-lookup"><span data-stu-id="d8f25-133">For example:</span></span>
    
    <span data-ttu-id="d8f25-134">Data source=(local)\archinst;フェールオーバー パートナー=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="d8f25-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="d8f25-135">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8f25-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d8f25-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8f25-136">See also</span></span>

[<span data-ttu-id="d8f25-137">Skype for Business Server での監視レポートのインストール</span><span class="sxs-lookup"><span data-stu-id="d8f25-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="d8f25-138">Skype for Business Server での監視レポートの使用</span><span class="sxs-lookup"><span data-stu-id="d8f25-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
