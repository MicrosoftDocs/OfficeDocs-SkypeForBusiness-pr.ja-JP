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
ms.openlocfilehash: 6c97657b42ec4ea26f5300b1d28215d0360b63cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="e8ecb-102">Lync Server 2013 でのベストプラクティスアナライザーの準備とインストール</span><span class="sxs-lookup"><span data-stu-id="e8ecb-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8ecb-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e8ecb-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e8ecb-104">このトピックで説明するタスクを実行するには、Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="e8ecb-105">ベスト プラクティス アナライザーをインストールするためのシステム要件</span><span class="sxs-lookup"><span data-stu-id="e8ecb-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="e8ecb-106">Lync Server 2013 を実行するには、ベストプラクティスアナライザーを使用して環境をスキャンするには、次のいずれかのオペレーティングシステムの64ビット版がコンピューターで実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="e8ecb-107">Windows Server 2008 R2 Service Pack 1 (SP1) Standard オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="e8ecb-108">Windows Server 2008 R2 SP1 エンタープライズオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="e8ecb-109">Windows Server 2008 R2 SP1 Datacenter オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="e8ecb-110">Windows Server 2012 Datacenter オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="e8ecb-111">Windows Server 2012 Standard オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="e8ecb-112">Windows Server 2012 エンタープライズオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="e8ecb-113">Windows Server 2012 R2 Datacenter オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="e8ecb-114">Windows Server 2012 R2 Standard オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="e8ecb-115">Windows Server 2012 R2 Enterprise オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="e8ecb-116">Windows 8 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="e8ecb-117">Windows 7 オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="e8ecb-117">Windows 7 operating system</span></span>

<span data-ttu-id="e8ecb-118">また、以下も実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="e8ecb-119">Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="e8ecb-120">Lync server 2013 の場合は、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="e8ecb-121">Lync Server 2013、コアコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="e8ecb-122">WMI 下位互換パッケージ。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="e8ecb-123">詳細については、「移行」のドキュメントの「 [INSTALL WMI 下位互換パッケージをインストール](install-wmi-backward-compatibility-package.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="e8ecb-124">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="e8ecb-125">詳細については、「展開」のドキュメントの「 [Windows PowerShell 3.0 For Lync Server 2013 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e8ecb-126">ベストプラクティスアナライザーは、Lync Server 2013、コアコンポーネント、または WMI 下位互換パッケージを実行していない、サポートされているオペレーティングシステムを搭載したコンピューターにインストールできますが、これらのコンピューターでベストプラクティスアナライザーを使用しても、レポートを表示することはできません。スキャンを実行する。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="e8ecb-127">インストール対象のコンピューターの選択</span><span class="sxs-lookup"><span data-stu-id="e8ecb-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="e8ecb-128">Lync server 2013 管理専用のコンピューターに Lync Server 2013、ベストプラクティスアナライザーをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="e8ecb-129">Lync Server 2013 を実行しているサーバー、または Lync Server 2013 管理ツールを実行している管理コンピューターに、ツールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="e8ecb-130">Lync Server を実行しているサーバーにツールをインストールする場合は、ツールを使用してそのサーバーのみをスキャンすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="e8ecb-131">ベスト プラクティス アナライザーのインストール</span><span class="sxs-lookup"><span data-stu-id="e8ecb-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="e8ecb-132">Lync Server 2013 のベストプラクティスアナライザーをダウンロードすることが[http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)できます。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-132">You can download the Best Practices Analyzer for Lync Server 2013 at [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="e8ecb-133">ベスト プラクティス アナライザーをインストールするには、ツールをインストールするコンピューターで Microsoft インストーラー ファイル (RtcBPA.msi) を起動し、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="e8ecb-134">プログラムファイルをインストールする既定の場所は\<、システム\>\\ドライブの\\プログラムファイル Lync\\Server 2013 BPA です。</span><span class="sxs-lookup"><span data-stu-id="e8ecb-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

