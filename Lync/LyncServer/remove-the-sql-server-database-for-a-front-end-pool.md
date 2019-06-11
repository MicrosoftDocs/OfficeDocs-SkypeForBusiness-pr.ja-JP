---
title: フロントエンド プール用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="3d5dc-102">フロントエンド プール用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="3d5dc-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d5dc-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3d5dc-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3d5dc-104">Microsoft Lync Server 2010 フロントエンドプールを削除するか、プールを再構成して別のデータベースを使用する場合は、プールデータをホストしている SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="3d5dc-105">次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="3d5dc-106">トポロジビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="3d5dc-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="3d5dc-107">Lync Server 2013 フロントエンドサーバーから、[トポロジビルダー] を開き、既存のトポロジをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="3d5dc-108">[トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql Server ストア**] で、削除または再構成されたフロントエンドプールに関連付けられている sql server インスタンスを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="3d5dc-109">トポロジを公開し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="3d5dc-110">SQL Server からユーザーデータベースとアプリケーションデータベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="3d5dc-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="3d5dc-111">SQL Server 上のデータベースを削除するには、データベースファイルを削除する SQL Server の [SQL Server のオプション] グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="3d5dc-112">Lync Server 管理シェルを開く</span><span class="sxs-lookup"><span data-stu-id="3d5dc-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="3d5dc-113">プールユーザーストアのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="3d5dc-114">ここ\<で\> 、fqdn はデータベースサーバーの完全修飾ドメイン名 (FQDN) であり\<、\>インスタンスは名前付きデータベースインスタンス (定義されている場合) です。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="3d5dc-115">プールアプリケーションストアのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="3d5dc-116">ここ\<で\> 、fqdn はデータベースサーバーの fqdn で、 \<インスタンス\>は名前付きデータベースインスタンス (定義されている場合) です。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="3d5dc-117">**CsDataBase**コマンドレットで操作の確認を求めるメッセージが表示されたら、情報を読み、 **Y**キーを押します (または、enter \*\*\*\* キーを押すか、enter キーを押して続行します)。または、コマンドレットを停止するか (エラーがある場合)、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3d5dc-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

