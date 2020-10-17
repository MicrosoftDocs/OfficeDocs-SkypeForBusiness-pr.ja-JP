---
title: 'Lync Server 2013: ベストプラクティスアナライザーを実行するための要件'
description: 'Lync Server 2013: ベストプラクティスアナライザーを実行するための要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for running Best Practices Analyzer
ms:assetid: 3c7dc44e-5f8a-40a7-9ebb-9ad707ac0007
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591345(v=OCS.15)
ms:contentKeyID: 48183880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58a604a2b7d4a2d60a366d288b448ce8f255e5e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542483"
---
# <a name="requirements-for-running-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="1d46d-103">Lync Server 2013 でベストプラクティスアナライザーを実行するための要件</span><span class="sxs-lookup"><span data-stu-id="1d46d-103">Requirements for running Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d46d-104">_**トピックの最終更新日:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="1d46d-104">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="1d46d-105">Lync server 2013、ベストプラクティスアナライザーを使用して Lync Server 2013 環境をスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-105">You can use Lync Server 2013, Best Practices Analyzer to scan your Lync Server 2013 environment.</span></span> <span data-ttu-id="1d46d-106">これを使用して以前の環境をスキャンすることはできませんが、以前のバージョンのツールを使用してこれらの環境をスキャンすることはできます。</span><span class="sxs-lookup"><span data-stu-id="1d46d-106">You cannot use it to scan previous environments, but you can use the previous versions of the tool to scan those environments.</span></span> <span data-ttu-id="1d46d-107">Lync Server 2010 および Office Communications Server 2007 R2 バージョンのベストプラクティスアナライザーのダウンロードと使用の詳細については、「」 [https://go.microsoft.com/fwlink/p/?linkId=210536](https://go.microsoft.com/fwlink/p/?linkid=256358) および「Office Communications server のベストプラクティスアナライザー For Office Communications server 2007 および Office Communications server 2007 R2」を参照して2010ください [https://go.microsoft.com/fwlink/p/?linkId=256358](https://go.microsoft.com/fwlink/p/?linkid=210651) 。</span><span class="sxs-lookup"><span data-stu-id="1d46d-107">For details about downloading and using the Lync Server 2010 and Office Communications Server 2007 R2 versions of Best Practices Analyzer, see "Lync Server 2010, Best Practices Analyzer" at [https://go.microsoft.com/fwlink/p/?linkId=210536](https://go.microsoft.com/fwlink/p/?linkid=256358) and "Best Practices Analyzer for Office Communications Server 2007 and Office Communications Server 2007 R2" at [https://go.microsoft.com/fwlink/p/?linkId=256358](https://go.microsoft.com/fwlink/p/?linkid=210651).</span></span>

<span data-ttu-id="1d46d-108">スキャンを開始する前に、Lync Server 2013 環境内のすべてのコンポーネントが実行されていて、オンラインになっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d46d-108">Prior to starting your scan, you should ensure that all components in your Lync Server 2013 environment are running and online.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d46d-p102">ファイアウォールの設定、アクセス許可など、エッジ サーバーの構成や関連する境界ネットワーク設定によっては、ベスト プラクティス アナライザーがエッジ サーバーにアクセスできず、スキャンを実行できない可能性があります。スキャン対象にエッジ サーバーが含まれ、エッジ サーバーへのアクセスに問題が発生していることがレポートで報告された場合、その問題がレポートに表示されないようにするには、エッジ サーバーをスキャン オプションから削除し、再度スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d46d-p102">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue with accessing Edge Servers, you might want to remove Edge Servers from the scan options and run the scan again so that the issues do not show up in the report.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

