---
title: 監視サーバーの SQL Server データベースを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 監視サーバーを削除した後は、サーバーのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
ms.openlocfilehash: 85999f1bbb3fc443edcab9d1f1354f26187c6a75
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373358"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="51ee8-104">監視サーバーの SQL Server データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="51ee8-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="51ee8-105">監視サーバーを削除した後は、サーバーのデータをホストしていた SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="51ee8-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="51ee8-106">トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="51ee8-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="51ee8-107">トポロジ ビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="51ee8-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="51ee8-108">ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="51ee8-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="51ee8-109">トポロジ ビルダーでは、**コンポーネントを共有**し、 **SQL Server ストア**に移動を選択し、SQL Server のインスタンスが削除されたに関連付けられている、またはサーバーの監視を再設定] を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51ee8-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="51ee8-110">、トポロジを公開し、し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="51ee8-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="51ee8-111">SQL Server からデータベース ファイルを削除するのには</span><span class="sxs-lookup"><span data-stu-id="51ee8-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="51ee8-112">SQL Server ベースのサーバー上のデータベースを削除するには、データベース ファイルを削除する SQL Server サーバーの SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ee8-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="51ee8-113">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="51ee8-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="51ee8-114">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="51ee8-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="51ee8-115">_ \<FQDN\>_ は、データベース ・ サーバの完全修飾ドメイン名 (FQDN) と_\<インスタンス\>_ 省略可能な名前付きデータベース インスタンスは、します。</span><span class="sxs-lookup"><span data-stu-id="51ee8-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="51ee8-116">**アンインストール CsDataBase**コマンドレットを使用して、動作を確認されたらの情報を読み、続行、または N、し、Enter キーを押します (エラーがある場合) は、コマンドレットを停止したい場合に Y (または Enter) キーを押します。</span><span class="sxs-lookup"><span data-stu-id="51ee8-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

