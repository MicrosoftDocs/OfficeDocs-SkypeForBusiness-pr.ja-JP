---
title: 'Lync Server 2013: 追加ソフトウェア要件'
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
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="d0509-102">Lync Server 2013 の追加ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="d0509-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0509-103">_**最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="d0509-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="d0509-104">Lync Server 2013 では、サーバープラットフォームのハードウェアとオペレーティングシステムの要件に加えて、展開するサーバーに追加のソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0509-105">Lync Server を実行しているサーバーのプラットフォーム要件の詳細については、「lync <A href="lync-server-2013-server-hardware-platforms.md">server 2013 のサーバーハードウェアプラットフォーム</A>」および「 <A href="lync-server-2013-server-and-tools-operating-system-support.md">lync Server 2013 のサーバーとツールのオペレーティングシステムのサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="d0509-106">クライアントコンピューターとデバイスのシステム要件の詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 でのクライアントとデバイスの計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="d0509-107">管理ツールのソフトウェア要件の詳細については、「 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 での管理ツールのソフトウェア要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="d0509-108">すべての内部サーバーの役割に必要なその他のソフトウェア</span><span class="sxs-lookup"><span data-stu-id="d0509-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="d0509-109">このセクションでは、すべての内部サーバーロールで必要なソフトウェアの一覧を示します。これは、エッジサーバーを除くすべての Lync Server server ロールです。</span><span class="sxs-lookup"><span data-stu-id="d0509-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="d0509-110">エッジサーバーとエッジプールの要件については、このトピックの「**エッジサーバー向けの追加ソフトウェア**」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="d0509-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="d0509-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="d0509-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="d0509-112">Lync Server 2013 を実行している各サーバーには、正しいバージョンの Windows PowerShell 3.0 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="d0509-113">詳細については、「 [Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="d0509-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d0509-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="d0509-115">Lync Server を使用するには、社内のすべてのサーバーの役割、および Lync Server 管理ツールまたは Microsoft Lync Server 2013、計画ツールを実行するすべてのコンピューターで Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0509-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="d0509-116">Lync Server 2013 の場合は、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="d0509-117">手動でインストールするには、microsoft ダウンロードセンターから Microsoft .NET 4.5 フレームワークをダウンロードしてください。[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="d0509-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="d0509-118">Windows Server 2012 を実行しているサーバーに Microsoft .NET Framework 4.5 をインストールする</span><span class="sxs-lookup"><span data-stu-id="d0509-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="d0509-119">Lync Server 2013 と Windows Server 2012 を実行するサーバーに Microsoft .NET Framework 4.5 をインストールする場合は、追加の手順を1つ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="d0509-120">.NET Framework 4.5 がインストールされたら、サーバーマネージャーを使用して、HTTP アクティブ化をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d0509-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="d0509-121">**Windows Server 2012 で .NET 4.5 HTTP ライセンス認証をインストールするには**</span><span class="sxs-lookup"><span data-stu-id="d0509-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="d0509-122">[**スタート**] メニューで、[**プログラム**]、[**管理ツール**]、[**サーバーマネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0509-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="d0509-123">サーバーマネージャーの [**機能の概要**] で、[**機能の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0509-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="d0509-124">**.Net Framework 4.5**を展開します。</span><span class="sxs-lookup"><span data-stu-id="d0509-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="d0509-125">まだ選択されていない場合は、[ **WCF ライセンス認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0509-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="d0509-126">次に、[ **HTTP ライセンス認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0509-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="d0509-127">[**次へ**] をクリックし、画面の指示に従ってインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="d0509-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="d0509-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="d0509-128">Windows Identity Foundation</span></span>

<span data-ttu-id="d0509-129">Lync Server 2013 の**Windows Identity foundation**では、サーバー間の認証シナリオをサポートするために、Windows id ファンデーションをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="d0509-130">Windows Server 2008 R2 および Windows Server 2012 では、Windows Id 基盤をインストールするために異なる手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d0509-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="d0509-131">次の一覧からサーバーのオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0509-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="d0509-132">Windows server 2008 R2 For Windows Server 2008 R2 では、既にコンピューターにインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0509-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="d0509-133">これを行うには、「**プログラムの追加と削除**」、「**インストールされている更新プログラムを表示**」の各項目にアクセスして、「 **windows** **id ファンデーション (KB974405)**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="d0509-134">Windows Id Foundation のインストールの詳細につい[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="d0509-135">Windows server 2012 For Windows Server 2012 では、**サーバーマネージャー**を使って Windows Identity Foundation をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d0509-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="d0509-136">サーバーマネージャーの**役割と機能の追加ウィザード**で、[**機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0509-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="d0509-137">一覧から [ **Windows Id Foundation 3.5** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d0509-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="d0509-138">[**次へ**] をクリックし、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0509-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="d0509-139">すべてのフロントエンドサーバーおよび標準エディションサーバー向けの追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="d0509-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="d0509-140">すべてのフロントエンドサーバーと Standard Edition サーバーでは、特定のモジュールでインターネットインフォメーションサービス (IIS) を実行する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d0509-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="d0509-141">さらに、会議、コールパークアプリケーション、お知らせ、または応答グループが展開されているすべてのフロントエンドサーバーおよび標準エディションサーバーは、Windows Media Format Runtime を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="d0509-142">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="d0509-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="d0509-143">フロントエンドサーバーと Standard Edition サーバーでは、次のモジュールを使用して、インターネットインフォメーションサービス (IIS) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="d0509-144">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d0509-144">Static Content</span></span>

  - <span data-ttu-id="d0509-145">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="d0509-145">Default Document</span></span>

  - <span data-ttu-id="d0509-146">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="d0509-146">HTTP Errors</span></span>

  - <span data-ttu-id="d0509-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d0509-147">ASP.NET</span></span>

  - <span data-ttu-id="d0509-148">.NET の拡張性</span><span class="sxs-lookup"><span data-stu-id="d0509-148">.NET Extensibility</span></span>

  - <span data-ttu-id="d0509-149">Internet Server API (ISAPI) の拡張機能</span><span class="sxs-lookup"><span data-stu-id="d0509-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="d0509-150">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="d0509-150">ISAPI Filters</span></span>

  - <span data-ttu-id="d0509-151">HTTP ログ</span><span class="sxs-lookup"><span data-stu-id="d0509-151">HTTP Logging</span></span>

  - <span data-ttu-id="d0509-152">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="d0509-152">Logging Tools</span></span>

  - <span data-ttu-id="d0509-153">トレース</span><span class="sxs-lookup"><span data-stu-id="d0509-153">Tracing</span></span>

  - <span data-ttu-id="d0509-154">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="d0509-154">Windows Authentication</span></span>

  - <span data-ttu-id="d0509-155">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="d0509-155">Request Filtering</span></span>

  - <span data-ttu-id="d0509-156">静的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="d0509-156">Static Content Compression</span></span>

  - <span data-ttu-id="d0509-157">動的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="d0509-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="d0509-158">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="d0509-158">IIS Management Console</span></span>

  - <span data-ttu-id="d0509-159">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="d0509-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="d0509-160">匿名認証 (IIS がインストールされると、既定でインストールされます。)</span><span class="sxs-lookup"><span data-stu-id="d0509-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="d0509-161">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="d0509-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="d0509-162">Windows Media Format Runtime と Windows デスクトップエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d0509-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="d0509-163">**Windows デスクトップエクスペリエンス**会議を展開するすべてのフロントエンドサーバーおよび標準エディションサーバーには、windows デスクトップエクスペリエンスの一部としてインストールされている windows Server 2012 以外の Windows Media Format ランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="d0509-164">Windows Server 2012 には Microsoft メディアファンデーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0509-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="d0509-165">Windows Media 形式ランタイムは、コールパーク、アナウンスメント、および応答グループアプリケーションがお知らせや音楽を再生するために、Windows Media オーディオ (.wma) ファイルを実行するために必要です。</span><span class="sxs-lookup"><span data-stu-id="d0509-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="d0509-166">Lync Server 2013 をインストールする前に、Windows デスクトップエクスペリエンスをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0509-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="d0509-167">Lync Server 2013 でサーバー上にこのソフトウェアが見つからない場合は、インストールするように求められます。その後、インストールを完了するには、サーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="d0509-168">Windows Server 2012 で実行されているフロントエンドサーバーおよび標準エディションサーバー向けの追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="d0509-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="d0509-169">フロントエンドサーバーには、Windows Server 2012 に既定でインストールされていない .NET 3.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0509-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="d0509-170">インストールするには、Windows Server 2012 インストールメディアを D ドライブに挿入し、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d0509-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="d0509-171">Windows Server 2012 を実行しているサーバーへの .NET 3.5 のインストールの詳細については、「 <https://go.microsoft.com/fwlink/p/?linkid=275032>Microsoft .net Framework 3.5 展開に関する考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="d0509-172">ディレクター向けのその他のソフトウェア</span><span class="sxs-lookup"><span data-stu-id="d0509-172">Additional Software for Directors</span></span>

<span data-ttu-id="d0509-173">ディレクターは、次のモジュールを使用して、インターネットインフォメーションサービス (IIS) を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="d0509-174">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="d0509-174">Static Content</span></span>

  - <span data-ttu-id="d0509-175">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="d0509-175">Default Document</span></span>

  - <span data-ttu-id="d0509-176">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="d0509-176">HTTP Errors</span></span>

  - <span data-ttu-id="d0509-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d0509-177">ASP.NET</span></span>

  - <span data-ttu-id="d0509-178">.NET の拡張性</span><span class="sxs-lookup"><span data-stu-id="d0509-178">.NET Extensibility</span></span>

  - <span data-ttu-id="d0509-179">Internet Server API (ISAPI) の拡張機能</span><span class="sxs-lookup"><span data-stu-id="d0509-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="d0509-180">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="d0509-180">ISAPI Filters</span></span>

  - <span data-ttu-id="d0509-181">HTTP ログ</span><span class="sxs-lookup"><span data-stu-id="d0509-181">HTTP Logging</span></span>

  - <span data-ttu-id="d0509-182">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="d0509-182">Logging Tools</span></span>

  - <span data-ttu-id="d0509-183">トレース</span><span class="sxs-lookup"><span data-stu-id="d0509-183">Tracing</span></span>

  - <span data-ttu-id="d0509-184">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="d0509-184">Windows Authentication</span></span>

  - <span data-ttu-id="d0509-185">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="d0509-185">Request Filtering</span></span>

  - <span data-ttu-id="d0509-186">静的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="d0509-186">Static Content Compression</span></span>

  - <span data-ttu-id="d0509-187">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="d0509-187">IIS Management Console</span></span>

  - <span data-ttu-id="d0509-188">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="d0509-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="d0509-189">匿名認証 (IIS がインストールされると、既定でインストールされます。)</span><span class="sxs-lookup"><span data-stu-id="d0509-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="d0509-190">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="d0509-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="d0509-191">常設チャットフロントエンドサーバー向けの追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="d0509-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="d0509-192">常設チャットフロントエンドサーバーでは、Windows Server のコンポーネントであるメッセージキュー (MSMQ とも呼ばれます) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="d0509-193">MSMQ を有効にする方法については、ここをクリックして[ください。](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="d0509-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="d0509-194">エッジサーバー向けの追加ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="d0509-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="d0509-195">エッジサーバーには、次のソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0509-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="d0509-196">Lync Server 2013 を実行している各サーバーには、正しいバージョンの Windows PowerShell 3.0 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="d0509-197">詳細については、「 [Lync Server 2013 用に Windows PowerShell 3.0 をインストールする](lync-server-2013-installing-windows-powershell-3-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="d0509-198">Lync Server には Microsoft .NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0509-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="d0509-199">Windows Server 2008 R2 にインストールされている Lync Server 2013 の場合、Lync Server 2013 をインストールする前に、サーバーに64ビット版の Microsoft .NET Framework 4.5 を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="d0509-200">手動でインストールするには、microsoft ダウンロードセンターから Microsoft .NET 4.5 フレームワークをダウンロードしてください。[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="d0509-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="d0509-201">Lync Server 2013 の**Windows Identity foundation**では、サーバー間の認証シナリオをサポートするために、Windows id ファンデーションをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="d0509-202">Windows Server 2008 R2 および Windows Server 2012 では、Windows Id 基盤をインストールするために異なる手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d0509-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="d0509-203">次の一覧からサーバーのオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0509-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="d0509-204">Windows server 2008 R2 For Windows Server 2008 R2 では、既にコンピューターにインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0509-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="d0509-205">これを行うには、「**プログラムの追加と削除**」、「**インストールされている更新プログラムを表示**」の各項目にアクセスして、「 **windows** **id ファンデーション (KB974405)**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="d0509-206">Windows Id Foundation のインストールの詳細につい[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0509-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="d0509-207">Windows server 2012 For Windows Server 2012 では、**サーバーマネージャー**を使って Windows Identity Foundation をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d0509-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="d0509-208">サーバーマネージャーの**役割と機能の追加ウィザード**で、[**機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0509-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="d0509-209">一覧から [ **Windows Id Foundation 3.5** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d0509-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="d0509-210">[**次へ**] をクリックし、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0509-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="d0509-211">階層ソケットプロバイダーをメディアサーバーにインストールしない</span><span class="sxs-lookup"><span data-stu-id="d0509-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="d0509-212">Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバークライアントソフトウェア、またはその他の Winsock レイヤードサービスプロバイダ (LSP) ソフトウェアは、任意のフロントエンドサーバーまたはスタンドアロンの仲介サーバーにインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="d0509-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="d0509-213">このソフトウェアをインストールすると、メディアトラフィックのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0509-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0509-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0509-214">See Also</span></span>


[<span data-ttu-id="d0509-215">Lync Server 2013 の管理ツールのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="d0509-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

