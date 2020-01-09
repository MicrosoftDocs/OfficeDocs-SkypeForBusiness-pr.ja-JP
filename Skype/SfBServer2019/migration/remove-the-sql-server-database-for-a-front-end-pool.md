---
title: フロントエンド プール用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フロントエンドプールを削除するか、プールを再構成して別のデータベースを使用する場合は、プールデータをホストしている SQL Server データベースを削除することができます。 次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。
ms.openlocfilehash: f26cf1f93abb8538c068a4ab2d6f81c9c36d759d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989092"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="f864b-104">フロントエンド プール用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="f864b-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="f864b-105">フロントエンドプールを削除するか、プールを再構成して別のデータベースを使用する場合は、プールデータをホストしている SQL Server データベースを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f864b-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="f864b-106">次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="f864b-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="f864b-107">トポロジビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="f864b-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="f864b-108">Skype for Business Server 2019 フロントエンドサーバーから、[トポロジビルダー] を開き、既存のトポロジをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f864b-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="f864b-109">[トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql Server ストア**] で、削除または再構成されたフロントエンドプールに関連付けられている sql server インスタンスを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f864b-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="f864b-110">トポロジを公開し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="f864b-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="f864b-111">SQL server からユーザーデータベースとアプリケーションデータベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="f864b-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="f864b-112">SQL server 上のデータベースを削除するには、データベースファイルを削除する SQL server の [SQL Server のオプション] グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f864b-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="f864b-113">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f864b-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="f864b-114">プールユーザーストアのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f864b-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="f864b-115">ここ_ \<で\> 、fqdn_はデータベースサーバーの完全修飾ドメイン名 (FQDN) であり_ \<、\>インスタンス_は名前付きデータベースインスタンス (定義されている場合) です。</span><span class="sxs-lookup"><span data-stu-id="f864b-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="f864b-116">プールアプリケーションストアのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f864b-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="f864b-117">ここ_ \<で\> 、fqdn_はデータベースサーバーの fqdn で、 _ \<インスタンス\> _は名前付きデータベースインスタンス (定義されている場合) です。</span><span class="sxs-lookup"><span data-stu-id="f864b-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="f864b-118">**CsDataBase**コマンドレットで操作の確認を求めるメッセージが表示されたら、情報を読み、Y (または enter) キーを押して続行するか、または N キーを押してコマンドレットを停止するか (エラーがある場合)、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f864b-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

