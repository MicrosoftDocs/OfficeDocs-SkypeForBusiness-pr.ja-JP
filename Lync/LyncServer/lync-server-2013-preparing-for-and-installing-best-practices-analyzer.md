---
title: 'Lync Server 2013: ベストプラクティスアナライザーの準備とインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f5992b45d8930bac880f66422d10ddbd4b94f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="8f55c-102">Lync Server 2013 でのベストプラクティスアナライザーの準備とインストール</span><span class="sxs-lookup"><span data-stu-id="8f55c-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f55c-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8f55c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8f55c-104">このトピックで説明されているタスクを実行するには、管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f55c-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="8f55c-105">ベストプラクティスアナライザーをインストールするためのシステム要件</span><span class="sxs-lookup"><span data-stu-id="8f55c-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="8f55c-106">Lync Server 2013 のベストプラクティスアナライザーを実行して環境をスキャンするには、コンピューターで次のいずれかのオペレーティングシステムの64ビット版が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f55c-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="8f55c-107">Windows Server 2008 R2 Service Pack 1 (SP1) 標準オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="8f55c-108">Windows Server 2008 R2 SP1 Enterprise オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="8f55c-109">Windows Server 2008 R2 SP1 Datacenter オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="8f55c-110">Windows Server 2012 Datacenter オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="8f55c-111">Windows Server 2012 標準オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="8f55c-112">Windows Server 2012 エンタープライズオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="8f55c-113">Windows Server 2012 R2 Datacenter オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="8f55c-114">Windows Server 2012 R2 Standard オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="8f55c-115">Windows Server 2012 R2 Enterprise オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="8f55c-116">Windows 8 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="8f55c-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="8f55c-117">Windows 7 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="8f55c-117">Windows 7 operating system</span></span>

<span data-ttu-id="8f55c-118">コンピューターでは、次の操作も実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f55c-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="8f55c-119">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8f55c-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="8f55c-120">Lync Server 2013 の場合は、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f55c-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="8f55c-121">Lync Server 2013、コアコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="8f55c-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="8f55c-122">WMI の下位互換性パッケージ。</span><span class="sxs-lookup"><span data-stu-id="8f55c-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="8f55c-123">詳細については、「移行ドキュメントで[WMI 下位互換性パッケージをインストール](install-wmi-backward-compatibility-package.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f55c-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="8f55c-124">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="8f55c-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="8f55c-125">詳細については、「展開ドキュメントで[Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f55c-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8f55c-126">ベストプラクティスアナライザーは、Lync Server 2013、コアコンポーネント、または WMI 下位互換性パッケージを実行していないオペレーティングシステムがサポートされているコンピューターにインストールできますが、これらのコンピューターではベストプラクティスアナライザーを使ってレポートを表示することはできません。スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f55c-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="8f55c-127">インストールするコンピューターを選ぶ</span><span class="sxs-lookup"><span data-stu-id="8f55c-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="8f55c-128">Lync server 2013 のベストプラクティスアナライザーを Lync Server 2013 管理専用のコンピューターにインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f55c-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="8f55c-129">Lync Server 2013 を実行しているサーバー、または Lync Server 2013 管理ツールを実行している管理コンピューターにツールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f55c-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="8f55c-130">Lync Server を実行しているサーバーにツールをインストールする場合は、このツールを使用してそのサーバーのみをスキャンすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f55c-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="8f55c-131">ベストプラクティスアナライザーをインストールする</span><span class="sxs-lookup"><span data-stu-id="8f55c-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="8f55c-132">Lync Server 2013 のベストプラクティスアナライザーをダウンロードでき[http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)ます。</span><span class="sxs-lookup"><span data-stu-id="8f55c-132">You can download the Best Practices Analyzer for Lync Server 2013 at [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="8f55c-133">ベストプラクティスアナライザーをインストールするには、ツールをインストールするコンピューターで Microsoft インストーラーファイル RtcBPA .msi を起動し、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="8f55c-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="8f55c-134">プログラムファイルをインストールするための既定の\<場所は\>\\、システム\\ドライブのプログラム\\ファイル Lync Server 2013 BPA です。</span><span class="sxs-lookup"><span data-stu-id="8f55c-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

