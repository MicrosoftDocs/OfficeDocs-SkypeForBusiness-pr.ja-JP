---
title: オペレーティングシステムと必要なソフトウェアをサーバーにインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 266e8b049bd5de97fbb8f8d5d1e89b7280db3d4f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="c12a7-102">Lync Server 2013 のサーバーにオペレーティングシステムと必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="c12a7-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c12a7-103">_**トピックの最終更新日:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="c12a7-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="c12a7-104">ハードウェアおよびシステム インフラストラクチャを設定したら、展開する各サーバーに適切な Windows オペレーティング システム、更新プログラム、および他の必要なソフトウェアをすべてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="c12a7-105">これには、各 Lync Server 2013 のサーバーの役割、および展開に必要な SQL Server を実行している追加のインフラストラクチャサーバーまたはサーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c12a7-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c12a7-106">ここでは、オペレーティング システムと内部サーバーに必要なソフトウェアのインストールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c12a7-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="c12a7-107">エッジサーバーを展開して外部ユーザーアクセスをサポートする場合は、エッジサーバーやリバースプロキシサーバーを含む、これらのサーバーのオペレーティングシステムと前提条件となるソフトウェアもインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="c12a7-108">外部ユーザーアクセスをサポートするサーバーの準備の詳細については、「展開」のドキュメントの「<A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">境界ネットワークでのサーバーのインストールの準備 (Lync Server 2013 の</A>場合)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="c12a7-109">サーバーへの Windows オペレーティング システムのインストール</span><span class="sxs-lookup"><span data-stu-id="c12a7-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="c12a7-110">展開する各サーバーで、次のようにして適切な Windows オペレーティングシステムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c12a7-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="c12a7-111">**Lync server 2013**   を実行しているサーバー lync server 2013 を実行しているサーバーのオペレーティングシステム要件の詳細については、「サポート」のドキュメントの「 [lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="c12a7-112">**データベース**サーバーバックエンドデータベース、アーカイブデータベース、監視データベースなど、データベースサーバーのオペレーティングシステム要件の詳細については、SQL Server のドキュメントを参照してください。   </span><span class="sxs-lookup"><span data-stu-id="c12a7-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="c12a7-113">SQL Server 2012 については、SQL Server 2012 オンラインブック[https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)() を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c12a7-114">Windows Server&nbsp;2008&nbsp;R2 SP1 に Lync Server 2013 をインストールしている場合は、まず、マイクロソフトサポート技術情報の記事2646886「修正: モジュールが IIS 7.5 で insertentitybody メソッドを呼び出すときにヒープの破損が発生する」 ( <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&ampkbid = 2646886</A>) に記載されている更新プログラムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="c12a7-115">また、KB 記事「<A href="https://go.microsoft.com/fwlink/p/?linkid=506893">イベント id 32402, 61045 は、Windows Server 2012 にインストールされている Lync Server 2013 フロントエンドサーバーに記録さ</A>れています」の説明に従って、レジストリを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-115">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="c12a7-116">サーバーへの Windows 更新プログラムのインストール</span><span class="sxs-lookup"><span data-stu-id="c12a7-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="c12a7-117">各サーバーで、Windows Update から次の更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c12a7-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="c12a7-118">**Lync server 2013**   を実行しているサーバーの windows update lync server 2013 を実行しているサーバーに必要な更新プログラムの詳細については、「計画」のドキュメントの「 [Lync server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="c12a7-119">**データベース**   サーバーバックエンドデータベース、アーカイブデータベース、監視データベースなど、データベースサーバーに必要な更新プログラムの詳細については、SQL Server 2012 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="c12a7-120">SQL Server 2012 については、SQL Server 2012 オンラインブック[https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)() を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="c12a7-121">他の必要なソフトウェアのサーバーへのインストール</span><span class="sxs-lookup"><span data-stu-id="c12a7-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="c12a7-122">Lync Server 2013 には、サーバーに次の追加ソフトウェアがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="c12a7-123">**Lync server 2013**   を実行しているサーバーの前提条件となるソフトウェア lync server 2013 を実行しているサーバーに対するその他のソフトウェアの前提条件は、展開されているサーバーの役割によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="c12a7-124">各サーバーの特定のソフトウェア要件の詳細については、「計画」のドキュメントの「 [Lync server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="c12a7-125">**Windows identity foundation**   Lync server 2013 では、サーバー間認証のシナリオをサポートするために windows identity foundation をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="c12a7-126">コンピューターに既にインストールされていることを確認するには、[コントロールパネル] の [**プログラムと機能**] をクリックし、**インストールされた更新プログラムを表示**して、[ **Microsoft Windows**] の下に表示します。</span><span class="sxs-lookup"><span data-stu-id="c12a7-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="c12a7-127">Windows Identity Foundation のインストールの詳細につい[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)ては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-127">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="c12a7-128">**Microsoft .net framework 4.5**   Lync Server 2013 には、microsoft .net framework 4.5 の64ビットエディションが必要です。</span><span class="sxs-lookup"><span data-stu-id="c12a7-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="c12a7-129">**データベースサーバー**   の前提条件となるソフトウェアデータベースサーバーに必要な Windows Update (バックエンドデータベース、アーカイブデータベース、監視データベースなど) の詳細については、SQL Server 2012 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12a7-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c12a7-130">Lync Server 2013 は、各 Standard Edition サーバーと、ローカル構成ストアが配置されている Lync Server 2013 を実行している各サーバーに、Microsoft SQL Server 2012 Express を自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="c12a7-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="c12a7-131">**Windows media フォーマットランタイム**   会議を展開するすべてのフロントエンドサーバーと Standard Edition サーバーには、windows media フォーマットランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="c12a7-132">コール パーク、アナウンス、応答グループの各アプリケーションがアナウンスと音楽を再生する Windows Media オーディオ (.wma) ファイルを実行するには、Windows Media フォーマット ランタイムが必要です。</span><span class="sxs-lookup"><span data-stu-id="c12a7-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c12a7-133">Windows Server 2012 および Windows Server 2012 R2 では、Windows Media フォーマットランタイムが Microsoft Media Foundation と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c12a7-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c12a7-134">Windows Server&nbsp;2008 および windows server&nbsp;2008&nbsp;R2 の場合、Windows Media フォーマットランタイムは windows デスクトップ環境の一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c12a7-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="c12a7-135">Lync Server 2013 をインストールする前に、Windows デスクトップ環境をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c12a7-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="c12a7-136">Lync Server 2013 がサーバー上でこのソフトウェアを見つけられない場合は、インストールを求めるメッセージが表示され、インストールを完了するためにサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12a7-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

