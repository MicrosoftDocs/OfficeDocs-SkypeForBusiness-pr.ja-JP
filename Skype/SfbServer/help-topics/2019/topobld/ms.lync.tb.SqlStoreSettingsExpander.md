---
title: SQL ストア設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: データベースのプロパティを編集SQL Server、データベース インスタンスのSQL Serverする必要があります。 [プロパティの編集] ダイアログ ボックスで、アーカイブ サーバー データベースをコンピューター間で移動するなどのタスクを実行することはできません。 また、[プロパティの編集] ダイアログ ボックスを使用して、中央管理ストアをSQL Serverのインスタンスを変更することはできません。
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805517"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="8e3be-105">SQL ストア設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="8e3be-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="8e3be-106">データベースのプロパティを編集SQL Server、データベース インスタンスのSQL Serverする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e3be-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="8e3be-107">[**プロパティの編集**] ダイアログ ボックスで、アーカイブ サーバー データベースをコンピューター間で移動するなどのタスクを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="8e3be-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="8e3be-108">また、[プロパティの編集]ダイアログ ボックスを使用して、中央管理ストアをSQL Serverのインスタンスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="8e3be-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="8e3be-109">データベースのプロパティSQL Serverする</span><span class="sxs-lookup"><span data-stu-id="8e3be-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="8e3be-110">中央管理ストア以外のSQL Serverデータベースで使用されるデータベースのインスタンスを変更するには、トポロジ ビルダーで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8e3be-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="8e3be-111">オブジェクトのインスタンスを変更SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e3be-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="8e3be-112">[**SQL ストア**] ノードの下で該当するデータベースを選択し、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e3be-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="8e3be-113">[**プロパティの編集**] ダイアログ ボックスで、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8e3be-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="8e3be-114">既定のインスタンスを使用SQL Server、[既定のインスタンス] **を選択** し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e3be-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="8e3be-115">名前付きデータベース インスタンスを使用するには、[**名前付きインスタンス**] を選択し、テキスト ボックスにインスタンス名を入力してから [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e3be-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="8e3be-116">インスタンス名 (ArchivingInstance など) のみを入力し、パス全体を入力SQL Serverしてください。</span><span class="sxs-lookup"><span data-stu-id="8e3be-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="8e3be-117">[プロパティの編集]ダイアログ ボックスで作業している場合、入力したデータベース インスタンスが有効なインスタンスとしてトポロジ ビルダーによって検証されません。</span><span class="sxs-lookup"><span data-stu-id="8e3be-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="8e3be-118">たとえば、インスタンス名として誤って「ArchivingInstanec」と入力し **、[OK]** をクリックすると、トポロジ ビルダーはその無効なインスタンスを受け入れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8e3be-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="8e3be-119">このトポロジを公開する前に、この間違いを修正する必要があります。SQL Server インスタンスが見つからない場合、トポロジ ビルダーによってそのインスタンスは作成されます。</span><span class="sxs-lookup"><span data-stu-id="8e3be-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

