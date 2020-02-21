---
title: アーカイブサーバーの SQL Server データベースを削除する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d077b21b1b45cc73c268b3dc6294f0a476f48809
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="3314d-102">アーカイブサーバーの SQL Server データベースを削除する</span><span class="sxs-lookup"><span data-stu-id="3314d-102">Remove the SQL Server database for an Archiving server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3314d-103">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3314d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3314d-104">Microsoft Lync Server 2010 アーカイブサーバーを削除した後、プールデータをホストしていた SQL Server データベースを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3314d-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="3314d-105">次の手順を使用して、トポロジビルダーから定義を削除し、データベースサーバーからデータベースとログファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="3314d-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="3314d-106">トポロジビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="3314d-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="3314d-107">Lync Server 2013 フロントエンドサーバーで、トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="3314d-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="3314d-108">トポロジビルダーで、[**共有コンポーネント**] に移動し、[ **sql server ストア**] をクリックし、削除または再構成したアーカイブサーバーに関連付けられている sql server インスタンスを右クリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3314d-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="3314d-109">トポロジを公開し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="3314d-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="3314d-110">SQL Server からデータベース ファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="3314d-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="3314d-111">SQL Server のデータベースを削除するには、データベース ファイルを削除している SQL Server の SQL Server sysadmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3314d-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="3314d-112">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3314d-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="3314d-113">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3314d-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="3314d-114">ここ\<で\> 、fqdn はデータベースサーバーの完全修飾ドメイン名 (fqdn)、 \<インスタンス\>は名前付きデータベースインスタンス (定義されている場合) です。</span><span class="sxs-lookup"><span data-stu-id="3314d-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="3314d-115">**Uninstall-CsDataBase** コマンドレットから操作を確認するメッセージが表示される場合は、情報を読み、**Y** (または Enter) キーを押して操作を続行するか、**N** キーを押し、次に Enter キーを押してコマンドレットを停止します (問題がある場合)。</span><span class="sxs-lookup"><span data-stu-id="3314d-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

