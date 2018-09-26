---
title: アーカイブ サーバーの SQL Server データベースを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: アーカイブ サーバーを削除した後は、プールのデータをホストしていた SQL Server データベースを削除できます。 トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。
ms.openlocfilehash: c82f718cf86de653f6c1340d38e21e96cbaa150d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027964"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="38345-104">アーカイブ サーバーの SQL Server データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="38345-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="38345-105">アーカイブ サーバーを削除した後は、プールのデータをホストしていた SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="38345-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="38345-106">トポロジ ビルダーでは、定義を削除するのには次の手順を使用し、データベース ・ サーバからデータベースとログ ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="38345-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="38345-107">トポロジ ビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="38345-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="38345-108">ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="38345-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="38345-109">トポロジ ビルダーでは、**コンポーネントを共有**し、 **SQL Server ストア**に移動を選択し、SQL Server のインスタンスが削除されたに関連付けられている、またはアーカイブ サーバーを再構成] を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38345-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="38345-110">、トポロジを公開し、し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="38345-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="38345-111">SQL Server からデータベース ファイルを削除するのには</span><span class="sxs-lookup"><span data-stu-id="38345-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="38345-112">SQL Server 上のデータベースを削除するには、データベース ファイルを削除する SQL Server の SQL Server システム管理者グループのメンバーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38345-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="38345-113">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="38345-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="38345-114">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="38345-114">At the command line, type the following:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="38345-115">_ \<FQDN\>_ は、データベース ・ サーバの完全修飾ドメイン名 (FQDN) と_\<インスタンス\>_(1 つが定義されている) 場合は、名前付きデータベース インスタンスは、します。</span><span class="sxs-lookup"><span data-stu-id="38345-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="38345-116">**アンインストール CsDataBase**コマンドレットを使用して、動作を確認されたらの情報を読み、続行、または N、し、Enter キーを押します (エラーがある場合) は、コマンドレットを停止したい場合に Y (または Enter) キーを押します。</span><span class="sxs-lookup"><span data-stu-id="38345-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

