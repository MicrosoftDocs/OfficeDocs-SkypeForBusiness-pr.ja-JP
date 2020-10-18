---
title: Lync Server 2013 の技術ダイアグラム
description: Lync Server 2013 の技術ダイアグラム
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical diagrams
ms:assetid: 7b6da49b-ac72-4ab0-8957-166e330b38fa
ms:mtpsurl: https://technet.microsoft.com/library/Dn594589(v=OCS.15)
ms:contentKeyID: 61180439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4dee8dab089de924317d6979e6d085072b0beab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577203"
---
# <a name="technical-diagrams-for-lync-server-2013"></a><span data-ttu-id="64d6b-103">Lync Server 2013 の技術ダイアグラム</span><span class="sxs-lookup"><span data-stu-id="64d6b-103">Technical diagrams for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64d6b-104">_**トピックの最終更新日:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="64d6b-104">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="64d6b-105">**概要:**  これらの図は、Lync 2013 で推奨されるソリューションの視覚的な表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="64d6b-105">**Summary:** These diagrams provide visual representations of recommended solutions for Lync 2013.</span></span>

<span data-ttu-id="64d6b-106">これらのリソースは、Visio (.vsd) 形式 (Visio 2010 または Visio 2013) および PDF 形式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="64d6b-106">These resources are available in Visio (.vsd) format (Visio 2010 or Visio 2013) and PDF format.</span></span> <span data-ttu-id="64d6b-107">ドキュメントを印刷する方法については、「ポスターの印刷に関するヒント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64d6b-107">For information about how to print documents, see Tips for printing posters.</span></span>

<span data-ttu-id="64d6b-p102">これらのファイルを表示するには、特別なソフトウェアが必要な場合があります。詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64d6b-p102">You might need additional software to view these files. See the following table for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64d6b-110">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="64d6b-110">File type</span></span></th>
<th><span data-ttu-id="64d6b-111">ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="64d6b-111">Software</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64d6b-112">.vsd</span><span class="sxs-lookup"><span data-stu-id="64d6b-112">.vsd</span></span></p></td>
<td><p><span data-ttu-id="64d6b-113">Visio 2010、Visio 2013、または <a href="https://go.microsoft.com/fwlink/?linkid=393676">無料の visio viewer</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-113">Visio 2010, Visio 2013, or the <a href="https://go.microsoft.com/fwlink/?linkid=393676">free Visio viewer</a></span></span></p>
<p><span data-ttu-id="64d6b-114">Visio Viewer を使用している場合は、VSD のリンクを右クリックし、 <strong>[対象をファイルに保存]</strong> をクリックして、ファイルをコンピューターに保存した後、コンピューターからファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="64d6b-114">If you use the Visio viewer, right-click the VSD link, click <strong>Save Target As</strong>, save the file to your computer, and then open the file from your computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64d6b-115">.pdf</span><span class="sxs-lookup"><span data-stu-id="64d6b-115">.pdf</span></span></p></td>
<td><p><span data-ttu-id="64d6b-116"><a href="https://go.microsoft.com/fwlink/?linkid=393675">Adobe Reader</a> などの任意の PDF ビューア</span><span class="sxs-lookup"><span data-stu-id="64d6b-116">Any PDF viewer, such as <a href="https://go.microsoft.com/fwlink/?linkid=393675">Adobe Reader</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64d6b-117">.zip</span><span class="sxs-lookup"><span data-stu-id="64d6b-117">.zip</span></span></p></td>
<td><p><span data-ttu-id="64d6b-118">任意のファイル圧縮ユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="64d6b-118">Any file compression utility.</span></span> <span data-ttu-id="64d6b-119">Windows 7 および8これらのファイルをネイティブで開きます。</span><span class="sxs-lookup"><span data-stu-id="64d6b-119">Windows 7 and 8 open these files natively.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="posters"></a><span data-ttu-id="64d6b-120">ポスター</span><span class="sxs-lookup"><span data-stu-id="64d6b-120">Posters</span></span>

