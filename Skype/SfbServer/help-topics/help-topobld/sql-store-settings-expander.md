---
title: SQL ストア設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: SQL Server データベースのプロパティを編集するには、SQL Server データベースインスタンスを変更する必要があります。 [プロパティの編集] ダイアログボックスを使用して、アーカイブサーバーデータベースを別のコンピューターに移動するなどのタスクを実行することはできません。 さらに、[プロパティの編集] ダイアログボックスを使って、中央管理ストアをホストする SQL Server のインスタンスを変更することはできません。
ms.openlocfilehash: 5119159c782e4d27b47d9759ff7b75323b9992fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291208"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="1a97b-105">SQL ストア設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="1a97b-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="1a97b-106">SQL Server データベースのプロパティを編集するには、SQL Server データベースインスタンスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a97b-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="1a97b-107">[**プロパティの編集**] ダイアログボックスを使用して、アーカイブサーバーデータベースを別のコンピューターに移動するなどのタスクを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a97b-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="1a97b-108">さらに、[**プロパティの編集**] ダイアログボックスを使って、中央管理ストアをホストする SQL Server のインスタンスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a97b-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="1a97b-109">SQL Server データベースのプロパティを編集する</span><span class="sxs-lookup"><span data-stu-id="1a97b-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="1a97b-110">サーバーの全体管理ストア以外のデータベースによって使用される SQL Server のインスタンスを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a97b-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="1a97b-111">SQL Server のインスタンスを変更するには</span><span class="sxs-lookup"><span data-stu-id="1a97b-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="1a97b-112">[ **SQL ストア**] ノードで適切なデータベースを選択し、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a97b-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="1a97b-113">[**プロパティの編集**] ダイアログボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1a97b-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="1a97b-114">既定の SQL Server インスタンスを使用するには、[**既定のインスタンス**] を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a97b-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="1a97b-115">名前付きのデータベースインスタンスを使用するには、[**名前付きインスタンス**] を選択し、テキストボックスにインスタンス名を入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a97b-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="1a97b-116">SQL Server のパス全体ではなく、インスタンス名だけを入力する必要があります (たとえば、ArchivingInstance)。</span><span class="sxs-lookup"><span data-stu-id="1a97b-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="1a97b-117">[**プロパティの編集**] ダイアログボックスで作業している場合、トポロジビルダーは、入力したデータベースインスタンスが有効なインスタンスであることを確認しません。</span><span class="sxs-lookup"><span data-stu-id="1a97b-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="1a97b-118">たとえば、誤ってインスタンス名として typeArchivingInstanec して [ **OK]** をクリックした場合、トポロジビルダーは無効なインスタンスを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="1a97b-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="1a97b-119">このトポロジを公開する前に、この間違いを修正する必要があります。 SQL Server インスタンスが見つからない場合は、トポロジビルダーでそのインスタンスが作成されることはありません。</span><span class="sxs-lookup"><span data-stu-id="1a97b-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

