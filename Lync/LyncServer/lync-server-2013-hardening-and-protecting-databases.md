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
ms.openlocfilehash: 77e02a5fd0f90367f23e7b0fb314f037f7b31e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="5228f-102">Lync Server 2013 のデータベースのセキュリティ強化および保護</span><span class="sxs-lookup"><span data-stu-id="5228f-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5228f-103">_**最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="5228f-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="5228f-104">Microsoft Lync Server 2013 は、ユーザー情報、会議の状態、アーカイブデータ、および通話詳細レコード (CDRs) を保存するための SQL Server データベースにも依存しています。</span><span class="sxs-lookup"><span data-stu-id="5228f-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="5228f-105">Lync server 2013 データを Lync Server のバックエンドデータベースで最大限に活用するには、フォールトトレランスを向上させてトラブルシューティングを簡素化する方法でアプリケーションデータを区分することができます。</span><span class="sxs-lookup"><span data-stu-id="5228f-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="5228f-106">これらの目標を達成するには、次の方法でアプリケーションデータをパーティションに分割します。</span><span class="sxs-lookup"><span data-stu-id="5228f-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="5228f-107">**サーバーのパーティション分割のベストプラクティス**   は、オペレーティングシステムファイル、アプリケーションファイル、プログラムファイルをデータファイルから分離することです。</span><span class="sxs-lookup"><span data-stu-id="5228f-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="5228f-108">**トランザクションログファイルとデータベースファイル**   を保存する場合は、これらのファイルを別々に保存して、フォールトトレランスを強化し、回復を最適化して、暗号化されたディスクまたはボリュームに保存します。</span><span class="sxs-lookup"><span data-stu-id="5228f-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="5228f-109">**サーバークラスタリング**   の使用バックエンドサーバーを使用して、Lync server 2013 システムの可用性を最適化します。</span><span class="sxs-lookup"><span data-stu-id="5228f-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="5228f-110">**すべてのデータバックアップを暗号化して適切に処理**   されないようにして、紛失、廃棄、または紛失したバックアップメディアを使用して、Lync Server 2013 の展開のデータセキュリティに大きな脅威が生じる可能性があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5228f-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="5228f-111">Standard Edition server 以外の Lync Server 2013 サーバーでは、SQL Server Express インスタンス (RTCLOCAL インスタンス) にリモートからアクセスすることはできません。また、Standard Edition サーバー上の SQL Server Express を除き、ローカルのファイアウォール例外は作成されません。</span><span class="sxs-lookup"><span data-stu-id="5228f-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="5228f-112">Standard Edition サーバーでは、バックエンドデータベースと中央管理ストア (CMS) の両方が、リモートでアクセスできるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="5228f-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="5228f-113">SQL Server データベースを強化するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5228f-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="5228f-114">Standard Edition サーバーの SQL Server Express ファイアウォールをカスタマイズして、データベースにリモートアクセスできるサーバーの範囲を制限します。</span><span class="sxs-lookup"><span data-stu-id="5228f-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="5228f-115">既定では、すべての IP アドレスでデータベースにリモートアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5228f-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="5228f-116">Sql server 構成マネージャーを使用して、SQL Server リモートアクセスのプロトコル、IP アドレス、ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="5228f-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="5228f-117">Lync Server 2013 は、TCP/IP プロトコルを使います。</span><span class="sxs-lookup"><span data-stu-id="5228f-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="5228f-118">IP バージョン 4 (IPv4) をサポートしますが、IP バージョン 6 (IPv6) ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5228f-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5228f-119">Lync Server 2013 は、デュアル IP スタックが有効になっているネットワークで機能することができます。</span><span class="sxs-lookup"><span data-stu-id="5228f-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="5228f-120">Lync Server 2013 は複数の IP アドレス (マルチホームネットワークのアドレスカード) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5228f-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="5228f-121">SQL Server が特定の IP アドレス (個別のアドレスまたはサブネット) のみをリッスンするように指定し、特定のプロトコルのみを使用するように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5228f-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="5228f-122">Lync Server 2013 は、静的および動的な SQL Server のポートをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5228f-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="5228f-123">静的な (既定以外の) ポートで SQL Server を実行します。 SQL Server Browser は実行しないでください (クライアントにリスニングポートを報告することはできません)。</span><span class="sxs-lookup"><span data-stu-id="5228f-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="5228f-124">これには、フロントエンドサーバー、監視サーバー、アーカイブサーバー、管理コンソール (Lync Server 管理シェル、Lync Server コントロールパネル、またはトポロジビルダーを実行する)、およびその他の各 SQL Server クライアントでカスタム構成が必要です。Lync Server データベースを実行しているサーバー)。</span><span class="sxs-lookup"><span data-stu-id="5228f-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5228f-125">データベースへのアクセスは、信頼できるデータベース管理者に制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5228f-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="5228f-126">データベース管理者が直接アクセス許可を付与されていない場合でも、悪意のあるデータベース管理者はデータベースにデータを挿入または変更して、Lync Server 2013 サーバー経由で権限を取得するか、またはサービスから機密情報を取得することができます。Lync Server 2013 サーバーの制御。</span><span class="sxs-lookup"><span data-stu-id="5228f-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="5228f-127">カスタム構成と SQL Server データベースの強化の詳細については、「NextHop ブログの記事「カスタム SQL Server ネットワーク構成での Lync Server 2010 の[http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5228f-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5228f-128">オペレーティングシステムやアプリケーションサーバーを強化することもできます。また、グループポリシーを使用して、Lync Server の展開にセキュリティ lockdowns を実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="5228f-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="5228f-129">詳細については、「 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Lync Server 2013 用のサーバーとアプリケーションの強化と保護</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5228f-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

