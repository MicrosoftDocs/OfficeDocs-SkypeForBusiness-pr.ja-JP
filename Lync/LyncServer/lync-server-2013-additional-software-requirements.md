---
title: 'Lync Server 2013: 追加のソフトウェア要件'
description: 'Lync Server 2013: 追加のソフトウェア要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbc36f23a2246c9d653e47954064182c756f0dff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553043"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="72404-103">Lync Server 2013 の追加ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="72404-103">Additional software requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72404-104">_**トピックの最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="72404-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="72404-105">Lync Server 2013 では、サーバープラットフォームのハードウェアとオペレーティングシステムの要件に加えて、展開するサーバーに追加のソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-105">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72404-106">Lync Server を実行しているサーバーのプラットフォーム要件の詳細については、「lync server <A href="lync-server-2013-server-hardware-platforms.md">2013 のサーバーハードウェアプラットフォーム</A> 」および「 <A href="lync-server-2013-server-and-tools-operating-system-support.md">lync Server 2013 のサーバーおよびツールのオペレーティングシステムのサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72404-106">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="72404-107">クライアントコンピューターとデバイスのシステム要件の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-clients-and-devices.md">planning for clients and devices In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72404-107">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="72404-108">管理ツールのソフトウェア要件の詳細については、「 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 の管理ツールのソフトウェア要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72404-108">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="72404-109">すべての内部サーバーの役割に必要な追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="72404-109">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="72404-110">このセクションでは、すべての内部サーバーの役割に必要なソフトウェアを一覧表示します。これは、エッジサーバーを除くすべての Lync Server サーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="72404-110">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="72404-111">エッジサーバーとエッジプールの要件については、このトピックで後述する「 **エッジサーバーの追加ソフトウェア**」を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="72404-111">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="72404-112">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="72404-112">Windows PowerShell 3.0</span></span>

