---
title: 'Lync Server 2013: IIS 構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b9803fdb6c4a048fdf072b5ba2e5722b863640
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="45b71-102">Lync Server 2013 の IIS 構成</span><span class="sxs-lookup"><span data-stu-id="45b71-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45b71-103">_**最終更新日:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="45b71-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="45b71-104">この手順を完了するには、ローカル管理者とドメインユーザーとして、サーバーに少なくともログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b71-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="45b71-105">Lync Server 2013、Standard Edition、または第1のフロントエンドサーバー用のフロントエンドサーバーをプールに構成してインストールする前に、サーバーの役割とインターネットインフォメーションサービス (IIS) 用の Web サービスをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="45b71-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="45b71-106">組織で IIS およびすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある場合は、Lync Server 2013 を初めてインストールするときに、[セットアップ] ダイアログボックスで Lync Server 2013 ファイルのインストール場所のパスを変更することができます。管理ツール。</span><span class="sxs-lookup"><span data-stu-id="45b71-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="45b71-107">IIS をインストールする前に、管理ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="45b71-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="45b71-108">このパス (OCSCore など) にセットアップファイルをインストールすると、Lync Server の他の2013ファイルもこのドライブに展開されます。</span><span class="sxs-lookup"><span data-stu-id="45b71-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="45b71-109">Dtails については、「 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 管理ツールをインストール</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b71-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="45b71-110">IIS をインストールするときに、Windows Server Manager によって展開された INETPUB <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>を再配置する方法の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b71-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="45b71-111">次の表は、必要な IIS 7.5 の役割サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="45b71-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="45b71-112">IIS 7.5 の役割サービス</span><span class="sxs-lookup"><span data-stu-id="45b71-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45b71-113">ロール見出し</span><span class="sxs-lookup"><span data-stu-id="45b71-113">Role Heading</span></span></th>
<th><span data-ttu-id="45b71-114">役割サービス</span><span class="sxs-lookup"><span data-stu-id="45b71-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45b71-115">インストールされている一般的な HTTP 機能</span><span class="sxs-lookup"><span data-stu-id="45b71-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="45b71-116">静的なコンテンツ</span><span class="sxs-lookup"><span data-stu-id="45b71-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-117">インストールされている一般的な HTTP 機能</span><span class="sxs-lookup"><span data-stu-id="45b71-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="45b71-118">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="45b71-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-119">インストールされている一般的な HTTP 機能</span><span class="sxs-lookup"><span data-stu-id="45b71-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="45b71-120">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="45b71-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-121">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="45b71-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="45b71-122">ASP.NET</span></span></p>
<p><span data-ttu-id="45b71-123">Windows Server 2012 にも、.ASP 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="45b71-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-124">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="45b71-125">.NET の拡張性</span><span class="sxs-lookup"><span data-stu-id="45b71-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-126">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="45b71-127">Internet Server API (ISAPI) の拡張機能</span><span class="sxs-lookup"><span data-stu-id="45b71-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-128">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="45b71-129">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="45b71-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-130">正常性と診断</span><span class="sxs-lookup"><span data-stu-id="45b71-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="45b71-131">HTTP ログ</span><span class="sxs-lookup"><span data-stu-id="45b71-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-132">正常性と診断</span><span class="sxs-lookup"><span data-stu-id="45b71-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="45b71-133">ログツール</span><span class="sxs-lookup"><span data-stu-id="45b71-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-134">正常性と診断</span><span class="sxs-lookup"><span data-stu-id="45b71-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="45b71-135">トレース</span><span class="sxs-lookup"><span data-stu-id="45b71-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-136">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="45b71-136">Security</span></span></p></td>
<td><p><span data-ttu-id="45b71-137">匿名認証 (既定でインストールされ、有効になっている)</span><span class="sxs-lookup"><span data-stu-id="45b71-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-138">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="45b71-138">Security</span></span></p></td>
<td><p><span data-ttu-id="45b71-139">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="45b71-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-140">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="45b71-140">Security</span></span></p></td>
<td><p><span data-ttu-id="45b71-141">クライアント証明書のマッピング認証</span><span class="sxs-lookup"><span data-stu-id="45b71-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-142">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="45b71-142">Security</span></span></p></td>
<td><p><span data-ttu-id="45b71-143">フィルターを要求する</span><span class="sxs-lookup"><span data-stu-id="45b71-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-144">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="45b71-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="45b71-145">静的なコンテンツの圧縮</span><span class="sxs-lookup"><span data-stu-id="45b71-145">Static content compression</span></span></p>
<p><span data-ttu-id="45b71-146">動的なコンテンツの圧縮</span><span class="sxs-lookup"><span data-stu-id="45b71-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-147">管理ツール</span><span class="sxs-lookup"><span data-stu-id="45b71-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="45b71-148">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="45b71-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-149">管理ツール</span><span class="sxs-lookup"><span data-stu-id="45b71-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="45b71-150">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="45b71-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="45b71-151">Windows Server 2008 R2 SP1 x64 オペレーティングシステムでは、Windows PowerShell 2.0 を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="45b71-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="45b71-152">最初に ServerManager モジュールをインポートし、次に IIS 7.5 の役割と役割サービスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45b71-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="45b71-153">匿名認証は、既定で IIS server の役割と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="45b71-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="45b71-154">匿名認証は、IIS のインストール後に管理できます。</span><span class="sxs-lookup"><span data-stu-id="45b71-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="45b71-155">詳細については、の「匿名認証 (IIS 7) <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>を有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b71-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="45b71-156">次の表は、Windows Server 2012 および Windows Server 2012 R2 に必要な IIS 8.0 と IIS 8.5 の役割サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="45b71-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="45b71-157">Windows Server 2012 および Windows Server 2012 R2 の場合、add-windowsfeature コマンドレットは Install コマンドレットに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="45b71-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="45b71-158">詳細については、「 <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-add-windowsfeature</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45b71-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="45b71-159">IIS 8.0 および IIS 8.5 の役割サービス</span><span class="sxs-lookup"><span data-stu-id="45b71-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45b71-160">ロール見出し</span><span class="sxs-lookup"><span data-stu-id="45b71-160">Role Heading</span></span></th>
<th><span data-ttu-id="45b71-161">役割サービス</span><span class="sxs-lookup"><span data-stu-id="45b71-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45b71-162">Web サーバー (IIS)</span><span class="sxs-lookup"><span data-stu-id="45b71-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="45b71-163">Web サーバー</span><span class="sxs-lookup"><span data-stu-id="45b71-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-164">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="45b71-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-165">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="45b71-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-166">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="45b71-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-167">ディレクトリの参照</span><span class="sxs-lookup"><span data-stu-id="45b71-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-168">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="45b71-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-169">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="45b71-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-170">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="45b71-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-171">静的なコンテンツ</span><span class="sxs-lookup"><span data-stu-id="45b71-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-172">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="45b71-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-173">HTTP リダイレクション</span><span class="sxs-lookup"><span data-stu-id="45b71-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-174">状態と診断</span><span class="sxs-lookup"><span data-stu-id="45b71-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="45b71-175">HTTP ログ</span><span class="sxs-lookup"><span data-stu-id="45b71-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-176">状態と診断</span><span class="sxs-lookup"><span data-stu-id="45b71-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="45b71-177">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="45b71-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-178">状態と診断</span><span class="sxs-lookup"><span data-stu-id="45b71-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="45b71-179">要求監視</span><span class="sxs-lookup"><span data-stu-id="45b71-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-180">状態と診断</span><span class="sxs-lookup"><span data-stu-id="45b71-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="45b71-181">トレース</span><span class="sxs-lookup"><span data-stu-id="45b71-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-182">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="45b71-182">Security</span></span></p></td>
<td><p><span data-ttu-id="45b71-183">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="45b71-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-184">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="45b71-184">Security</span></span></p></td>
<td><p><span data-ttu-id="45b71-185">基本認証</span><span class="sxs-lookup"><span data-stu-id="45b71-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-186">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="45b71-186">Security</span></span></p></td>
<td><p><span data-ttu-id="45b71-187">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="45b71-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-188">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="45b71-188">Security</span></span></p></td>
<td><p><span data-ttu-id="45b71-189">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="45b71-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-190">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="45b71-191">.Net 拡張機能3.5</span><span class="sxs-lookup"><span data-stu-id="45b71-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-192">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="45b71-193">.Net 拡張機能4.5</span><span class="sxs-lookup"><span data-stu-id="45b71-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-194">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="45b71-195">ASP.Net 3.5</span><span class="sxs-lookup"><span data-stu-id="45b71-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-196">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="45b71-197">ASP.Net 4.5</span><span class="sxs-lookup"><span data-stu-id="45b71-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-198">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="45b71-199">ISAPI 拡張機能</span><span class="sxs-lookup"><span data-stu-id="45b71-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-200">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="45b71-201">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="45b71-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-202">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="45b71-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="45b71-203">サーバー側のインクルード</span><span class="sxs-lookup"><span data-stu-id="45b71-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-204">管理ツール</span><span class="sxs-lookup"><span data-stu-id="45b71-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="45b71-205">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="45b71-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-206">管理ツール</span><span class="sxs-lookup"><span data-stu-id="45b71-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="45b71-207">IIS 6 メタベースの互換性</span><span class="sxs-lookup"><span data-stu-id="45b71-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-208">管理ツール</span><span class="sxs-lookup"><span data-stu-id="45b71-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="45b71-209">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="45b71-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-210">.Net 3.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="45b71-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-211">.Net 3.5 フレームワーク</span><span class="sxs-lookup"><span data-stu-id="45b71-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-212">.Net 4.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="45b71-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-213">.Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="45b71-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-214">.Net 4.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="45b71-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-215">ASP.Net 4.5</span><span class="sxs-lookup"><span data-stu-id="45b71-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-216">.Net 4.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="45b71-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-217">HTTP アクティブ化</span><span class="sxs-lookup"><span data-stu-id="45b71-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-218">.Net 4.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="45b71-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="45b71-219">TCP ポート共有</span><span class="sxs-lookup"><span data-stu-id="45b71-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-220">バックグラウンドインテリジェント転送サービス</span><span class="sxs-lookup"><span data-stu-id="45b71-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="45b71-221">IIS Server Extensions</span><span class="sxs-lookup"><span data-stu-id="45b71-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-222">インクと手書きサービス</span><span class="sxs-lookup"><span data-stu-id="45b71-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="45b71-223">インクと手書きサービス</span><span class="sxs-lookup"><span data-stu-id="45b71-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-224">メディア ファンデーション</span><span class="sxs-lookup"><span data-stu-id="45b71-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="45b71-225">メディア ファンデーション</span><span class="sxs-lookup"><span data-stu-id="45b71-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-226">ユーザーインターフェイスとインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="45b71-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="45b71-227">グラフィカル管理ツールとインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="45b71-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-228">ユーザーインターフェイスとインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="45b71-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="45b71-229">デスクトップエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="45b71-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-230">ユーザーインターフェイスとインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="45b71-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="45b71-231">サーバーグラフィカルシェル</span><span class="sxs-lookup"><span data-stu-id="45b71-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-232">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="45b71-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="45b71-233">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="45b71-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45b71-234">Windows プロセスアクティブ化サービス</span><span class="sxs-lookup"><span data-stu-id="45b71-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="45b71-235">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="45b71-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45b71-236">Windows プロセスアクティブ化サービス</span><span class="sxs-lookup"><span data-stu-id="45b71-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="45b71-237">構成 Api</span><span class="sxs-lookup"><span data-stu-id="45b71-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="45b71-238">Windows Server 2012 および Windows Server 2012 R2 では、Windows PowerShell 3.0 を使用して、IIS の要件をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="45b71-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="45b71-239">Windows PowerShell 3.0 で ServerManager モジュールを使用して、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="45b71-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="45b71-240">Windows Server 2012 での新機能は、Windows Server 2012 ソースメディアが存在する場所を定義する、– Source パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="45b71-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="45b71-241">メディアは、DVD ドライブ (D:\Sources\Sxs など)、またはメディアファイルがコピーされたネットワーク共有 (Fileserver\windows2012\sources\Sxs など\\) として定義できます。</span><span class="sxs-lookup"><span data-stu-id="45b71-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45b71-242">関連項目</span><span class="sxs-lookup"><span data-stu-id="45b71-242">See Also</span></span>


[<span data-ttu-id="45b71-243">Lync Server 2013 のフロントエンド プールおよび Standard Edition サーバーの IIS 要件</span><span class="sxs-lookup"><span data-stu-id="45b71-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