<span data-ttu-id="64d6b-121">これらのポスターは特定の技術的な領域を詳細に説明しており、TechNet またはダウンロードセンターで入手可能なコンテンツの対応する記事で使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-121">These posters detail a specific technical area, and are intended to be used with corresponding articles on TechNet or content available on the download center.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64d6b-122">Title</span><span class="sxs-lookup"><span data-stu-id="64d6b-122">Title</span></span></th>
<th><span data-ttu-id="64d6b-123">説明</span><span class="sxs-lookup"><span data-stu-id="64d6b-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64d6b-124"><strong>Lync Server 2013 の社内アーキテクチャ</strong></span><span class="sxs-lookup"><span data-stu-id="64d6b-124"><strong>Lync Server 2013 On-Premises Architectures</strong></span></span></p>
<img src="images/Dn594589.36530bb8-732f-4be0-9502-082c01df9fba(OCS.15).jpg" title="Lync アーキテクチャポスターのサムネイル" alt="thumbnail of Lync architectures poster" />
<p><span data-ttu-id="64d6b-126">Microsoft からの Zoom.it (デスクトップまたはラップトップコンピューターに最適) につい<a href="https://go.microsoft.com/fwlink/?linkid=392974">て、詳細な情報をポスターに表示します</a>。</span><span class="sxs-lookup"><span data-stu-id="64d6b-126"><a href="https://go.microsoft.com/fwlink/?linkid=392974">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="64d6b-127"><a href="https://go.microsoft.com/fwlink/?linkid=392578">PDF 版</a> (モバイルデバイスやタブレットコンピューターに最適)</span><span class="sxs-lookup"><span data-stu-id="64d6b-127"><a href="https://go.microsoft.com/fwlink/?linkid=392578">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="64d6b-128"><a href="https://go.microsoft.com/fwlink/?linkid=392579">Visio バージョン</a> (visio ユーザーに最適)</span><span class="sxs-lookup"><span data-stu-id="64d6b-128"><a href="https://go.microsoft.com/fwlink/?linkid=392579">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="64d6b-129">ポスターは、計画と展開に関するアーキテクチャ上のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="64d6b-129">Poster provides architectural guidance for planning and deployment.</span></span> <span data-ttu-id="64d6b-130">このポスターには、Lync Server の一般的なコンポーネント、展開を計画するときに使用する用語、新機能、サーバーの役割、およびインストールの概要が記載されています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-130">The poster contains information about common components of Lync Server, terminology used when planning a deployment, new features, server roles, and an installation overview.</span></span> <span data-ttu-id="64d6b-131">さらに、ポスターには、高可用性と障害復旧だけでなく、小規模、中規模、大規模なサンプルトポロジのアーキテクチャの例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-131">In addition the poster contains example architectures for increasing high availability and disaster recovery as well as small, medium, and large sample topologies.</span></span></p>
<p><span data-ttu-id="64d6b-132">サイズ:34 x 44 インチ</span><span class="sxs-lookup"><span data-stu-id="64d6b-132">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="64d6b-133">このポスターは、Visio 2013 を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-133">This poster was created using Visio 2013.</span></span> <span data-ttu-id="64d6b-134">特定の環境では、変更を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64d6b-134">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64d6b-135"><strong>Lync 通話品質の方法論</strong></span><span class="sxs-lookup"><span data-stu-id="64d6b-135"><strong>Lync Call Quality Methodology</strong></span></span></p>
<img src="images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg" title="CQM プロセスを説明するポスター" alt="Poster describing the CQM process" />
<p><span data-ttu-id="64d6b-137">Microsoft からの Zoom.it (デスクトップまたはラップトップコンピューターに最適) につい<a href="https://go.microsoft.com/fwlink/?linkid=392972">て、詳細な情報をポスターに表示します</a>。</span><span class="sxs-lookup"><span data-stu-id="64d6b-137"><a href="https://go.microsoft.com/fwlink/?linkid=392972">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="64d6b-138"><a href="https://go.microsoft.com/fwlink/?linkid=391841">Visio と PDF の両方のバージョンと .zip ファイル</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-138"><a href="https://go.microsoft.com/fwlink/?linkid=391841">Visio and PDF versions together in a .zip file</a></span></span></p></td>
<td><p><span data-ttu-id="64d6b-139">エンタープライズ voip の品質に影響する問題について、Lync システムのトラブルシューティングについて説明しているポスターです。</span><span class="sxs-lookup"><span data-stu-id="64d6b-139">Poster describing Lync system troubleshooting, especially for issues affecting enterprise voice quality.</span></span> <span data-ttu-id="64d6b-140">このポスターは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="64d6b-140">Use this poster with:</span></span></p>
<ul>
<li><p><span data-ttu-id="64d6b-141"><a href="https://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server ネットワークガイド</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-141"><a href="https://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server Networking Guide</a></span></span></p></li>
<li><p><span data-ttu-id="64d6b-142"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Server 2013 の Lync 通話品質の方法論</a> (アクセシビリティ記事)</span><span class="sxs-lookup"><span data-stu-id="64d6b-142"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Call Quality Methodology in Lync Server 2013</a> (accessibility article)</span></span></p></li>
<li><p><span data-ttu-id="64d6b-143"><a href="lync-server-2013-poster-key-health-indicators.md">Lync Server 2013 (アクセシビリティに関する記事) のキー正常性インジケーター</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-143"><a href="lync-server-2013-poster-key-health-indicators.md">Key Health Indicators in Lync Server 2013</a> (accessibility article)</span></span></p></li>
</ul>
<p><span data-ttu-id="64d6b-144">サイズ:34 x 44 インチ</span><span class="sxs-lookup"><span data-stu-id="64d6b-144">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="64d6b-145">このポスターは、Visio 2010 を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-145">This poster was created using Visio 2010.</span></span> <span data-ttu-id="64d6b-146">特定の環境では、変更を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64d6b-146">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64d6b-147"><strong>主要な正常性インジケーター</strong></span><span class="sxs-lookup"><span data-stu-id="64d6b-147"><strong>Key Health Indicators</strong></span></span></p>
<img src="images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg" title="KHI データを使用したトラブルシューティングについて説明するポスター" alt="Poster describing troubleshooting using KHI data" />
<p><span data-ttu-id="64d6b-149">Microsoft からの Zoom.it (デスクトップまたはラップトップコンピューターに最適) につい<a href="https://go.microsoft.com/fwlink/?linkid=392971">て、詳細な情報をポスターに表示します</a>。</span><span class="sxs-lookup"><span data-stu-id="64d6b-149"><a href="https://go.microsoft.com/fwlink/?linkid=392971">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="64d6b-150"><a href="https://go.microsoft.com/fwlink/?linkid=391838">Visio と PDF の両方のバージョンと .zip ファイル</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-150"><a href="https://go.microsoft.com/fwlink/?linkid=391838">Visio and PDF versions together in a .zip file</a></span></span></p></td>
<td><p><span data-ttu-id="64d6b-151">基本的なサーバーの正常性と、Lync 実装における特定のサーバーの役割の両方について、サーバーのトラブルシューティング指標を説明するポスター。</span><span class="sxs-lookup"><span data-stu-id="64d6b-151">Poster describing server troubleshooting metrics both for basic server health and for a given server’s role in the Lync implementation.</span></span> <span data-ttu-id="64d6b-152">このポスターは次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="64d6b-152">Use this poster with:</span></span></p>
<ul>
<li><p><span data-ttu-id="64d6b-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server ネットワークガイド</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server Networking Guide</a></span></span></p></li>
<li><p><span data-ttu-id="64d6b-154"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Server 2013 の Lync 通話品質の方法論</a> (アクセシビリティ記事)</span><span class="sxs-lookup"><span data-stu-id="64d6b-154"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Call Quality Methodology in Lync Server 2013</a> (accessibility article)</span></span></p></li>
<li><p><span data-ttu-id="64d6b-155"><a href="lync-server-2013-poster-key-health-indicators.md">Lync Server 2013 (アクセシビリティに関する記事) のキー正常性インジケーター</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-155"><a href="lync-server-2013-poster-key-health-indicators.md">Key Health Indicators in Lync Server 2013</a> (accessibility article)</span></span></p></li>
</ul>
<p><span data-ttu-id="64d6b-156">サイズ:17 x 22 インチ</span><span class="sxs-lookup"><span data-stu-id="64d6b-156">Size: 17-by-22 inch</span></span></p>
<p><span data-ttu-id="64d6b-157">このポスターは、Visio 2010 を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-157">This poster was created using Visio 2010.</span></span> <span data-ttu-id="64d6b-158">特定の環境では、変更を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64d6b-158">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64d6b-159"><strong>Lync 2013 プラットフォーム オプション</strong></span><span class="sxs-lookup"><span data-stu-id="64d6b-159"><strong>Lync 2013 Platform Options</strong></span></span></p>
<img src="images/Dn594589.c5b66828-c3cf-4654-bb75-b93f97d085b3(OCS.15).jpg" title="プラットフォームオプションのポスターのサムネイル表示" alt="thumbnail view of platform options poster" />
<p><span data-ttu-id="64d6b-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=391840">Microsoft の Zoom.it を使用して、詳細な情報でポスターにズームする</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=391840">Zoom into the poster in full detail with Zoom.it from Microsoft</a></span></span></p>
<p><span data-ttu-id="64d6b-162"><a href="https://go.microsoft.com/fwlink/p/?linkid=391837">PDF 版</a> (モバイルデバイスやタブレットコンピューターに最適)</span><span class="sxs-lookup"><span data-stu-id="64d6b-162"><a href="https://go.microsoft.com/fwlink/p/?linkid=391837">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="64d6b-163"><a href="https://go.microsoft.com/fwlink/p/?linkid=391839">Visio バージョン</a> (visio ユーザーに最適)</span><span class="sxs-lookup"><span data-stu-id="64d6b-163"><a href="https://go.microsoft.com/fwlink/p/?linkid=391839">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="64d6b-164">このポスターでは、Lync 2013 に対して使用可能なプラットフォームのオプションについて説明します。また、Bdm のお客様は、Microsoft 365、ハイブリッド Lync、Lync Server オンプレミスおよびホストされた Lync で Lync Online から選択できます。</span><span class="sxs-lookup"><span data-stu-id="64d6b-164">This poster describes the available platform options for Lync 2013 to BDMs and architects  Customers can choose from Lync Online with Microsoft 365, Hybrid Lync, Lync Server on-premises and Hosted Lync.</span></span> <span data-ttu-id="64d6b-165">ポスターには、それぞれに最も理想的なシナリオ、ライセンスの要件、IT プロフェッショナルの責任など、アーキテクチャーに関するオプションの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-165">The poster includes details of each architectural option, including the most ideal scenarios for each, the license requirements and IT Pro responsibilities.</span></span></p>
<p><span data-ttu-id="64d6b-166">サイズ:34 x 44 インチ</span><span class="sxs-lookup"><span data-stu-id="64d6b-166">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="64d6b-167">このポスターは、Visio 2013 を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-167">This poster was created using Visio 2013.</span></span> <span data-ttu-id="64d6b-168">特定の環境では、変更を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64d6b-168">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64d6b-169"><strong>Microsoft Lync Server 2013 プロトコルワークロード</strong></span><span class="sxs-lookup"><span data-stu-id="64d6b-169"><strong>Microsoft Lync Server 2013 Protocol Workloads</strong></span></span></p>
<img src="images/Dn594589.e00f8445-4e00-48f6-a3e2-f97334dde719(OCS.15).jpg" title="プロトコルワークロードポスターのサムネイルビュー" alt="thumbnail view of protocol Workloads poster" />
<p><span data-ttu-id="64d6b-171"><a href="https://go.microsoft.com/fwlink/?linkid=392970">Microsoft の Zoom.it を使用して、詳細な情報でポスターにズームする</a></span><span class="sxs-lookup"><span data-stu-id="64d6b-171"><a href="https://go.microsoft.com/fwlink/?linkid=392970">Zoom into the poster in full detail with Zoom.it from Microsoft</a></span></span></p>
<p><span data-ttu-id="64d6b-172"><a href="https://go.microsoft.com/fwlink/?linkid=392512">PDF 版</a> (モバイルデバイスやタブレットコンピューターに最適)</span><span class="sxs-lookup"><span data-stu-id="64d6b-172"><a href="https://go.microsoft.com/fwlink/?linkid=392512">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="64d6b-173"><a href="https://go.microsoft.com/fwlink/?linkid=392513">Visio バージョン</a> (visio ユーザーに最適)</span><span class="sxs-lookup"><span data-stu-id="64d6b-173"><a href="https://go.microsoft.com/fwlink/?linkid=392513">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="64d6b-174">Lync 2013、Lync Phone、Lync Web App、Lync for Mac、Lync Mobile w の機能と要件について理解するには、このポスターをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="64d6b-174">Download this poster to understand the capabilities and requirements of Lync 2013, Lync Phone, Lync Web App, Lync for Mac, and Lync Mobile w.</span></span> <span data-ttu-id="64d6b-175">組織全体での Lync Server ワークロードの円滑なコミュニケーション方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64d6b-175">See how Lync Server workloads facilitate communication across an organization.</span></span></p>
<p><span data-ttu-id="64d6b-176">サイズ:24 x 36 インチ</span><span class="sxs-lookup"><span data-stu-id="64d6b-176">Size: 24-by-36 inch</span></span></p>
<p><span data-ttu-id="64d6b-177">このポスターは、Visio 2013 を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="64d6b-177">This poster was created using Visio 2013.</span></span> <span data-ttu-id="64d6b-178">特定の環境では、変更を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64d6b-178">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="tips"></span>

