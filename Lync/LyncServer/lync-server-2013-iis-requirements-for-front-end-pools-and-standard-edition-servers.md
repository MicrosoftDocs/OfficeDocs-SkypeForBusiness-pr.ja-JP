---
title: フロントエンドプールおよび Standard Edition サーバーの IIS 要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1511ea24acb058f8de7bdbcf7f831e6493b2ffd6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="da190-102">Lync Server 2013 のフロントエンドプールおよび Standard Edition サーバーの IIS 要件</span><span class="sxs-lookup"><span data-stu-id="da190-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da190-103">_**トピックの最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="da190-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="da190-104">Standard Edition サーバーとフロントエンドサーバーおよびディレクターの場合、Lync Server 2013 インストーラーは次の目的のためにインターネットインフォメーションサービス (IIS) に仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="da190-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="da190-105">ユーザーがアドレス帳サービスからファイルをダウンロードできるようにする。</span><span class="sxs-lookup"><span data-stu-id="da190-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="da190-106">クライアントが更新を取得できるようにするには</span><span class="sxs-lookup"><span data-stu-id="da190-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="da190-107">会議を有効にする。</span><span class="sxs-lookup"><span data-stu-id="da190-107">To enable conferencing</span></span>

  - <span data-ttu-id="da190-108">ユーザーが会議コンテンツをダウンロードできるようにする。</span><span class="sxs-lookup"><span data-stu-id="da190-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="da190-109">ユーザーが配布グループを拡張できるようにする。</span><span class="sxs-lookup"><span data-stu-id="da190-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="da190-110">電話会議を有効にする。</span><span class="sxs-lookup"><span data-stu-id="da190-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="da190-111">応答グループ機能を有効にする。</span><span class="sxs-lookup"><span data-stu-id="da190-111">To enable response group features</span></span>

<span data-ttu-id="da190-112">さらに、Lync Server 2010:11 月2011インストーラーの累積的な更新プログラムにより、次の目的のために IIS で仮想ディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="da190-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="da190-113">インスタントメッセージング (IM) やプレゼンスなど、モバイルデバイスでのモビリティ機能をサポートするフロントエンドサーバーまたは Standard Edition サーバー上</span><span class="sxs-lookup"><span data-stu-id="da190-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="da190-114">フロントエンドサーバーまたは Standard Edition サーバーとディレクターで、モバイルデバイスがモビリティリソースを自動的に検出できるようにする</span><span class="sxs-lookup"><span data-stu-id="da190-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="da190-115">モビリティを展開する場合は、IIS 7.5 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da190-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="da190-116">Lync Server Mobility Service installer は、パフォーマンスを向上させるためにいくつかの ASP.NET フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="da190-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="da190-117">既定では、IIS 7.5 が Windows Server 2008 R2 にインストールされ、Mobility Service インストーラーによって ASP.NET 設定が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="da190-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="da190-118">Windows Server 2008 で IIS 7.0 を使用する場合は、この設定を手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da190-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="da190-119">Lync Server には、次の IIS モジュールがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="da190-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="da190-120">IIS およびすべての Web サービスをシステムドライブ以外のドライブに配置する必要がある組織では、[セットアップ] ダイアログボックスで Lync Server ファイルのインストール場所のパスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="da190-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="da190-121">このパスに対して、OCSCore を含むセットアップファイルをインストールすると、残りの Lync Server ファイルもこのドライブに展開されます。</span><span class="sxs-lookup"><span data-stu-id="da190-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="da190-122">IIS のインストール時に Windows Server Manager によって展開された INETPUB の再<A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>配置方法の詳細については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da190-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="da190-123">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="da190-123">Static Content</span></span>

  - <span data-ttu-id="da190-124">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="da190-124">Default Document</span></span>

  - <span data-ttu-id="da190-125">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="da190-125">HTTP Errors</span></span>

  - <span data-ttu-id="da190-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="da190-126">ASP.NET</span></span>

  - <span data-ttu-id="da190-127">.NET 拡張機能</span><span class="sxs-lookup"><span data-stu-id="da190-127">.NET Extensibility</span></span>

  - <span data-ttu-id="da190-128">Internet Server API (ISAPI) 拡張機能</span><span class="sxs-lookup"><span data-stu-id="da190-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="da190-129">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="da190-129">ISAPI Filters</span></span>

  - <span data-ttu-id="da190-130">HTTP ロギング機能</span><span class="sxs-lookup"><span data-stu-id="da190-130">HTTP Logging</span></span>

  - <span data-ttu-id="da190-131">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="da190-131">Logging Tools</span></span>

  - <span data-ttu-id="da190-132">・</span><span class="sxs-lookup"><span data-stu-id="da190-132">Tracing</span></span>

  - <span data-ttu-id="da190-133">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="da190-133">Windows Authentication</span></span>

  - <span data-ttu-id="da190-134">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="da190-134">Request Filtering</span></span>

  - <span data-ttu-id="da190-135">静的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="da190-135">Static Content Compression</span></span>

  - <span data-ttu-id="da190-136">動的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="da190-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="da190-137">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="da190-137">IIS Management Console</span></span>

  - <span data-ttu-id="da190-138">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="da190-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="da190-139">匿名認証 (IIS のインストール時に既定でインストールされる)</span><span class="sxs-lookup"><span data-stu-id="da190-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="da190-140">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="da190-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="da190-141">次の表では、内部アクセス用の仮想ディレクトリの URI とそれらが参照しているファイル システム リソースの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="da190-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="da190-142">内部アクセス用の仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="da190-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da190-143">機能</span><span class="sxs-lookup"><span data-stu-id="da190-143">Feature</span></span></th>
