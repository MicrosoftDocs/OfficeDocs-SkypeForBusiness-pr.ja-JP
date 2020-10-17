---
title: 'Lync Server 2013: データベースのセキュリティ強化および保護'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0254c77bb276add6f55ccff623c1fc2bec590102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536914"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="3c8d7-102">Lync Server 2013 のデータベースの強化と保護</span><span class="sxs-lookup"><span data-stu-id="3c8d7-102">Hardening and protecting the databases of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c8d7-103">_**トピックの最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="3c8d7-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="3c8d7-104">また、Microsoft Lync Server 2013 は、ユーザー情報、会議の状態、アーカイブデータ、および通話詳細レコード (Cdr) を格納するための SQL Server データベースに依存しています。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="3c8d7-105">Lync Server のバックエンドデータベースで Lync Server 2013 データを最大限に利用できるようにするには、フォールトトレランスを向上させてトラブルシューティングを簡略化する方法でアプリケーションデータをパーティション分割します。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="3c8d7-106">アプリケーション データを分割する方法は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="3c8d7-107">**サーバーパーティション分割のベストプラクティス**     の使用オペレーティングシステム、アプリケーション、およびプログラムファイルをデータファイルから分離します。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="3c8d7-108">**トランザクションログファイルとデータベースファイル**     の保存これらのファイルを別々に保存して、フォールトトレランスを向上させ、回復を最適化し、暗号化されたディスクまたはボリュームに保存します。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="3c8d7-109">**サーバーのクラスター化**     を使用するバックエンドサーバーをクラスター化して、Lync Server 2013 のシステム可用性を最適化します。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="3c8d7-110">**すべてのデータバックアップが暗号化され、適切に処理**     されることを確認する紛失、破棄、または紛失したバックアップメディアは、Lync Server 2013 の展開のデータセキュリティに大きな脅威をもたらす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="3c8d7-111">Standard Edition サーバー以外の Lync Server 2013 サーバーでは、SQL Server Express インスタンス (RTCLOCAL インスタンス) はリモートでアクセスできず、ローカルファイアウォールの例外は作成されません。ただし、Standard Edition サーバー上の SQL Server Express を除きます。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="3c8d7-112">Standard Edition サーバーでは、バックエンドデータベースと中央管理ストア (CMS) の両方がリモートでアクセスできるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="3c8d7-113">SQL Server データベースを強化するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="3c8d7-p103">Standard Edition サーバー上の SQL Server Express ファイアウォールをカスタマイズして、データベースにリモートからアクセスできるサーバーのスコープを制限します。既定では、すべての IP アドレスがデータベースにリモートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-p103">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database. By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="3c8d7-116">SQL Server 構成マネージャーを使用して、SQL Server リモート アクセス用のプロトコル、IP アドレス、およびポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="3c8d7-117">Lync Server 2013 は TCP/IP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="3c8d7-118">IP version 4 (IPv4) をサポートし、IP version 6 (IPv6) はサポートしません。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3c8d7-119">Lync Server 2013 は、デュアル IP スタックが有効になっているネットワークで機能します。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="3c8d7-120">Lync Server 2013 では、複数の IP アドレス (マルチホームネットワークアドレスカード) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="3c8d7-121">SQL Server が特定の IP アドレス (個別のアドレスまたはサブネット単位) のみをリッスンすることや、特定のプロトコルのみを使用することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="3c8d7-122">Lync Server 2013 は、静的および動的な SQL Server ポートをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="3c8d7-123">既定でない静的ポートで SQL Server を実行し、SQL Server ブラウザーを実行しません (この結果、クライアントにリッスン ポートをレポートできません)。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="3c8d7-124">これには、フロントエンドサーバー、監視サーバー、アーカイブサーバー、管理コンソール (Lync Server 管理シェル、Lync Server コントロールパネル、またはトポロジビルダーを実行している)、および Lync Server データベースを実行している他のすべてのサーバーを含む、各 SQL Server クライアントのカスタム構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c8d7-125">データベースへのアクセスは、信頼できるデータベース管理者に制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="3c8d7-126">悪意のあるデータベース管理者は、データベース管理者が Lync Server 2013 サーバーの直接のアクセスや制御を許可されていない場合でも、Lync Server 2013 サーバーでの権限を取得するか、またはサービスから機密情報を取得するために、データベースにデータを挿入または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="3c8d7-127">カスタム構成の詳細と SQL Server データベースのセキュリティ強化については、NextHop の記事「カスタム SQL Server ネットワーク構成での Lync Server 2010 の使用」、「」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) 。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c8d7-128">また、オペレーティングシステムとアプリケーションサーバーを強化することもできます。また、グループポリシーを使用して、Lync Server 展開のセキュリティロックダウンを実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="3c8d7-129">詳細については、「 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Lync Server 2013 のサーバーとアプリケーションのセキュリティ強化と保護</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c8d7-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

