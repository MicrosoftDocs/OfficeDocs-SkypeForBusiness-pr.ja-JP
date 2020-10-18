---
title: オペレーティングシステムと必要なソフトウェアをサーバーにインストールする
description: オペレーティングシステムと必要なソフトウェアをサーバーにインストールします。
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
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574133"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="90570-103">Lync Server 2013 のサーバーにオペレーティングシステムと必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="90570-103">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90570-104">_**トピックの最終更新日:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="90570-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="90570-105">ハードウェアおよびシステム インフラストラクチャを設定したら、展開する各サーバーに適切な Windows オペレーティング システム、更新プログラム、および他の必要なソフトウェアをすべてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90570-105">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="90570-106">これには、各 Lync Server 2013 のサーバーの役割、および展開に必要な SQL Server を実行している追加のインフラストラクチャサーバーまたはサーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="90570-106">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="90570-107">ここでは、オペレーティング システムと内部サーバーに必要なソフトウェアのインストールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="90570-107">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="90570-108">エッジサーバーを展開して外部ユーザーアクセスをサポートする場合は、エッジサーバーやリバースプロキシサーバーを含む、これらのサーバーのオペレーティングシステムと前提条件となるソフトウェアもインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90570-108">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="90570-109">外部ユーザーアクセスをサポートするサーバーの準備の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">境界ネットワークでのサーバーのインストールの準備 (Lync Server 2013 の</A> 場合)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90570-109">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="90570-110">サーバーへの Windows オペレーティング システムのインストール</span><span class="sxs-lookup"><span data-stu-id="90570-110">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="90570-111">展開する各サーバーで、次のようにして適切な Windows オペレーティングシステムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="90570-111">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="90570-112">**Lync Server 2013**     を実行しているサーバーLync Server 2013 を実行しているサーバーのオペレーティングシステム要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90570-112">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="90570-113">**データベースサーバー**    データベースサーバーのオペレーティングシステム要件 (バックエンドデータベース、アーカイブデータベース、監視データベースなど) の詳細については、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90570-113">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="90570-114">SQL Server 2012 については、SQL Server 2012 オンラインブック () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。</span><span class="sxs-lookup"><span data-stu-id="90570-114">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="90570-115">Windows Server 2008 R2 SP1 に Lync Server 2013 をインストールしている場合は、 &nbsp; &nbsp; まず、マイクロソフトサポート技術情報の記事2646886「修正: モジュールが IIS 7.5 で InsertEntityBody メソッドを呼び出すときにヒープの破損が発生する」 ( <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp kbid = 2646886</A>) に記載されている更新プログラムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90570-115">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="90570-116">また、KB 記事「 <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">イベント id 32402, 61045 は、Windows Server 2012 にインストールされている Lync Server 2013 フロントエンドサーバーに記録さ</A>れています」の説明に従って、レジストリを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90570-116">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="90570-117">サーバーへの Windows 更新プログラムのインストール</span><span class="sxs-lookup"><span data-stu-id="90570-117">Install Windows Update on Servers</span></span>

<span data-ttu-id="90570-118">各サーバーで、Windows Update から次の更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="90570-118">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="90570-119">**Lync Server 2013 を実行しているサーバーの Windows Update**    Lync Server 2013 を実行しているサーバーで必要とされる Windows Update からの更新プログラムの詳細については、「計画」のドキュメントの「 [Lync server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90570-119">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="90570-120">**データベースサーバー**    バックエンドデータベース、アーカイブデータベース、監視データベースなど、データベースサーバーに必要な更新プログラムの詳細については、SQL Server 2012 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90570-120">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="90570-121">SQL Server 2012 については、SQL Server 2012 オンラインブック () を参照してください [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。</span><span class="sxs-lookup"><span data-stu-id="90570-121">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="90570-122">他の必要なソフトウェアのサーバーへのインストール</span><span class="sxs-lookup"><span data-stu-id="90570-122">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="90570-123">Lync Server 2013 には、サーバーに次の追加ソフトウェアがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90570-123">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="90570-124">**Lync Server 2013 を実行しているサーバーの前提条件となるソフトウェア**    Lync Server 2013 を実行しているサーバーの追加ソフトウェアの前提条件は、展開されるサーバーの役割によって異なります。</span><span class="sxs-lookup"><span data-stu-id="90570-124">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="90570-125">各サーバーの特定のソフトウェア要件の詳細については、「計画」のドキュメントの「 [Lync server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90570-125">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="90570-126">**Windows Identity Foundation**    Lync Server 2013 では、サーバー間認証のシナリオをサポートするために、Windows Identity Foundation をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90570-126">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="90570-127">コンピューターに既にインストールされていることを確認するには、[コントロールパネル] の [ **プログラムと機能**] をクリックし、 **インストールされた更新プログラムを表示**して、[ **Microsoft Windows**] の下に表示します。</span><span class="sxs-lookup"><span data-stu-id="90570-127">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="90570-128">Windows Identity Foundation のインストールの詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。</span><span class="sxs-lookup"><span data-stu-id="90570-128">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="90570-129">**Microsoft .Net Framework 4.5**    Lync Server 2013 では、64ビット版の Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="90570-129">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="90570-130">**データベースサーバー**     の前提条件となるソフトウェアデータベースサーバーに必要な Windows Update (バックエンドデータベース、アーカイブデータベース、監視データベースなど) の詳細については、SQL Server 2012 のドキュメントを参照してください [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。</span><span class="sxs-lookup"><span data-stu-id="90570-130">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="90570-131">Lync Server 2013 は、各 Standard Edition サーバーと、ローカル構成ストアが配置されている Lync Server 2013 を実行している各サーバーに、Microsoft SQL Server 2012 Express を自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="90570-131">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="90570-132">**Windows Media フォーマットランタイム**    会議を展開するすべてのフロントエンドサーバーおよび Standard Edition サーバーには、Windows Media フォーマットランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90570-132">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="90570-133">コール パーク、アナウンス、応答グループの各アプリケーションがアナウンスと音楽を再生する Windows Media オーディオ (.wma) ファイルを実行するには、Windows Media フォーマット ランタイムが必要です。</span><span class="sxs-lookup"><span data-stu-id="90570-133">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="90570-134">Windows Server 2012 および Windows Server 2012 R2 では、Windows Media フォーマットランタイムが Microsoft Media Foundation と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="90570-134">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="90570-135">Windows Server &nbsp; 2008 および Windows server &nbsp; 2008 R2 の場合、Windows &nbsp; Media フォーマットランタイムは windows デスクトップ環境の一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="90570-135">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="90570-136">Lync Server 2013 をインストールする前に、Windows デスクトップ環境をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90570-136">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="90570-137">Lync Server 2013 がサーバー上でこのソフトウェアを見つけられない場合は、インストールを求めるメッセージが表示され、インストールを完了するためにサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90570-137">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

