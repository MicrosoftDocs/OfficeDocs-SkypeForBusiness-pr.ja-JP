---
title: 'Lync Server 2013: Lync Server 2013 を実行しているサーバーのシステム要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d25be2132fdaba58024ba58081656b830ea9fe4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497334"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="96a69-102">Lync Server 2013 を実行しているサーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="96a69-102">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96a69-103">_**トピックの最終更新日:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="96a69-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="96a69-104">ハードウェア要件の詳細については、「 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 のサーバーハードウェアプラットフォーム</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96a69-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="96a69-105">Standard Edition と Enterprise Edition のサーバーは、同じソフトウェア要件を共有します。</span><span class="sxs-lookup"><span data-stu-id="96a69-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="96a69-106">Lync Server 2013 Enterprise Edition を実行しているサーバーは、主要な組織の展開として大規模な組織を対象としています。</span><span class="sxs-lookup"><span data-stu-id="96a69-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="96a69-107">Enterprise Edition サーバーは、1 プールにつき、約 80,000 の所属ユーザーまでの拡張性を有するよう、設計されています。</span><span class="sxs-lookup"><span data-stu-id="96a69-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="96a69-108">Lync Server 2013 の Standard Edition を実行しているサーバーは、小規模な組織と、メインの組織展開から離れた場所を対象としています。</span><span class="sxs-lookup"><span data-stu-id="96a69-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="96a69-109">1組の Standard Edition サーバーは、最大5000ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="96a69-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="96a69-110">Standard Edition サーバーと Enterprise Edition サーバーの相違点の詳細については、「 [Deployment の概要 (Lync Server 2013](lync-server-2013-deployment-overview.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96a69-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="96a69-111">オペレーティング システムのインストール</span><span class="sxs-lookup"><span data-stu-id="96a69-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="96a69-112">Lync Server 2013 は、64ビット版でのみ使用できます。これには、64ビットハードウェアと、Windows Server オペレーティングシステムの64ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="96a69-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="96a69-113">このリリースでは、32ビット版の Lync Server 2013 は利用できません。</span><span class="sxs-lookup"><span data-stu-id="96a69-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="96a69-114">Standard Edition および Enterprise Edition サーバーでは、次のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="96a69-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="96a69-115">Windows Server 2008 R2 SP1 または最新のサービスパック</span><span class="sxs-lookup"><span data-stu-id="96a69-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="96a69-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="96a69-116">Windows Server 2012</span></span>

  - <span data-ttu-id="96a69-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="96a69-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="96a69-118">Standard Edition サーバーまたは Enterprise Edition フロントエンドサーバーに、オペレーティングシステムソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="96a69-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="96a69-119">オペレーティング システムを最新の状態にするため、そして組織の標準に沿うのに必要な更新レベルにするために、すべての変更プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="96a69-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="96a69-120">操作要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96a69-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] 
> <span data-ttu-id="96a69-121">Lync Server 2013 では、オペレーティングシステムの一括アップグレードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="96a69-121">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="96a69-122">別のプールを展開し、ユーザーを別のオペレーティングシステムを使用して新しいプールに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96a69-122">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="96a69-123">Windows Server 2012 R2 で Lync Server 2013 を動作させるには、Windows Server でレジストリキーの値を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="96a69-123">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="96a69-124">この変更は、証明書が正常に機能し、クライアントが存続可能 Branch アプライアンスに登録するために必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="96a69-124">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="96a69-125">詳細については、「」を参照してください <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> 。</span><span class="sxs-lookup"><span data-stu-id="96a69-125">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="96a69-126">Lync Server 2013 の追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="96a69-126">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="96a69-127">オペレーティングシステムに必要な更新プログラムに加えて、Lync Server 2013 では、オペレーティングシステムの役割、機能、およびソフトウェアを運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96a69-127">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="96a69-128">トポロジを公開して Lync Server 2013 をインストールする前にインストールする必要がある追加ソフトウェアの詳細については、「計画」のドキュメントの「 [Lync server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96a69-128">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="96a69-129">すべてのサーバーの役割に必要な追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="96a69-129">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="96a69-130">すべてのサーバーの役割についても、Windows PowerShell コマンドラインインターフェイス3.0 と Microsoft .NET Framework 4.5 がインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96a69-130">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="96a69-131">また、Lync Server 管理ツールを実行するコンピューターでは、Windows PowerShell コマンドラインインターフェイス3.0 と Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="96a69-131">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="96a69-132">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="96a69-132">Windows PowerShell 3.0</span></span>

<span data-ttu-id="96a69-133">Lync Server 2013 では、Lync Server トポロジに参加する各コンピューターに Windows PowerShell 3.0 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96a69-133">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="96a69-134">Windows PowerShell 3.0 のインストールの詳細については、「 [Windows powershell 3.0 を Lync Server 2013 にインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96a69-134">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="96a69-135">Windows Server &nbsp; 2008 &nbsp; R2 SP1 では、Microsoft .net Framework 4.5 をインストールする前に、windows PowerShell コマンドラインインターフェイス3.0 をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="96a69-135">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="96a69-136">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="96a69-136">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="96a69-137">Windows Server 2012 または Windows Server 2012 R2 上で Lync Server 2013 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールする場合は、1つの追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96a69-137">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="96a69-138">.NET Framework 4.5 をインストールした後、サーバーマネージャーを使用して HTTP アクティブ化をインストールします。</span><span class="sxs-lookup"><span data-stu-id="96a69-138">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="96a69-139">**Windows Server 2012 または Windows Server 2012 R2 に .NET 4.5 HTTP ライセンス認証をインストールするには**</span><span class="sxs-lookup"><span data-stu-id="96a69-139">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="96a69-140">[ **スタート** ] メニューの [ **プログラム**] をクリックし、[ **管理ツール**] をクリックして、[ **サーバーマネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96a69-140">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="96a69-141">サーバーマネージャーの [ **機能の概要**] で、[ **機能の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96a69-141">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="96a69-142">[ **.Net Framework 4.5**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="96a69-142">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="96a69-143">まだ選択されていない場合は、[ **WCF アクティブ化** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96a69-143">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="96a69-144">[ **HTTP アクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96a69-144">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="96a69-145">[ **次へ** ] をクリックし、画面の指示に従ってインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="96a69-145">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

