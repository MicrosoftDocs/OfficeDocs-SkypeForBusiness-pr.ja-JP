---
title: 'Lync Server 2013: Lync Server 2013 を実行するサーバーのシステム要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="b15be-102">Lync Server 2013 を実行するサーバーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="b15be-102">System requirements for servers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b15be-103">_**最終更新日:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="b15be-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b15be-104">ハードウェア要件の詳細については、「 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 用のサーバーハードウェアプラットフォーム</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b15be-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b15be-105">Standard Edition と Enterprise Edition のサーバーは、同じソフトウェア要件を共有します。</span><span class="sxs-lookup"><span data-stu-id="b15be-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="b15be-106">Lync Server 2013、Enterprise Edition を実行しているサーバーは、主要な組織の展開として大規模な組織向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="b15be-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="b15be-107">Enterprise Edition server は、1つのプールあたり約8万のホームユーザーに対応するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b15be-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="b15be-108">Lync Server 2013、Standard エディションを実行しているサーバーは、組織の主要な展開によって小規模の組織やリモートの場所を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b15be-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="b15be-109">標準エディションのサーバーの1組は、最大5000ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="b15be-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="b15be-110">Standard Edition server と Enterprise Edition サーバーの違いの詳細については、「 [Lync Server 2013 の展開の概要](lync-server-2013-deployment-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b15be-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="b15be-111">オペレーティングシステムのインストール</span><span class="sxs-lookup"><span data-stu-id="b15be-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b15be-112">Lync Server 2013 は、64ビット版でのみ使用できます。これには、64ビットハードウェアと Windows Server オペレーティングシステムの64ビット版が必要です。</span><span class="sxs-lookup"><span data-stu-id="b15be-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="b15be-113">このリリースでは、32ビット版の Lync Server 2013 は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b15be-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="b15be-114">Standard Edition server および Enterprise Edition server では、次のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b15be-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="b15be-115">Windows Server 2008 R2 SP1 または最新の service pack</span><span class="sxs-lookup"><span data-stu-id="b15be-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="b15be-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b15be-116">Windows Server 2012</span></span>

  - <span data-ttu-id="b15be-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b15be-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="b15be-118">Standard Edition Server または Enterprise Edition のフロントエンドサーバーに、オペレーティングシステムソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b15be-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="b15be-119">すべての更新プログラムを適用して、オペレーティングシステムを最新の更新プログラムおよび必須の更新レベルにして、組織の標準に準拠させます。</span><span class="sxs-lookup"><span data-stu-id="b15be-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="b15be-120">操作要件の詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b15be-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b15be-121">Lync Server 2013 を Windows Server 2012 R2 で動作させるには、Windows Server でレジストリキーの値を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b15be-121">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="b15be-122">この変更は、証明書が正しく動作するために必要な場合があり、クライアントが Survivable Branch アプライアンスに登録します。</span><span class="sxs-lookup"><span data-stu-id="b15be-122">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="b15be-123">詳細については<A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b15be-123">For more information, see <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="b15be-124">Lync Server 2013 のその他のソフトウェア</span><span class="sxs-lookup"><span data-stu-id="b15be-124">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="b15be-125">Lync Server 2013 では、オペレーティングシステムに必要な更新に加えて、オペレーティングシステムの役割、機能、およびソフトウェアの操作が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b15be-125">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="b15be-126">トポロジを公開して Lync Server 2013 をインストールする前にインストールする必要があるその他のソフトウェアの詳細については、計画ドキュメントの「 [Lync server 2013 のその他のソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b15be-126">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="b15be-127">すべてのサーバーの役割に必要なその他のソフトウェア</span><span class="sxs-lookup"><span data-stu-id="b15be-127">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="b15be-128">すべてのサーバーの役割では、Windows PowerShell コマンドラインインターフェイス3.0 と Microsoft .NET Framework 4.5 がインストールされていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b15be-128">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="b15be-129">さらに、Lync Server 管理ツールを実行するコンピューターでは、Windows PowerShell コマンドラインインターフェイス3.0 と Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="b15be-129">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="b15be-130">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="b15be-130">Windows PowerShell 3.0</span></span>

<span data-ttu-id="b15be-131">Lync Server 2013 では、Lync Server のトポロジに参加する各コンピューターに Windows PowerShell 3.0 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b15be-131">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="b15be-132">Windows PowerShell 3.0 のインストールの詳細については、「 [Lync Server 2013 用に Windows powershell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b15be-132">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b15be-133">Windows Server&nbsp;2008&nbsp;R2 SP1 では、Microsoft .net Framework 4.5 をインストールする前に windows PowerShell コマンドラインインターフェイス3.0 をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b15be-133">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="b15be-134">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b15be-134">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="b15be-135">Windows Server 2012 または Windows Server 2012 R2 で Lync Server 2013 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールする場合は、追加の手順を1つ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b15be-135">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="b15be-136">.NET Framework 4.5 がインストールされたら、サーバーマネージャーを使用して、HTTP アクティブ化をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b15be-136">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="b15be-137">**Windows Server 2012 または Windows Server 2012 R2 で .NET 4.5 HTTP ライセンス認証をインストールするには**</span><span class="sxs-lookup"><span data-stu-id="b15be-137">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="b15be-138">[**スタート**] メニューで、[**プログラム**]、[**管理ツール**]、[**サーバーマネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b15be-138">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="b15be-139">サーバーマネージャーの [**機能の概要**] で、[**機能の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b15be-139">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="b15be-140">**.Net Framework 4.5**を展開します。</span><span class="sxs-lookup"><span data-stu-id="b15be-140">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="b15be-141">まだ選択されていない場合は、[ **WCF ライセンス認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b15be-141">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="b15be-142">次に、[ **HTTP ライセンス認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b15be-142">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="b15be-143">[**次へ**] をクリックし、画面の指示に従ってインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="b15be-143">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

