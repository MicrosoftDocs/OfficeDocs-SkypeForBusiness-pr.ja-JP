---
title: フロントエンド プール用の SQL Server データベースの削除
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
description: フロントエンドプールを削除した後、または別のデータベースを使用するようにプールを再構成した後は、プールデータをホストしていた SQL Server データベースを削除できます。 次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753409"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="b6de1-104">フロントエンド プール用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="b6de1-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="b6de1-105">フロントエンドプールを削除した後、または別のデータベースを使用するようにプールを再構成した後は、プールデータをホストしていた SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b6de1-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="b6de1-106">次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="b6de1-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="b6de1-107">トポロジビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="b6de1-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="b6de1-108">Skype for Business Server 2019 フロントエンドサーバーから、トポロジビルダーを開き、既存のトポロジをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b6de1-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="b6de1-109">[トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql server ストア**] を選択して、削除または再構成したフロントエンドプールに関連付けられている SQL server インスタンスを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6de1-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="b6de1-110">トポロジを公開し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="b6de1-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="b6de1-111">SQL server からユーザーおよびアプリケーションデータベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="b6de1-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="b6de1-112">SQL server 上のデータベースを削除するには、データベースファイルを削除する対象の SQL server の SQL Server の [ユーザー] グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6de1-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="b6de1-113">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b6de1-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="b6de1-114">プール ユーザー ストアのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6de1-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="b6de1-115">ここで、 _\<FQDN\>_ はデータベースサーバーの完全修飾ドメイン名 (FQDN)、 _\<instance\>_ は名前付きデータベースインスタンス (定義されている場合) です。</span><span class="sxs-lookup"><span data-stu-id="b6de1-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="b6de1-116">プール アプリケーション ストアのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6de1-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="b6de1-117">ここで、 _\<FQDN\>_ はデータベースサーバーの FQDN、は _\<instance\>_ 名前付きデータベースインスタンス (定義されている場合) です。</span><span class="sxs-lookup"><span data-stu-id="b6de1-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="b6de1-118">**Uninstall**コマンドレットを実行してアクションを確認するように求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、N キーを押してコマンドレットを停止します (エラーがある場合)。</span><span class="sxs-lookup"><span data-stu-id="b6de1-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

