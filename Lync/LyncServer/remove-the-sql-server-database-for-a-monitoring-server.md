---
title: 監視サーバー用の SQL Server データベースの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f877f7d8d1ade4d260ed137f52046c21f29cf11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="6a232-102">監視サーバー用の SQL Server データベースの削除</span><span class="sxs-lookup"><span data-stu-id="6a232-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a232-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="6a232-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="6a232-104">Microsoft Lync Server 2010 監視サーバーを削除したら、サーバーデータをホストしている SQL Server データベースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6a232-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="6a232-105">次の手順を使用して、Topology Builder から定義を削除し、データベースサーバーからデータベースとログファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="6a232-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="6a232-106">トポロジビルダーを使用して SQL Server データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="6a232-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="6a232-107">Lync Server 2013 フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="6a232-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="6a232-108">[トポロジビルダー] で、[**共有コンポーネント**] に移動し、[ **sql server ストア**] で、削除または再構成された監視サーバーに関連付けられている sql server インスタンスを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a232-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="6a232-109">トポロジを公開し、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a232-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="6a232-110">SQL Server からデータベースファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="6a232-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="6a232-111">SQL Server ベースのサーバー上のデータベースを削除するには、データベースファイルを削除する SQL Server サーバーの SQL Server の [データファイル] グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a232-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="6a232-112">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6a232-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="6a232-113">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6a232-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="6a232-114">ここ\<で\> 、fqdn はデータベースサーバーの完全修飾ドメイン名 (FQDN) で、 \<[\>インスタンス] はオプションの名前付きデータベースインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="6a232-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="6a232-115">**CsDataBase**コマンドレットで操作の確認を求めるメッセージが表示されたら、情報を読み、 **Y**キーを押します (または、enter キーを押すか、enter キーを押して続行します)。または、コマンドレットを停止するか (エラーがある場合)、enter キー**を押します**。</span><span class="sxs-lookup"><span data-stu-id="6a232-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

