---
title: アーカイブ サーバー用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: アーカイブ サーバーを削除した後は、プールのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
ms.openlocfilehash: acb402dd6cb28be5b607b8a358524dfc0c1fea69
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875441"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="1cedb-104">アーカイブ サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="1cedb-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="1cedb-105">アーカイブ サーバーを削除した後は、プールのデータをホストしていた SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1cedb-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="1cedb-106">トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="1cedb-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="1cedb-107">トポロジ ビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="1cedb-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="1cedb-108">ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="1cedb-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="1cedb-109">トポロジ ビルダーでは、**コンポーネントを共有**し、 **SQL Server ストア**に移動を選択し、SQL Server のインスタンスが削除されたに関連付けられている、またはアーカイブ サーバーを再構成] を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cedb-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="1cedb-110">、トポロジを公開し、し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="1cedb-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="1cedb-111">SQL Server からデータベース ファイルを削除するのには</span><span class="sxs-lookup"><span data-stu-id="1cedb-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="1cedb-112">SQL Server 上のデータベースを削除するには、データベース ファイルを削除する SQL Server の SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cedb-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="1cedb-113">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1cedb-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="1cedb-114">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1cedb-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="1cedb-115">_ \<FQDN\>_ は、データベース ・ サーバの完全修飾ドメイン名 (FQDN) と_\<インスタンス\>_(1 つが定義されている) 場合は、名前付きデータベース インスタンスは、します。</span><span class="sxs-lookup"><span data-stu-id="1cedb-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="1cedb-116">**アンインストール CsDataBase**コマンドレットを使用して、動作を確認されたらの情報を読み、続行、または N、し、Enter キーを押します (エラーがある場合) は、コマンドレットを停止したい場合に Y (または Enter) キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1cedb-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

