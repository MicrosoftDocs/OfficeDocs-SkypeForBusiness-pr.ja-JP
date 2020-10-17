---
title: 監視サーバー用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda833bd188eeaa2b969e8748bffb87944c5dc59
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518114"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="84981-102">監視サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="84981-102">Remove the SQL Server database for a Monitoring server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84981-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="84981-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="84981-104">Microsoft Lync Server 2010 監視サーバーを削除した後、サーバーデータをホストしていた SQL Server データベースを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="84981-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="84981-105">次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="84981-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="84981-106">トポロジビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="84981-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="84981-107">Lync Server 2013 フロントエンドサーバーで、トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="84981-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="84981-108">トポロジビルダーで、[ **共有コンポーネント** ] に移動し、[ **sql server ストア**] をクリックし、削除または再構成された監視サーバーに関連付けられている sql server インスタンスを右クリックして、[ **削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84981-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="84981-109">トポロジを公開し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="84981-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="84981-110">SQL Server からデータベース ファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="84981-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="84981-111">SQL Server ベースのサーバーにあるデータベースを削除するためには、削除しようとしているデータベース ファイルがある SQL Server ベースのサーバーの SQL Server sysadmins グループのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="84981-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="84981-112">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="84981-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="84981-113">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="84981-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="84981-114">ここ \<FQDN\> で、はデータベースサーバーの完全修飾ドメイン名 (FQDN)、 \<instance\> はオプションの名前付きデータベースインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="84981-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="84981-115">**Uninstall-CsDataBase** コマンドレットから操作を確認するメッセージが表示される場合は、情報を読み、**Y** (または Enter) キーを押して操作を続行するか、**N** キーを押し、次に Enter キーを押してコマンドレットを停止します (問題がある場合)。</span><span class="sxs-lookup"><span data-stu-id="84981-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

