---
title: 監視サーバー用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 監視サーバーを削除した後、サーバーデータをホストしていた SQL Server データベースを削除できます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753329"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="f3cef-104">監視サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="f3cef-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="f3cef-105">監視サーバーを削除した後、サーバーデータをホストしていた SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="f3cef-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="f3cef-106">次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="f3cef-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="f3cef-107">トポロジビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="f3cef-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="f3cef-108">Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3cef-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="f3cef-109">トポロジビルダーで、[**共有コンポーネント**] に移動し、[ **sql server ストア**] をクリックし、削除または再構成された監視サーバーに関連付けられている sql server インスタンスを右クリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3cef-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="f3cef-110">トポロジを公開し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="f3cef-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="f3cef-111">SQL Server からデータベース ファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="f3cef-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="f3cef-112">SQL Server ベースのサーバーにあるデータベースを削除するためには、削除しようとしているデータベース ファイルがある SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f3cef-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="f3cef-113">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3cef-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="f3cef-114">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3cef-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="f3cef-115">ここ _\<FQDN\>_ で、はデータベースサーバーの完全修飾ドメイン名 (FQDN)、 _\<instance\>_ はオプションの名前付きデータベースインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f3cef-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="f3cef-116">**Uninstall**コマンドレットを実行してアクションを確認するように求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、N キーを押してコマンドレットを停止します (エラーがある場合)。</span><span class="sxs-lookup"><span data-stu-id="f3cef-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

