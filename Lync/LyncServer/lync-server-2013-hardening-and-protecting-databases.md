---
title: 'Lync Server 2013: データベースのセキュリティ強化および保護'
description: 'Lync Server 2013: データベースの強化と保護。'
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
ms.openlocfilehash: af1ed8f54384e8ecac3b1e4ce6a4253a10bcc2c6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577433"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="5036c-103">Lync Server 2013 のデータベースの強化と保護</span><span class="sxs-lookup"><span data-stu-id="5036c-103">Hardening and protecting the databases of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5036c-104">_**トピックの最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="5036c-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="5036c-105">また、Microsoft Lync Server 2013 は、ユーザー情報、会議の状態、アーカイブデータ、および通話詳細レコード (Cdr) を格納するための SQL Server データベースに依存しています。</span><span class="sxs-lookup"><span data-stu-id="5036c-105">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="5036c-106">Lync Server のバックエンドデータベースで Lync Server 2013 データを最大限に利用できるようにするには、フォールトトレランスを向上させてトラブルシューティングを簡略化する方法でアプリケーションデータをパーティション分割します。</span><span class="sxs-lookup"><span data-stu-id="5036c-106">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="5036c-107">アプリケーション データを分割する方法は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5036c-107">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="5036c-108">**サーバーパーティション分割のベストプラクティス**     の使用オペレーティングシステム、アプリケーション、およびプログラムファイルをデータファイルから分離します。</span><span class="sxs-lookup"><span data-stu-id="5036c-108">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="5036c-109">**トランザクションログファイルとデータベースファイル**     の保存これらのファイルを別々に保存して、フォールトトレランスを向上させ、回復を最適化し、暗号化されたディスクまたはボリュームに保存します。</span><span class="sxs-lookup"><span data-stu-id="5036c-109">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="5036c-110">**サーバーのクラスター化**     を使用するバックエンドサーバーをクラスター化して、Lync Server 2013 のシステム可用性を最適化します。</span><span class="sxs-lookup"><span data-stu-id="5036c-110">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="5036c-111">**すべてのデータバックアップが暗号化され、適切に処理**     されることを確認する紛失、破棄、または紛失したバックアップメディアは、Lync Server 2013 の展開のデータセキュリティに大きな脅威をもたらす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5036c-111">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="5036c-112">Standard Edition サーバー以外の Lync Server 2013 サーバーでは、SQL Server Express インスタンス (RTCLOCAL インスタンス) はリモートでアクセスできず、ローカルファイアウォールの例外は作成されません。ただし、Standard Edition サーバー上の SQL Server Express を除きます。</span><span class="sxs-lookup"><span data-stu-id="5036c-112">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="5036c-113">Standard Edition サーバーでは、バックエンドデータベースと中央管理ストア (CMS) の両方がリモートでアクセスできるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="5036c-113">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="5036c-114">SQL Server データベースを強化するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5036c-114">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="5036c-p103">Standard Edition サーバー上の SQL Server Express ファイアウォールをカスタマイズして、データベースにリモートからアクセスできるサーバーのスコープを制限します。既定では、すべての IP アドレスがデータベースにリモートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5036c-p103">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database. By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="5036c-117">SQL Server 構成マネージャーを使用して、SQL Server リモート アクセス用のプロトコル、IP アドレス、およびポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="5036c-117">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="5036c-118">Lync Server 2013 は TCP/IP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5036c-118">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="5036c-119">IP version 4 (IPv4) をサポートし、IP version 6 (IPv6) はサポートしません。</span><span class="sxs-lookup"><span data-stu-id="5036c-119">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5036c-120">Lync Server 2013 は、デュアル IP スタックが有効になっているネットワークで機能します。</span><span class="sxs-lookup"><span data-stu-id="5036c-120">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="5036c-121">Lync Server 2013 では、複数の IP アドレス (マルチホームネットワークアドレスカード) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5036c-121">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="5036c-122">SQL Server が特定の IP アドレス (個別のアドレスまたはサブネット単位) のみをリッスンすることや、特定のプロトコルのみを使用することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5036c-122">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="5036c-123">Lync Server 2013 は、静的および動的な SQL Server ポートをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5036c-123">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="5036c-124">既定でない静的ポートで SQL Server を実行し、SQL Server ブラウザーを実行しません (この結果、クライアントにリッスン ポートをレポートできません)。</span><span class="sxs-lookup"><span data-stu-id="5036c-124">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="5036c-125">これには、フロントエンドサーバー、監視サーバー、アーカイブサーバー、管理コンソール (Lync Server 管理シェル、Lync Server コントロールパネル、またはトポロジビルダーを実行している)、および Lync Server データベースを実行している他のすべてのサーバーを含む、各 SQL Server クライアントのカスタム構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="5036c-125">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5036c-126">データベースへのアクセスは、信頼できるデータベース管理者に制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5036c-126">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="5036c-127">悪意のあるデータベース管理者は、データベース管理者が Lync Server 2013 サーバーの直接のアクセスや制御を許可されていない場合でも、Lync Server 2013 サーバーでの権限を取得するか、またはサービスから機密情報を取得するために、データベースにデータを挿入または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5036c-127">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="5036c-128">カスタム構成の詳細と SQL Server データベースのセキュリティ強化については、NextHop の記事「カスタム SQL Server ネットワーク構成での Lync Server 2010 の使用」、「」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) 。</span><span class="sxs-lookup"><span data-stu-id="5036c-128">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5036c-129">また、オペレーティングシステムとアプリケーションサーバーを強化することもできます。また、グループポリシーを使用して、Lync Server 展開のセキュリティロックダウンを実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="5036c-129">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="5036c-130">詳細については、「 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Lync Server 2013 のサーバーとアプリケーションのセキュリティ強化と保護</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5036c-130">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