<th><span data-ttu-id="da190-144">仮想ディレクトリの URI</span><span class="sxs-lookup"><span data-stu-id="da190-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="da190-145">参照先</span><span class="sxs-lookup"><span data-stu-id="da190-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da190-146">アドレス帳サーバー</span><span class="sxs-lookup"><span data-stu-id="da190-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="da190-147">https://&lt;内部 FQDN&gt;/ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="da190-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="da190-148">内部ユーザー用のアドレス帳サーバー ダウンロード ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da190-149">自動検出サービス</span><span class="sxs-lookup"><span data-stu-id="da190-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="da190-150">https://&lt;内部 FQDN&gt;/自動検出</span><span class="sxs-lookup"><span data-stu-id="da190-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="da190-151">内部モバイルデバイスユーザーのモビリティリソースを検索する Lync Server 自動検出サービスの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da190-152">クライアントの更新</span><span class="sxs-lookup"><span data-stu-id="da190-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="da190-153">http://&lt;内部 FQDN&gt;/AutoUpdate/Int</span><span class="sxs-lookup"><span data-stu-id="da190-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="da190-154">内部のコンピューターベース クライアント用の更新ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da190-155">Conf</span><span class="sxs-lookup"><span data-stu-id="da190-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="da190-156">http://&lt;内部 FQDN&gt;/conf/Int</span><span class="sxs-lookup"><span data-stu-id="da190-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="da190-157">内部ユーザー用会議リソースの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da190-158">デバイス更新</span><span class="sxs-lookup"><span data-stu-id="da190-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="da190-159">http://&lt;内部 FQDN&gt;/DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="da190-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="da190-160">内部統合コミュニケーション (UC) デバイス用の UC デバイス更新ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da190-161">会議</span><span class="sxs-lookup"><span data-stu-id="da190-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="da190-162">http://&lt;内部 FQDN&gt;/etc/place/null</span><span class="sxs-lookup"><span data-stu-id="da190-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="da190-163">内部ユーザー用のミーティング コンテンツの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da190-164">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="da190-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="da190-165">https://&lt;内部 FQDN&gt;/mcx</span><span class="sxs-lookup"><span data-stu-id="da190-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="da190-166">内部モバイル デバイス ユーザー用の Mobility Service リソースの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da190-167">グループ拡張およびアドレス帳 Web クエリ サービス</span><span class="sxs-lookup"><span data-stu-id="da190-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="da190-168">http://&lt;内部 FQDN&gt;/グループの内部 FQDN</span><span class="sxs-lookup"><span data-stu-id="da190-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="da190-169">内部ユーザーのグループ拡張を有効にする Web サービスの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="da190-170">また、内部 Lync Mobile Microsoft Lync 2010 モバイルクライアントにグローバルアドレス一覧情報を提供する、アドレス帳 Web クエリサービスの場所についても説明します。</span><span class="sxs-lookup"><span data-stu-id="da190-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da190-171">電話会議</span><span class="sxs-lookup"><span data-stu-id="da190-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="da190-172">http://&lt;内部 FQDN&gt;/PhoneConferencing/Int</span><span class="sxs-lookup"><span data-stu-id="da190-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="da190-173">内部ユーザー用の電話会議データの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da190-174">デバイス更新</span><span class="sxs-lookup"><span data-stu-id="da190-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="da190-175">http://&lt;内部 FQDN&gt;/RequestHandler</span><span class="sxs-lookup"><span data-stu-id="da190-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="da190-176">内部 UC デバイスによるログのアップロードと更新の確認を可能にするデバイス更新 Web サービス要求ハンドラーの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da190-177">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="da190-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="da190-178">http://&lt;内部 FQDN&gt;/RgsConfig</span><span class="sxs-lookup"><span data-stu-id="da190-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="da190-179">http://&lt;内部 FQDN&gt;/RgsClients</span><span class="sxs-lookup"><span data-stu-id="da190-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="da190-180">応答グループ構成ツールの場所。</span><span class="sxs-lookup"><span data-stu-id="da190-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="da190-181">統合構成のフロントエンドプールの場合は、サーバーをプールに追加する前に IIS を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da190-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" /><span data-ttu-id="da190-183">セキュリティに関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="da190-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="da190-184">IIS 管理用スナップインを使用して、IIS Web コンポーネント サーバーで使用される証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="da190-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