<div>

## <a name="tips-for-printing-posters"></a><span data-ttu-id="64d6b-179">ポスターの印刷に関するヒント</span><span class="sxs-lookup"><span data-stu-id="64d6b-179">Tips for printing posters</span></span>

<span data-ttu-id="64d6b-p114">プロッターがある場合は、ポスターをフル サイズで印刷できます。プロッターがない場合は、次の手順を実行して小さな用紙に印刷します。</span><span class="sxs-lookup"><span data-stu-id="64d6b-p114">If you have a plotter, you can print these posters in their full size. If you don't have plotter, use the following steps to print on smaller paper.</span></span>

<span data-ttu-id="64d6b-182">**ポスターを小さな用紙に印刷する**</span><span class="sxs-lookup"><span data-stu-id="64d6b-182">**Print posters on smaller paper**</span></span>

1.  <span data-ttu-id="64d6b-183">ポスターを Visio で開きます。</span><span class="sxs-lookup"><span data-stu-id="64d6b-183">Open the poster in Visio.</span></span>

2.  <span data-ttu-id="64d6b-184">[ **ファイル**] メニューの [ **ページ設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64d6b-184">On the **File** menu, click **Page Setup**.</span></span>

3.  <span data-ttu-id="64d6b-185">[ **プリンターの設定**] タブの [ **プリンターの用紙**] で、印刷用紙のサイズを選択します。</span><span class="sxs-lookup"><span data-stu-id="64d6b-185">On the **Print Setup** tab, in the **Printer paper** section, select the size of paper you want to print on.</span></span>

4.  <span data-ttu-id="64d6b-186">[ **プリンターの設定**] タブの [ **拡大縮小印刷**] で、[ **自動調整**] をクリックし、「 **横 1 枚、縦 1 枚**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="64d6b-186">On the **Print Setup** tab, in the **Print zoom** section, click **Fit to**, and then enter **1 sheet across by 1 sheet down**.</span></span>

5.  <span data-ttu-id="64d6b-187">[ **ページ サイズ**] タブで、[ **図面内容に合わせる**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64d6b-187">On the **Page Size** tab, click **Size to fit drawing contents**, and then click **OK**.</span></span>

6.  <span data-ttu-id="64d6b-188">[ **ファイル**] メニューの [ **印刷**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64d6b-188">On the **File** menu, click **Print**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

