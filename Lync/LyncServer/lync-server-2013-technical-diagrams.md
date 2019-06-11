---
title: Lync Server 2013 テクニカル図表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical diagrams
ms:assetid: 7b6da49b-ac72-4ab0-8957-166e330b38fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn594589(v=OCS.15)
ms:contentKeyID: 61180439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d74f846f45b31fdff8921cfb628189726d4f2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-diagrams-for-lync-server-2013"></a><span data-ttu-id="521f7-102">Lync Server 2013 のテクニカルダイアグラム</span><span class="sxs-lookup"><span data-stu-id="521f7-102">Technical diagrams for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="521f7-103">_**最終更新日:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="521f7-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="521f7-104">**概要:** これらの図は、Lync 2013 で推奨される解決策の視覚的な表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="521f7-104">**Summary:** These diagrams provide visual representations of recommended solutions for Lync 2013.</span></span>

<span data-ttu-id="521f7-105">これらのリソースは、Visio (.vsd) 形式 (visio 2010 または Visio 2013) および PDF 形式で利用できます。</span><span class="sxs-lookup"><span data-stu-id="521f7-105">These resources are available in Visio (.vsd) format (Visio 2010 or Visio 2013) and PDF format.</span></span> <span data-ttu-id="521f7-106">印刷方法の詳細については、「Tips for printing posters」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="521f7-106">For information about how to print documents, see Tips for printing posters.</span></span>

<span data-ttu-id="521f7-p102">これらのファイルを表示するために、他のソフトウェアが必要になることがあります。詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="521f7-p102">You might need additional software to view these files. See the following table for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="521f7-109">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="521f7-109">File type</span></span></th>
<th><span data-ttu-id="521f7-110">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="521f7-110">Software</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="521f7-111">.vsd</span><span class="sxs-lookup"><span data-stu-id="521f7-111">.vsd</span></span></p></td>
<td><p><span data-ttu-id="521f7-112">Visio 2010、Visio 2013、または<a href="http://go.microsoft.com/fwlink/?linkid=393676">無料の visio viewer</a></span><span class="sxs-lookup"><span data-stu-id="521f7-112">Visio 2010, Visio 2013, or the <a href="http://go.microsoft.com/fwlink/?linkid=393676">free Visio viewer</a></span></span></p>
<p><span data-ttu-id="521f7-113">Visio Viewer を使用する場合は、VSD リンクを右クリックし、[<strong>対象をファイルに保存</strong>] をクリックしてファイルをコンピューターに保存し、コンピューター上でそのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="521f7-113">If you use the Visio viewer, right-click the VSD link, click <strong>Save Target As</strong>, save the file to your computer, and then open the file from your computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="521f7-114">.pdf</span><span class="sxs-lookup"><span data-stu-id="521f7-114">.pdf</span></span></p></td>
<td><p><span data-ttu-id="521f7-115"><a href="http://go.microsoft.com/fwlink/?linkid=393675">Adobe Reader</a>などの任意の PDF ビューアー</span><span class="sxs-lookup"><span data-stu-id="521f7-115">Any PDF viewer, such as <a href="http://go.microsoft.com/fwlink/?linkid=393675">Adobe Reader</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="521f7-116">.zip</span><span class="sxs-lookup"><span data-stu-id="521f7-116">.zip</span></span></p></td>
<td><p><span data-ttu-id="521f7-117">任意のファイル圧縮ユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="521f7-117">Any file compression utility.</span></span> <span data-ttu-id="521f7-118">Windows 7 および8では、これらのファイルをネイティブで開きます。</span><span class="sxs-lookup"><span data-stu-id="521f7-118">Windows 7 and 8 open these files natively.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="posters"></a><span data-ttu-id="521f7-119">ポスター</span><span class="sxs-lookup"><span data-stu-id="521f7-119">Posters</span></span>

