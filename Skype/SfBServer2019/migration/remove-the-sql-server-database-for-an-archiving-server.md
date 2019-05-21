---
title: アーカイブ サーバー用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: アーカイブサーバーを削除した後で、プールデータをホストしている SQL Server データベースを削除できます。 次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: 975252ee991df507f02bc490d1d2ef2614f3b475
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307106"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="2e3f4-104">アーカイブ サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="2e3f4-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="2e3f4-105">アーカイブサーバーを削除した後で、プールデータをホストしている SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="2e3f4-106">次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="2e3f4-107">トポロジビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="2e3f4-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="2e3f4-108">Skype for Business Server 2019 フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="2e3f4-109">[トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql server ストア**] で、削除または再構成されたアーカイブサーバーに関連付けられている sql server インスタンスを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="2e3f4-110">トポロジを公開し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="2e3f4-111">SQL Server からデータベースファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="2e3f4-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="2e3f4-112">SQL Server 上のデータベースを削除するには、データベースファイルを削除する SQL Server の [SQL Server のオプション] グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="2e3f4-113">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="2e3f4-114">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="2e3f4-115">ここ_ \<で\> 、fqdn_はデータベースサーバーの完全修飾ドメイン名 (FQDN) であり_ \<、\>インスタンス_は名前付きデータベースインスタンス (定義されている場合) です。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="2e3f4-116">**CsDataBase**コマンドレットで操作の確認を求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、または N キーを押してコマンドレットを停止するか (エラーがある場合)、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2e3f4-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

