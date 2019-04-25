---
title: SQL ストア設定エキスパンダー
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: SQL Server データベースのプロパティを編集するには、SQL Server データベース インスタンスを変更してください。 1 台のコンピューターから、アーカイブ サーバー データベースを移動するなどのタスクを実行するのには、[プロパティの編集] ダイアログ ボックスを使うことはできません。 さらに、使うことはできません、プロパティの編集] ダイアログ ボックスをホストする SQL Server のインスタンスを変更するのには、中央管理ストアです。
ms.openlocfilehash: d1b5287344095c062421a6afc56d620c81584fd3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235193"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="bd44b-105">SQL ストア設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="bd44b-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="bd44b-106">SQL Server データベースのプロパティを編集するには、SQL Server データベース インスタンスを変更してください。</span><span class="sxs-lookup"><span data-stu-id="bd44b-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="bd44b-107">1 台のコンピューターから、アーカイブ サーバー データベースを移動するなどのタスクを実行するのには、[**プロパティの編集**] ダイアログ ボックスを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="bd44b-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="bd44b-108">さらに、使うことはできません、**プロパティの編集**] ダイアログ ボックスをホストする SQL Server のインスタンスを変更するのには、中央管理ストアです。</span><span class="sxs-lookup"><span data-stu-id="bd44b-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="bd44b-109">SQL Server データベースのプロパティの編集</span><span class="sxs-lookup"><span data-stu-id="bd44b-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="bd44b-110">中央管理ストア以外のデータベースで使用される SQL Server のインスタンスを変更するには、トポロジ ビルダーで次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="bd44b-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="bd44b-111">SQL Server のインスタンスを変更するのには</span><span class="sxs-lookup"><span data-stu-id="bd44b-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="bd44b-112">**SQL ストア**ノードの下の適切なデータベースを選択し、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd44b-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="bd44b-113">**プロパティの編集**] ダイアログ ボックスで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bd44b-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="bd44b-114">既定の SQL Server のインスタンスを使用して、**既定のインスタンス**を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd44b-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="bd44b-115">名前付きデータベース インスタンスを使用するには、**という名前のインスタンス**を選択して、テキスト ボックスで、インスタンス名を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd44b-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="bd44b-116">のみ、インスタンス名 (ArchivingInstance など)、および全体の SQL Server のパスではなくを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd44b-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="bd44b-117">**プロパティの編集**] ダイアログ ボックスでの作業は、トポロジ ビルダーには入力したデータベース ・ インスタンスが有効なインスタンスは確認できません。</span><span class="sxs-lookup"><span data-stu-id="bd44b-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="bd44b-118">などの場合、インスタンス名として typeArchivingInstanec を誤ってとは、 **[ok]** をクリックし、トポロジ ビルダーは、無効なインスタンスを受け取ります。。</span><span class="sxs-lookup"><span data-stu-id="bd44b-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="bd44b-119">このトポロジを公開する前に、この間違いを修正する必要があります: SQL Server のインスタンスが見つかりません、トポロジ ビルダーが作成されませんインスタンスをするのです。</span><span class="sxs-lookup"><span data-stu-id="bd44b-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

