---
title: 'Lync Server 2013: IIS 構成'
description: 'Lync Server 2013: IIS 構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554873"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="576ae-103">Lync Server 2013 の IIS 構成</span><span class="sxs-lookup"><span data-stu-id="576ae-103">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="576ae-104">_**トピックの最終更新日:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="576ae-104">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="576ae-105">この手順を正常に完了するには、少なくともローカル管理者とドメインユーザーとしてサーバーにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="576ae-105">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="576ae-106">プール内の Lync Server 2013、Standard Edition、または最初のフロントエンドサーバー用のフロントエンドサーバーを構成およびインストールする前に、インターネットインフォメーションサービス (IIS) のサーバーの役割と Web サービスをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="576ae-106">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="576ae-107">IIS およびすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある組織では、最初に Lync Server 2013 管理ツールをインストールするときに、[セットアップ] ダイアログボックスで Lync Server 2013 ファイルのインストール場所のパスを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="576ae-107">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="576ae-108">IIS をインストールする前に、管理ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="576ae-108">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="576ae-109">このパスにセットアップファイル (OCSCore.msi を含む) をインストールすると、残りの Lync Server 2013 ファイルもこのドライブに展開されます。</span><span class="sxs-lookup"><span data-stu-id="576ae-109">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="576ae-110">Dtails については、「 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 管理ツール</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="576ae-110">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="576ae-111">IIS のインストール時に Windows Server Manager によって展開された INETPUB の再配置方法の詳細については、「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。</span><span class="sxs-lookup"><span data-stu-id="576ae-111">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="576ae-112">次の表は、必要な IIS 7.5 の役割サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="576ae-112">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="576ae-113">IIS 7.5 の役割サービス</span><span class="sxs-lookup"><span data-stu-id="576ae-113">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="576ae-114">役割の見出し</span><span class="sxs-lookup"><span data-stu-id="576ae-114">Role Heading</span></span></th>
<th><span data-ttu-id="576ae-115">役割サービス</span><span class="sxs-lookup"><span data-stu-id="576ae-115">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ae-116">インストールされている共通の HTTP 機能</span><span class="sxs-lookup"><span data-stu-id="576ae-116">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="576ae-117">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="576ae-117">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-118">インストールされている共通の HTTP 機能</span><span class="sxs-lookup"><span data-stu-id="576ae-118">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="576ae-119">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="576ae-119">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-120">インストールされている共通の HTTP 機能</span><span class="sxs-lookup"><span data-stu-id="576ae-120">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="576ae-121">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="576ae-121">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-122">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-122">Application development</span></span></p></td>
<td><p><span data-ttu-id="576ae-123">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="576ae-123">ASP.NET</span></span></p>
<p><span data-ttu-id="576ae-124">Windows Server 2012 にも、ASP.DLL 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="576ae-124">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-125">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-125">Application development</span></span></p></td>
<td><p><span data-ttu-id="576ae-126">.NET 拡張機能</span><span class="sxs-lookup"><span data-stu-id="576ae-126">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-127">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-127">Application development</span></span></p></td>
<td><p><span data-ttu-id="576ae-128">Internet Server API (ISAPI) 拡張機能</span><span class="sxs-lookup"><span data-stu-id="576ae-128">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-129">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-129">Application development</span></span></p></td>
<td><p><span data-ttu-id="576ae-130">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="576ae-130">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-131">正常性と診断</span><span class="sxs-lookup"><span data-stu-id="576ae-131">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="576ae-132">HTTP ログ</span><span class="sxs-lookup"><span data-stu-id="576ae-132">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-133">正常性と診断</span><span class="sxs-lookup"><span data-stu-id="576ae-133">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="576ae-134">ログツール</span><span class="sxs-lookup"><span data-stu-id="576ae-134">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-135">正常性と診断</span><span class="sxs-lookup"><span data-stu-id="576ae-135">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="576ae-136">・</span><span class="sxs-lookup"><span data-stu-id="576ae-136">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-137">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="576ae-137">Security</span></span></p></td>
<td><p><span data-ttu-id="576ae-138">匿名認証 (既定でインストールされ、有効になっています)</span><span class="sxs-lookup"><span data-stu-id="576ae-138">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-139">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="576ae-139">Security</span></span></p></td>
<td><p><span data-ttu-id="576ae-140">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="576ae-140">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-141">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="576ae-141">Security</span></span></p></td>
<td><p><span data-ttu-id="576ae-142">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="576ae-142">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-143">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="576ae-143">Security</span></span></p></td>
<td><p><span data-ttu-id="576ae-144">要求フィルター</span><span class="sxs-lookup"><span data-stu-id="576ae-144">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-145">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="576ae-145">Performance</span></span></p></td>
<td><p><span data-ttu-id="576ae-146">静的なコンテンツの圧縮</span><span class="sxs-lookup"><span data-stu-id="576ae-146">Static content compression</span></span></p>
<p><span data-ttu-id="576ae-147">動的なコンテンツの圧縮</span><span class="sxs-lookup"><span data-stu-id="576ae-147">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-148">管理ツール</span><span class="sxs-lookup"><span data-stu-id="576ae-148">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="576ae-149">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="576ae-149">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-150">管理ツール</span><span class="sxs-lookup"><span data-stu-id="576ae-150">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="576ae-151">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="576ae-151">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="576ae-152">Windows Server 2008 R2 SP1 x64 オペレーティングシステムでは、Windows PowerShell 2.0 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="576ae-152">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="576ae-153">最初に ServerManager モジュールをインポートしてから、IIS 7.5 の役割および役割サービスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="576ae-153">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="576ae-154">匿名認証は、IIS サーバーの役割と共に既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="576ae-154">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="576ae-155">IIS をインストールした後で、匿名認証を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="576ae-155">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="576ae-156">詳細については、「」の「匿名認証 (IIS 7) を有効にする」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> 。</span><span class="sxs-lookup"><span data-stu-id="576ae-156">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="576ae-157">次の表は、Windows Server 2012 および Windows Server 2012 R2 に必要な IIS 8.0 および IIS 8.5 の役割サービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="576ae-157">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="576ae-158">Windows Server 2012 および Windows Server 2012 R2 では、Add-WindowsFeature コマンドレットは Install-WindowsFeature コマンドレットに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="576ae-158">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="576ae-159">詳細については、「 <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="576ae-159">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="576ae-160">IIS 8.0 および IIS 8.5 の役割サービス</span><span class="sxs-lookup"><span data-stu-id="576ae-160">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="576ae-161">役割の見出し</span><span class="sxs-lookup"><span data-stu-id="576ae-161">Role Heading</span></span></th>
<th><span data-ttu-id="576ae-162">役割サービス</span><span class="sxs-lookup"><span data-stu-id="576ae-162">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ae-163">Web サーバー (IIS)</span><span class="sxs-lookup"><span data-stu-id="576ae-163">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="576ae-164">Web サーバー</span><span class="sxs-lookup"><span data-stu-id="576ae-164">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-165">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="576ae-165">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-166">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="576ae-166">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-167">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="576ae-167">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-168">ディレクトリの参照</span><span class="sxs-lookup"><span data-stu-id="576ae-168">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-169">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="576ae-169">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-170">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="576ae-170">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-171">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="576ae-171">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-172">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="576ae-172">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-173">共通の HTTP 機能</span><span class="sxs-lookup"><span data-stu-id="576ae-173">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-174">HTTP リダイレクト</span><span class="sxs-lookup"><span data-stu-id="576ae-174">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-175">状態と診断</span><span class="sxs-lookup"><span data-stu-id="576ae-175">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="576ae-176">HTTP ログ</span><span class="sxs-lookup"><span data-stu-id="576ae-176">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-177">状態と診断</span><span class="sxs-lookup"><span data-stu-id="576ae-177">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="576ae-178">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="576ae-178">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-179">状態と診断</span><span class="sxs-lookup"><span data-stu-id="576ae-179">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="576ae-180">要求監視</span><span class="sxs-lookup"><span data-stu-id="576ae-180">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-181">状態と診断</span><span class="sxs-lookup"><span data-stu-id="576ae-181">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="576ae-182">・</span><span class="sxs-lookup"><span data-stu-id="576ae-182">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-183">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="576ae-183">Security</span></span></p></td>
<td><p><span data-ttu-id="576ae-184">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="576ae-184">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-185">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="576ae-185">Security</span></span></p></td>
<td><p><span data-ttu-id="576ae-186">基本認証</span><span class="sxs-lookup"><span data-stu-id="576ae-186">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-187">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="576ae-187">Security</span></span></p></td>
<td><p><span data-ttu-id="576ae-188">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="576ae-188">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-189">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="576ae-189">Security</span></span></p></td>
<td><p><span data-ttu-id="576ae-190">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="576ae-190">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-191">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-191">Application Development</span></span></p></td>
<td><p><span data-ttu-id="576ae-192">.Net 拡張機能3.5</span><span class="sxs-lookup"><span data-stu-id="576ae-192">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-193">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-193">Application Development</span></span></p></td>
<td><p><span data-ttu-id="576ae-194">.Net 拡張機能4.5</span><span class="sxs-lookup"><span data-stu-id="576ae-194">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-195">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-195">Application Development</span></span></p></td>
<td><p><span data-ttu-id="576ae-196">ASP.Net 3.5</span><span class="sxs-lookup"><span data-stu-id="576ae-196">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-197">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-197">Application Development</span></span></p></td>
<td><p><span data-ttu-id="576ae-198">ASP.Net 4.5</span><span class="sxs-lookup"><span data-stu-id="576ae-198">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-199">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-199">Application Development</span></span></p></td>
<td><p><span data-ttu-id="576ae-200">ISAPI 拡張機能</span><span class="sxs-lookup"><span data-stu-id="576ae-200">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-201">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-201">Application Development</span></span></p></td>
<td><p><span data-ttu-id="576ae-202">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="576ae-202">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-203">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="576ae-203">Application Development</span></span></p></td>
<td><p><span data-ttu-id="576ae-204">サーバー側インクルード</span><span class="sxs-lookup"><span data-stu-id="576ae-204">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-205">管理ツール</span><span class="sxs-lookup"><span data-stu-id="576ae-205">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="576ae-206">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="576ae-206">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-207">管理ツール</span><span class="sxs-lookup"><span data-stu-id="576ae-207">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="576ae-208">IIS 6 メタベースの互換性</span><span class="sxs-lookup"><span data-stu-id="576ae-208">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-209">管理ツール</span><span class="sxs-lookup"><span data-stu-id="576ae-209">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="576ae-210">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="576ae-210">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-211">.Net 3.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="576ae-211">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-212">.Net 3.5 Framework</span><span class="sxs-lookup"><span data-stu-id="576ae-212">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-213">.Net 4.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="576ae-213">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-214">.Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="576ae-214">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-215">.Net 4.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="576ae-215">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-216">ASP.Net 4.5</span><span class="sxs-lookup"><span data-stu-id="576ae-216">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-217">.Net 4.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="576ae-217">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-218">HTTP ライセンス認証</span><span class="sxs-lookup"><span data-stu-id="576ae-218">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-219">.Net 4.5 Framework の機能</span><span class="sxs-lookup"><span data-stu-id="576ae-219">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="576ae-220">TCP ポート共有</span><span class="sxs-lookup"><span data-stu-id="576ae-220">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-221">バックグラウンドインテリジェント転送サービス</span><span class="sxs-lookup"><span data-stu-id="576ae-221">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="576ae-222">IIS サーバー拡張機能</span><span class="sxs-lookup"><span data-stu-id="576ae-222">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-223">インクと手書きサービス</span><span class="sxs-lookup"><span data-stu-id="576ae-223">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="576ae-224">インクと手書きサービス</span><span class="sxs-lookup"><span data-stu-id="576ae-224">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-225">メディアファンデーション</span><span class="sxs-lookup"><span data-stu-id="576ae-225">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="576ae-226">メディアファンデーション</span><span class="sxs-lookup"><span data-stu-id="576ae-226">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-227">ユーザーインターフェイスとインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="576ae-227">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="576ae-228">グラフィカルな管理ツールおよびインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="576ae-228">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-229">ユーザーインターフェイスとインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="576ae-229">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="576ae-230">デスクトップ環境</span><span class="sxs-lookup"><span data-stu-id="576ae-230">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-231">ユーザーインターフェイスとインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="576ae-231">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="576ae-232">サーバーのグラフィカルシェル</span><span class="sxs-lookup"><span data-stu-id="576ae-232">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-233">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="576ae-233">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="576ae-234">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="576ae-234">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ae-235">Windows プロセスアクティブ化サービス</span><span class="sxs-lookup"><span data-stu-id="576ae-235">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="576ae-236">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="576ae-236">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ae-237">Windows プロセスアクティブ化サービス</span><span class="sxs-lookup"><span data-stu-id="576ae-237">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="576ae-238">構成 Api</span><span class="sxs-lookup"><span data-stu-id="576ae-238">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="576ae-239">Windows Server 2012 および Windows Server 2012 R2 では、Windows PowerShell 3.0 を使用して IIS の要件をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="576ae-239">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="576ae-240">Windows PowerShell 3.0 で ServerManager モジュールを使用して、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="576ae-240">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="576ae-241">Windows Server 2012 を使用した新機能– Source パラメーターは、Windows Server 2012 のソースメディアがある場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="576ae-241">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="576ae-242">メディアは、DVD ドライブ (D:\sources\sxs)。など)、またはメディアファイルがコピーされたネットワーク共有 (たとえば、Fileserver\windows2012\sources\Sxs) として定義でき \\ ます。</span><span class="sxs-lookup"><span data-stu-id="576ae-242">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="576ae-243">関連項目</span><span class="sxs-lookup"><span data-stu-id="576ae-243">See Also</span></span>


[<span data-ttu-id="576ae-244">Lync Server 2013 のフロントエンドプールおよび Standard Edition サーバーの IIS 要件</span><span class="sxs-lookup"><span data-stu-id="576ae-244">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