<span data-ttu-id="72404-113">Lync Server 2013 を実行している各サーバーに、正しいリリースの Windows PowerShell 3.0 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-113">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="72404-114">詳細については、「 [Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72404-114">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="72404-115">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="72404-115">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="72404-116">Lync Server には、すべての内部サーバーの役割に Microsoft .NET Framework 4.5 が必要です。また、Lync Server 管理ツールまたは Microsoft Lync Server 2013、計画ツールを実行するすべてのコンピューターで、Microsoft .NET Framework が必要です。</span><span class="sxs-lookup"><span data-stu-id="72404-116">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="72404-117">Lync server 2013 の場合は、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-117">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="72404-118">これを手動でインストールするには、microsoft ダウンロードセンターから Microsoft .NET 4.5 Framework をダウンロードしてください。 [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="72404-118">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="72404-119">Windows Server 2012 を実行しているサーバーに Microsoft .NET Framework 4.5 をインストールする</span><span class="sxs-lookup"><span data-stu-id="72404-119">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="72404-120">Lync Server 2013 および Windows Server 2012 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールする場合は、1つの追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-120">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="72404-121">.NET Framework 4.5 をインストールした後、サーバーマネージャーを使用して HTTP アクティブ化をインストールします。</span><span class="sxs-lookup"><span data-stu-id="72404-121">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="72404-122">**Windows Server 2012 に .NET 4.5 HTTP ライセンス認証をインストールするには**</span><span class="sxs-lookup"><span data-stu-id="72404-122">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="72404-123">[ **スタート** ] メニューの [ **プログラム**] をクリックし、[ **管理ツール**] をクリックして、[ **サーバーマネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72404-123">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="72404-124">サーバーマネージャーの [ **機能の概要**] で、[ **機能の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-124">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="72404-125">[ **.Net Framework 4.5**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="72404-125">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="72404-126">まだ選択されていない場合は、[ **WCF アクティブ化** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-126">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="72404-127">[ **HTTP アクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-127">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="72404-128">[ **次へ** ] をクリックし、画面の指示に従ってインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="72404-128">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="72404-129">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="72404-129">Windows Identity Foundation</span></span>

<span data-ttu-id="72404-130">Lync Server 2013 の**Windows Identity foundation**では、サーバー間の認証シナリオをサポートするために Windows identity foundation をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-130">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="72404-131">Windows Server 2008 R2 および Windows Server 2012 には、Windows 識別基盤をインストールするための異なる手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="72404-131">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="72404-132">次の一覧から、サーバーオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-132">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="72404-133">Windows Server 2008 R2 For Windows Server 2008 R2 コンピューターに既にインストールされているかどうかを確認するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="72404-133">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="72404-134">これを行うには、「**プログラムの追加と削除**」、「**インストール済みの更新プログラムの表示**」の順に移動して、WINDOWS **Identity Foundation (KB974405)\*\*\*\*のエントリ**を確認します。</span><span class="sxs-lookup"><span data-stu-id="72404-134">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="72404-135">Windows Identity Foundation のインストールの詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。</span><span class="sxs-lookup"><span data-stu-id="72404-135">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="72404-136">Windows server 2012 For Windows server 2012 では、 **サーバーマネージャー** を使用して Windows Identity Foundation をインストールします。</span><span class="sxs-lookup"><span data-stu-id="72404-136">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="72404-137">サーバーマネージャーの **役割と機能の追加ウィザード**で、[ **機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-137">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="72404-138">一覧から [ **Windows Identity Foundation 3.5** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-138">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="72404-139">[ **次へ**] をクリックし、[ **インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72404-139">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="72404-140">すべてのフロントエンドサーバーおよび Standard Edition サーバーの追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="72404-140">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="72404-141">また、すべてのフロントエンドサーバーと Standard Edition サーバーで、特定のモジュールを使用してインターネットインフォメーションサービス (IIS) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-141">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="72404-142">また、会議、コールパークアプリケーション、アナウンス、または応答グループが展開されているすべてのフロントエンドサーバーおよび Standard Edition サーバーは、Windows Media フォーマットランタイムを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-142">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="72404-143">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="72404-143">Internet Information Services (IIS)</span></span>

<span data-ttu-id="72404-144">フロントエンドサーバーおよび Standard Edition サーバーは、次のモジュールを使用してインターネットインフォメーションサービス (IIS) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-144">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="72404-145">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="72404-145">Static Content</span></span>

  - <span data-ttu-id="72404-146">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="72404-146">Default Document</span></span>

  - <span data-ttu-id="72404-147">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="72404-147">HTTP Errors</span></span>

  - <span data-ttu-id="72404-148">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72404-148">ASP.NET</span></span>

  - <span data-ttu-id="72404-149">.NET 拡張機能</span><span class="sxs-lookup"><span data-stu-id="72404-149">.NET Extensibility</span></span>

  - <span data-ttu-id="72404-150">Internet Server API (ISAPI) 拡張機能</span><span class="sxs-lookup"><span data-stu-id="72404-150">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="72404-151">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="72404-151">ISAPI Filters</span></span>

  - <span data-ttu-id="72404-152">HTTP ロギング機能</span><span class="sxs-lookup"><span data-stu-id="72404-152">HTTP Logging</span></span>

  - <span data-ttu-id="72404-153">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="72404-153">Logging Tools</span></span>

  - <span data-ttu-id="72404-154">・</span><span class="sxs-lookup"><span data-stu-id="72404-154">Tracing</span></span>

  - <span data-ttu-id="72404-155">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="72404-155">Windows Authentication</span></span>

  - <span data-ttu-id="72404-156">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="72404-156">Request Filtering</span></span>

  - <span data-ttu-id="72404-157">静的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="72404-157">Static Content Compression</span></span>

  - <span data-ttu-id="72404-158">動的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="72404-158">Dynamic Content Compression</span></span>

  - <span data-ttu-id="72404-159">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="72404-159">IIS Management Console</span></span>

  - <span data-ttu-id="72404-160">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="72404-160">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="72404-161">匿名認証 (IIS のインストール時に既定でインストールされます)</span><span class="sxs-lookup"><span data-stu-id="72404-161">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="72404-162">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="72404-162">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="72404-163">Windows Media フォーマットランタイムと Windows デスクトップでの作業</span><span class="sxs-lookup"><span data-stu-id="72404-163">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="72404-164">**Windows デスクトップ環境** 会議を展開するすべてのフロントエンドサーバーおよび Standard Edition サーバーには、windows Media フォーマットランタイムがインストールされている必要があります。これは、windows Server 2012 を除き、windows デスクトップ環境の一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="72404-164">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="72404-165">Windows Server 2012 には、Microsoft Media Foundation が必要です。</span><span class="sxs-lookup"><span data-stu-id="72404-165">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="72404-166">コール パーク、アナウンス、応答グループの各アプリケーションがアナウンスと音楽を再生する Windows Media オーディオ (.wma) ファイルを実行するには、Windows Media フォーマット ランタイムが必要です。</span><span class="sxs-lookup"><span data-stu-id="72404-166">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="72404-167">Lync Server 2013 をインストールする前に、Windows デスクトップ環境をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="72404-167">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="72404-168">Lync Server 2013 がサーバー上でこのソフトウェアを見つけられない場合は、インストールを求めるメッセージが表示され、インストールを完了するためにサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-168">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="72404-169">Windows Server 2012 上で実行されているフロントエンドサーバーおよび Standard Edition サーバーの追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="72404-169">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="72404-170">フロントエンドサーバーには、Windows Server 2012 に既定でインストールされていない .NET 3.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="72404-170">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="72404-171">インストールするには、Windows Server 2012 インストールメディアをドライブ D に挿入し、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="72404-171">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="72404-172">Windows Server 2012 を実行しているサーバーへの .NET 3.5 のインストールの詳細については、「」の「Microsoft .NET Framework 3.5 の展開に関する考慮事項」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=275032> 。</span><span class="sxs-lookup"><span data-stu-id="72404-172">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="72404-173">ディレクターの追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="72404-173">Additional Software for Directors</span></span>

<span data-ttu-id="72404-174">ディレクターは、次のモジュールを使用してインターネットインフォメーションサービス (IIS) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-174">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="72404-175">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="72404-175">Static Content</span></span>

  - <span data-ttu-id="72404-176">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="72404-176">Default Document</span></span>

  - <span data-ttu-id="72404-177">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="72404-177">HTTP Errors</span></span>

  - <span data-ttu-id="72404-178">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72404-178">ASP.NET</span></span>

  - <span data-ttu-id="72404-179">.NET 拡張機能</span><span class="sxs-lookup"><span data-stu-id="72404-179">.NET Extensibility</span></span>

  - <span data-ttu-id="72404-180">Internet Server API (ISAPI) 拡張機能</span><span class="sxs-lookup"><span data-stu-id="72404-180">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="72404-181">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="72404-181">ISAPI Filters</span></span>

  - <span data-ttu-id="72404-182">HTTP ロギング機能</span><span class="sxs-lookup"><span data-stu-id="72404-182">HTTP Logging</span></span>

  - <span data-ttu-id="72404-183">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="72404-183">Logging Tools</span></span>

  - <span data-ttu-id="72404-184">・</span><span class="sxs-lookup"><span data-stu-id="72404-184">Tracing</span></span>

  - <span data-ttu-id="72404-185">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="72404-185">Windows Authentication</span></span>

  - <span data-ttu-id="72404-186">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="72404-186">Request Filtering</span></span>

  - <span data-ttu-id="72404-187">静的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="72404-187">Static Content Compression</span></span>

  - <span data-ttu-id="72404-188">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="72404-188">IIS Management Console</span></span>

  - <span data-ttu-id="72404-189">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="72404-189">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="72404-190">匿名認証 (IIS のインストール時に既定でインストールされます)</span><span class="sxs-lookup"><span data-stu-id="72404-190">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="72404-191">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="72404-191">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="72404-192">常設チャットフロントエンドサーバー用の追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="72404-192">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="72404-193">常設チャットフロントエンドサーバーは、Windows Server のコンポーネントであるメッセージキュー (MSMQ とも呼ばれます) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-193">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="72404-194">MSMQ を有効にする方法については、 [ここをクリックしてください。](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="72404-194">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="72404-195">エッジサーバーの追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="72404-195">Additional Software for Edge Servers</span></span>

<span data-ttu-id="72404-196">エッジサーバーには、次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="72404-196">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="72404-197">Lync Server 2013 を実行している各サーバーに、正しいリリースの Windows PowerShell 3.0 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-197">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="72404-198">詳細については、「 [Lync Server 2013 用の Windows PowerShell 3.0 のインストール](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72404-198">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="72404-199">Lync Server には Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="72404-199">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="72404-200">Windows Server 2008 R2 にインストールされている Lync Server 2013 では、Lync 2013 Server をインストールする前に、サーバーに Microsoft .NET Framework 4.5 の64ビットエディションを手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-200">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="72404-201">これを手動でインストールするには、microsoft ダウンロードセンターから Microsoft .NET 4.5 Framework をダウンロードしてください。 [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="72404-201">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="72404-202">Lync Server 2013 の**Windows Identity foundation**では、サーバー間の認証シナリオをサポートするために Windows identity foundation をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72404-202">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="72404-203">Windows Server 2008 R2 および Windows Server 2012 には、Windows 識別基盤をインストールするための異なる手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="72404-203">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="72404-204">次の一覧から、サーバーオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-204">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="72404-205">Windows Server 2008 R2 For Windows Server 2008 R2 コンピューターに既にインストールされているかどうかを確認するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="72404-205">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="72404-206">これを行うには、「**プログラムの追加と削除**」、「**インストール済みの更新プログラムの表示**」の順に移動して、WINDOWS **Identity Foundation (KB974405)\*\*\*\*のエントリ**を確認します。</span><span class="sxs-lookup"><span data-stu-id="72404-206">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="72404-207">Windows Identity Foundation のインストールの詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。</span><span class="sxs-lookup"><span data-stu-id="72404-207">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="72404-208">Windows server 2012 For Windows server 2012 では、 **サーバーマネージャー** を使用して Windows Identity Foundation をインストールします。</span><span class="sxs-lookup"><span data-stu-id="72404-208">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="72404-209">サーバーマネージャーの **役割と機能の追加ウィザード**で、[ **機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-209">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="72404-210">一覧から [ **Windows Identity Foundation 3.5** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72404-210">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="72404-211">[ **次へ**] をクリックし、[ **インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72404-211">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="72404-212">複数層ソケット プロバイダーをメディア サーバーにインストールしないこと</span><span class="sxs-lookup"><span data-stu-id="72404-212">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="72404-213">任意のフロントエンドサーバーまたはスタンドアロンの仲介サーバーに、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバークライアントソフトウェア、またはその他の Winsock 階層サービスプロバイダ (LSP) ソフトウェアをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="72404-213">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="72404-214">このソフトウェアをインストールすると、メディアトラフィックのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="72404-214">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72404-215">関連項目</span><span class="sxs-lookup"><span data-stu-id="72404-215">See Also</span></span>


[<span data-ttu-id="72404-216">Lync Server 2013 の管理ツールソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="72404-216">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

