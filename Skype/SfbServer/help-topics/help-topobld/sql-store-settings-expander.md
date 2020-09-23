---
title: SQL ストア設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: SQL Server データベースのプロパティを編集するには、SQL Server データベースのインスタンスを変更する必要があります。 [プロパティの編集] ダイアログ ボックスで、アーカイブ サーバー データベースをコンピューター間で移動するなどのタスクを実行することはできません。 さらに、[プロパティの編集] ダイアログボックスを使用して、中央管理ストアをホストする SQL Server のインスタンスを変更することはできません。
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219612"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="0008b-105">SQL ストア設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="0008b-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="0008b-106">SQL Server データベースのプロパティを編集するには、SQL Server データベースのインスタンスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0008b-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="0008b-107">[**プロパティの編集**] ダイアログ ボックスで、アーカイブ サーバー データベースをコンピューター間で移動するなどのタスクを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="0008b-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="0008b-108">さらに、[ **プロパティの編集** ] ダイアログボックスを使用して、中央管理ストアをホストする SQL Server のインスタンスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0008b-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="0008b-109">SQL Server データベースのプロパティを編集する</span><span class="sxs-lookup"><span data-stu-id="0008b-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="0008b-110">中央管理ストア以外のデータベースで使用されている SQL Server のインスタンスを変更するには、トポロジビルダーで以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0008b-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="0008b-111">SQL Server のインスタンスを変更するには</span><span class="sxs-lookup"><span data-stu-id="0008b-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="0008b-112">[**SQL ストア**] ノードの下で該当するデータベースを選択し、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0008b-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="0008b-113">[**プロパティの編集**] ダイアログ ボックスで、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0008b-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="0008b-114">既定の SQL Server インスタンスを使用するには、[ **既定のインスタンス** ] を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0008b-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="0008b-115">名前付きデータベース インスタンスを使用するには、[**名前付きインスタンス**] を選択し、テキスト ボックスにインスタンス名を入力してから [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0008b-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="0008b-116">SQL Server パス全体ではなく、インスタンス名のみ (ArchivingInstance など) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0008b-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="0008b-117">[ **プロパティの編集** ] ダイアログボックスで作業している場合、入力したデータベースインスタンスが有効なインスタンスであることは、トポロジビルダーによって確認されません。</span><span class="sxs-lookup"><span data-stu-id="0008b-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="0008b-118">たとえば、誤ってインスタンス名を typeArchivingInstanec し、[ **OK**] をクリックすると、その無効なインスタンスがトポロジビルダーによって受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="0008b-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="0008b-119">このトポロジを公開するには、その前に、この間違いを修正する必要があります。 SQL Server インスタンスが見つからない場合、トポロジビルダーはそのインスタンスを作成しません。</span><span class="sxs-lookup"><span data-stu-id="0008b-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

