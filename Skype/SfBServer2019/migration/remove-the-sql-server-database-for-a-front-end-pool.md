---
title: フロント エンド プールの SQL Server データベースを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フロント エンド プールを削除した場合、または別のデータベースを使用するプールを再構成した後は、プールのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
ms.openlocfilehash: 65fd0367051e32aa081fa13859632504e1331669
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028608"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="0a3fa-104">フロント エンド プールの SQL Server データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="0a3fa-105">フロント エンド プールを削除した場合、または別のデータベースを使用するプールを再構成した後は、プールのデータをホストしていた SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="0a3fa-106">トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="0a3fa-107">トポロジ ビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="0a3fa-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="0a3fa-108">ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを起動し、既存のトポロジをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="0a3fa-109">トポロジ ビルダーでは、**コンポーネントを共有**し、 **SQL Server ストア**に移動、削除または再構成されたフロント エンド プールに関連付けられている SQL Server のインスタンスを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="0a3fa-110">、トポロジを公開し、レプリケーション ステータスを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="0a3fa-111">ユーザーおよびアプリケーションのデータベースを SQL server から削除するのには</span><span class="sxs-lookup"><span data-stu-id="0a3fa-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="0a3fa-112">SQL サーバー上のデータベースを削除するには、データベース ファイルを削除する SQL server の SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="0a3fa-113">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="0a3fa-114">プールのユーザー ストアのデータベースを削除するのには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-114">To remove the database for the pool user store, type:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="0a3fa-115">_ \<FQDN\>_ は、データベース ・ サーバの完全修飾ドメイン名 (FQDN) と_\<インスタンス\>_(1 つが定義されている) 場合は、名前付きデータベース インスタンスは、します。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="0a3fa-116">プール アプリケーション ストアのデータベースを削除するのには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-116">To remove the database for the pool application store, type:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="0a3fa-117">_ \<FQDN\>_ は、データベース ・ サーバの FQDN と_\<インスタンス\>_(1 つが定義されている) 場合は、名前付きデータベース インスタンスは、です。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="0a3fa-118">**アンインストール CsDataBase**コマンドレットを使用して、動作を確認されたらの情報を読み、続行、または N、し、Enter キーを押します (エラーがある場合) は、コマンドレットを停止したい場合に Y (または Enter) キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0a3fa-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