<span data-ttu-id="521f7-120">これらのポスターは、それぞれ固有の技術エリアの詳細を示していて、TechNet の対応する記事やダウンロード センターで提供されるコンテンツとともに使用することが想定されています。</span><span class="sxs-lookup"><span data-stu-id="521f7-120">These posters detail a specific technical area, and are intended to be used with corresponding articles on TechNet or content available on the download center.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="521f7-121">タイトル</span><span class="sxs-lookup"><span data-stu-id="521f7-121">Title</span></span></th>
<th><span data-ttu-id="521f7-122">説明</span><span class="sxs-lookup"><span data-stu-id="521f7-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="521f7-123"><strong>Lync Server 2013 オンプレミスのアーキテクチャ</strong></span><span class="sxs-lookup"><span data-stu-id="521f7-123"><strong>Lync Server 2013 On-Premises Architectures</strong></span></span></p>
<img src="images/Dn594589.36530bb8-732f-4be0-9502-082c01df9fba(OCS.15).jpg" title="Lync アーキテクチャポスターのサムネイル" alt="thumbnail of Lync architectures poster" />
<p><span data-ttu-id="521f7-125"><a href="http://go.microsoft.com/fwlink/?linkid=392974">Microsoft の Zoom.it を使用して、すべての詳細でポスターを拡大する</a>(デスクトップまたはノート pc で最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-125"><a href="http://go.microsoft.com/fwlink/?linkid=392974">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="521f7-126"><a href="http://go.microsoft.com/fwlink/?linkid=392578">PDF バージョン</a>(モバイルデバイスまたはタブレットコンピューターに最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-126"><a href="http://go.microsoft.com/fwlink/?linkid=392578">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="521f7-127"><a href="http://go.microsoft.com/fwlink/?linkid=392579">Visio のバージョン</a>(Visio を使用するユーザーに最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-127"><a href="http://go.microsoft.com/fwlink/?linkid=392579">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="521f7-128">[ポスター] 計画と展開のためのアーキテクチャガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="521f7-128">Poster provides architectural guidance for planning and deployment.</span></span> <span data-ttu-id="521f7-129">このポスターには、Lync Server の一般的なコンポーネント、展開を計画するときに使用する用語、新機能、サーバーの役割、インストールの概要などの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="521f7-129">The poster contains information about common components of Lync Server, terminology used when planning a deployment, new features, server roles, and an installation overview.</span></span> <span data-ttu-id="521f7-130">さらに、高可用性と災害復旧、および小規模、中規模、大規模なサンプルトポロジを実現するためのアーキテクチャの例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="521f7-130">In addition the poster contains example architectures for increasing high availability and disaster recovery as well as small, medium, and large sample topologies.</span></span></p>
<p><span data-ttu-id="521f7-131">サイズ: 86.36 x 111.76 cm</span><span class="sxs-lookup"><span data-stu-id="521f7-131">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="521f7-132">このポスターは、Visio 2013 を使って作成されました。</span><span class="sxs-lookup"><span data-stu-id="521f7-132">This poster was created using Visio 2013.</span></span> <span data-ttu-id="521f7-133">特定の環境に対する変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="521f7-133">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="521f7-134"><strong>Lync 通話品質の方法</strong></span><span class="sxs-lookup"><span data-stu-id="521f7-134"><strong>Lync Call Quality Methodology</strong></span></span></p>
<img src="images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg" title="CQM プロセスについて説明するポスター" alt="Poster describing the CQM process" />
<p><span data-ttu-id="521f7-136"><a href="http://go.microsoft.com/fwlink/?linkid=392972">Microsoft の Zoom.it を使用して、すべての詳細でポスターを拡大する</a>(デスクトップまたはノート pc で最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-136"><a href="http://go.microsoft.com/fwlink/?linkid=392972">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="521f7-137"><a href="http://go.microsoft.com/fwlink/?linkid=391841">1つの .zip ファイルでの Visio および PDF のバージョン</a></span><span class="sxs-lookup"><span data-stu-id="521f7-137"><a href="http://go.microsoft.com/fwlink/?linkid=391841">Visio and PDF versions together in a .zip file</a></span></span></p></td>
<td><p><span data-ttu-id="521f7-138">Lync システムのトラブルシューティングについて説明しています。特に、エンタープライズボイスの品質に影響する問題の場合。</span><span class="sxs-lookup"><span data-stu-id="521f7-138">Poster describing Lync system troubleshooting, especially for issues affecting enterprise voice quality.</span></span> <span data-ttu-id="521f7-139">このポスターの用途:</span><span class="sxs-lookup"><span data-stu-id="521f7-139">Use this poster with:</span></span></p>
<ul>
<li><p><span data-ttu-id="521f7-140"><a href="http://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server ネットワークガイド</a></span><span class="sxs-lookup"><span data-stu-id="521f7-140"><a href="http://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server Networking Guide</a></span></span></p></li>
<li><p><span data-ttu-id="521f7-141"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Server 2013 での Lync 通話品質の方法</a>(アクセシビリティに関する記事)</span><span class="sxs-lookup"><span data-stu-id="521f7-141"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Call Quality Methodology in Lync Server 2013</a> (accessibility article)</span></span></p></li>
<li><p><span data-ttu-id="521f7-142"><a href="lync-server-2013-poster-key-health-indicators.md">Lync Server 2013 の主要な正常性インジケーター</a>(アクセシビリティに関する記事)</span><span class="sxs-lookup"><span data-stu-id="521f7-142"><a href="lync-server-2013-poster-key-health-indicators.md">Key Health Indicators in Lync Server 2013</a> (accessibility article)</span></span></p></li>
</ul>
<p><span data-ttu-id="521f7-143">サイズ: 86.36 x 111.76 cm</span><span class="sxs-lookup"><span data-stu-id="521f7-143">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="521f7-144">このポスターは、Visio 2010 で作成されました。</span><span class="sxs-lookup"><span data-stu-id="521f7-144">This poster was created using Visio 2010.</span></span> <span data-ttu-id="521f7-145">特定の環境に対する変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="521f7-145">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="521f7-146"><strong>主要な正常性インジケーター</strong></span><span class="sxs-lookup"><span data-stu-id="521f7-146"><strong>Key Health Indicators</strong></span></span></p>
<img src="images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg" title="KHI データを使ったトラブルシューティングについて説明しているポスター" alt="Poster describing troubleshooting using KHI data" />
<p><span data-ttu-id="521f7-148"><a href="http://go.microsoft.com/fwlink/?linkid=392971">Microsoft の Zoom.it を使用して、すべての詳細でポスターを拡大する</a>(デスクトップまたはノート pc で最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-148"><a href="http://go.microsoft.com/fwlink/?linkid=392971">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="521f7-149"><a href="http://go.microsoft.com/fwlink/?linkid=391838">1つの .zip ファイルでの Visio および PDF のバージョン</a></span><span class="sxs-lookup"><span data-stu-id="521f7-149"><a href="http://go.microsoft.com/fwlink/?linkid=391838">Visio and PDF versions together in a .zip file</a></span></span></p></td>
<td><p><span data-ttu-id="521f7-150">基本的なサーバーの正常性と、Lync の実装でのサーバーの役割について、サーバーのトラブルシューティングのメトリックについて説明したポスター。</span><span class="sxs-lookup"><span data-stu-id="521f7-150">Poster describing server troubleshooting metrics both for basic server health and for a given server’s role in the Lync implementation.</span></span> <span data-ttu-id="521f7-151">このポスターの用途:</span><span class="sxs-lookup"><span data-stu-id="521f7-151">Use this poster with:</span></span></p>
<ul>
<li><p><span data-ttu-id="521f7-152"><a href="http://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server ネットワークガイド</a></span><span class="sxs-lookup"><span data-stu-id="521f7-152"><a href="http://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server Networking Guide</a></span></span></p></li>
<li><p><span data-ttu-id="521f7-153"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Server 2013 での Lync 通話品質の方法</a>(アクセシビリティに関する記事)</span><span class="sxs-lookup"><span data-stu-id="521f7-153"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Call Quality Methodology in Lync Server 2013</a> (accessibility article)</span></span></p></li>
<li><p><span data-ttu-id="521f7-154"><a href="lync-server-2013-poster-key-health-indicators.md">Lync Server 2013 の主要な正常性インジケーター</a>(アクセシビリティに関する記事)</span><span class="sxs-lookup"><span data-stu-id="521f7-154"><a href="lync-server-2013-poster-key-health-indicators.md">Key Health Indicators in Lync Server 2013</a> (accessibility article)</span></span></p></li>
</ul>
<p><span data-ttu-id="521f7-155">サイズ:17 x 22 インチ</span><span class="sxs-lookup"><span data-stu-id="521f7-155">Size: 17-by-22 inch</span></span></p>
<p><span data-ttu-id="521f7-156">このポスターは、Visio 2010 で作成されました。</span><span class="sxs-lookup"><span data-stu-id="521f7-156">This poster was created using Visio 2010.</span></span> <span data-ttu-id="521f7-157">特定の環境に対する変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="521f7-157">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="521f7-158"><strong>Lync 2013 プラットフォームのオプション</strong></span><span class="sxs-lookup"><span data-stu-id="521f7-158"><strong>Lync 2013 Platform Options</strong></span></span></p>
<img src="images/Dn594589.c5b66828-c3cf-4654-bb75-b93f97d085b3(OCS.15).jpg" title="プラットフォームオプションのポスターのサムネイルビュー" alt="thumbnail view of platform options poster" />
<p><span data-ttu-id="521f7-160"><a href="http://go.microsoft.com/fwlink/p/?linkid=391840">Microsoft の Zoom.it を使用して、すべての詳細でポスターを拡大する</a></span><span class="sxs-lookup"><span data-stu-id="521f7-160"><a href="http://go.microsoft.com/fwlink/p/?linkid=391840">Zoom into the poster in full detail with Zoom.it from Microsoft</a></span></span></p>
<p><span data-ttu-id="521f7-161"><a href="http://go.microsoft.com/fwlink/p/?linkid=391837">PDF バージョン</a>(モバイルデバイスまたはタブレットコンピューターに最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-161"><a href="http://go.microsoft.com/fwlink/p/?linkid=391837">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="521f7-162"><a href="http://go.microsoft.com/fwlink/p/?linkid=391839">Visio のバージョン</a>(Visio を使用するユーザーに最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-162"><a href="http://go.microsoft.com/fwlink/p/?linkid=391839">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="521f7-163">このポスターでは、Lync 2013 から BDMs の利用可能なプラットフォームオプションについて説明します。ユーザーは、Office 365、ハイブリッド Lync、Lync Server オンプレミスおよびホストされた Lync で Lync Online から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="521f7-163">This poster describes the available platform options for Lync 2013 to BDMs and architects  Customers can choose from Lync Online with Office 365, Hybrid Lync, Lync Server on-premises and Hosted Lync.</span></span> <span data-ttu-id="521f7-164">このポスターには、各アーキテクチャオプションの詳細が記載されています。各アーキテクチャの最適なシナリオ、ライセンス要件、IT Pro の責任などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="521f7-164">The poster includes details of each architectural option, including the most ideal scenarios for each, the license requirements and IT Pro responsibilities.</span></span></p>
<p><span data-ttu-id="521f7-165">サイズ: 86.36 x 111.76 cm</span><span class="sxs-lookup"><span data-stu-id="521f7-165">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="521f7-166">このポスターは、Visio 2013 を使って作成されました。</span><span class="sxs-lookup"><span data-stu-id="521f7-166">This poster was created using Visio 2013.</span></span> <span data-ttu-id="521f7-167">特定の環境に対する変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="521f7-167">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="521f7-168"><strong>Microsoft Lync Server 2013 Protocol のワークロード</strong></span><span class="sxs-lookup"><span data-stu-id="521f7-168"><strong>Microsoft Lync Server 2013 Protocol Workloads</strong></span></span></p>
<img src="images/Dn594589.e00f8445-4e00-48f6-a3e2-f97334dde719(OCS.15).jpg" title="プロトコルワークロードのポスターのサムネイルビュー" alt="thumbnail view of protocol Workloads poster" />
<p><span data-ttu-id="521f7-170"><a href="http://go.microsoft.com/fwlink/?linkid=392970">Microsoft の Zoom.it を使用して、すべての詳細でポスターを拡大する</a></span><span class="sxs-lookup"><span data-stu-id="521f7-170"><a href="http://go.microsoft.com/fwlink/?linkid=392970">Zoom into the poster in full detail with Zoom.it from Microsoft</a></span></span></p>
<p><span data-ttu-id="521f7-171"><a href="http://go.microsoft.com/fwlink/?linkid=392512">PDF バージョン</a>(モバイルデバイスまたはタブレットコンピューターに最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-171"><a href="http://go.microsoft.com/fwlink/?linkid=392512">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="521f7-172"><a href="http://go.microsoft.com/fwlink/?linkid=392513">Visio のバージョン</a>(Visio を使用するユーザーに最適)</span><span class="sxs-lookup"><span data-stu-id="521f7-172"><a href="http://go.microsoft.com/fwlink/?linkid=392513">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="521f7-173">このポスターをダウンロードして、lync 2013、Lync Phone、Lync Web App、Lync for Mac、Lync Mobile w の機能と要件を理解してください。</span><span class="sxs-lookup"><span data-stu-id="521f7-173">Download this poster to understand the capabilities and requirements of Lync 2013, Lync Phone, Lync Web App, Lync for Mac, and Lync Mobile w.</span></span> <span data-ttu-id="521f7-174">Lync Server のワークロードが組織全体でのコミュニケーションを容易にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="521f7-174">See how Lync Server workloads facilitate communication across an organization.</span></span></p>
<p><span data-ttu-id="521f7-175">サイズ:24 x 36 インチ</span><span class="sxs-lookup"><span data-stu-id="521f7-175">Size: 24-by-36 inch</span></span></p>
<p><span data-ttu-id="521f7-176">このポスターは、Visio 2013 を使って作成されました。</span><span class="sxs-lookup"><span data-stu-id="521f7-176">This poster was created using Visio 2013.</span></span> <span data-ttu-id="521f7-177">特定の環境に対する変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="521f7-177">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="tips"></span>

<div>

## <a name="tips-for-printing-posters"></a><span data-ttu-id="521f7-178">ポスターを印刷するためのヒント</span><span class="sxs-lookup"><span data-stu-id="521f7-178">Tips for printing posters</span></span>

<span data-ttu-id="521f7-179">プロッターをお持ちの場合は、これらのポスターをフルサイズで印刷することができます。</span><span class="sxs-lookup"><span data-stu-id="521f7-179">If you have a plotter, you can print these posters in their full size.</span></span> <span data-ttu-id="521f7-180">プロッターを使用していない場合は、次の手順に従って、小さい用紙に印刷します。</span><span class="sxs-lookup"><span data-stu-id="521f7-180">If you don't have plotter, use the following steps to print on smaller paper.</span></span>

<span data-ttu-id="521f7-181">**小さい用紙にポスターを印刷するには**</span><span class="sxs-lookup"><span data-stu-id="521f7-181">**Print posters on smaller paper**</span></span>

1.  <span data-ttu-id="521f7-182">Visio でポスターを開きます。</span><span class="sxs-lookup"><span data-stu-id="521f7-182">Open the poster in Visio.</span></span>

2.  <span data-ttu-id="521f7-183">[**ファイル**] メニューの [**ページ設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="521f7-183">On the **File** menu, click **Page Setup**.</span></span>

3.  <span data-ttu-id="521f7-184">[**プリンターの設定**] タブの [**プリンターの用紙**] セクションで、印刷する用紙のサイズを選びます。</span><span class="sxs-lookup"><span data-stu-id="521f7-184">On the **Print Setup** tab, in the **Printer paper** section, select the size of paper you want to print on.</span></span>

4.  <span data-ttu-id="521f7-185">[**プリンターの設定**] タブの [**拡大縮小印刷**] セクションで [**自動調整 横**] をクリックして、[**1 枚 縦 1 枚**] と入力します。</span><span class="sxs-lookup"><span data-stu-id="521f7-185">On the **Print Setup** tab, in the **Print zoom** section, click **Fit to**, and then enter **1 sheet across by 1 sheet down**.</span></span>

5.  <span data-ttu-id="521f7-186">[**用紙サイズ**] タブの [**図面内容に合わせる**] をクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="521f7-186">On the **Page Size** tab, click **Size to fit drawing contents**, and then click **OK**.</span></span>

6.  <span data-ttu-id="521f7-187">[**ファイル**] メニューの [**印刷**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="521f7-187">On the **File** menu, click **Print**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

