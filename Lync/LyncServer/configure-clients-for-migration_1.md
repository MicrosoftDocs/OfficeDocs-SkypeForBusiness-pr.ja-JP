---
title: 移行用にクライアントを構成する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a8f8cfcab36c1bfa47eb8ee4a24ebe683398707
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="937d3-102">移行用にクライアントを構成する</span><span class="sxs-lookup"><span data-stu-id="937d3-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="937d3-103">_**トピックの最終更新日:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="937d3-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="937d3-104">このトピックでは、Lync Server 2013 に移行する前に実行する必要のある推奨クライアント展開手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="937d3-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="937d3-105">これらの構成の変更は、Office Communications Server 2007 R2 で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="937d3-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="937d3-106">移行の前にこれらの手順を実行することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="937d3-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="937d3-107">詳細については、「 [Lync Server 2013 でのクライアントとデバイスの計画](lync-server-2013-planning-for-clients-and-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="937d3-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="937d3-108">移行の前にクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="937d3-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="937d3-109">最新の Office Communications Server 2007 R2 サーバー、クライアント、およびデバイスの更新プログラム (ホットフィックス) を展開します。</span><span class="sxs-lookup"><span data-stu-id="937d3-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="937d3-110">Office Communications Server 2007 R2 の更新プログラムを適用する</span><span class="sxs-lookup"><span data-stu-id="937d3-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="937d3-111">Communicator 2007 R2 の累積的な更新プログラムパッケージの説明</span><span class="sxs-lookup"><span data-stu-id="937d3-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="937d3-112">デバイスのソフトウェア更新プログラムの取得</span><span class="sxs-lookup"><span data-stu-id="937d3-112">Obtaining Software Updates for Devices</span></span>](https://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="937d3-113">Office Communications Server 2007 R2 では、クライアントバージョンフィルターを使用して、Office Communications Server 2007 R2 クライアントのみに最新の更新プログラムをインストールしてサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="937d3-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="937d3-114">Office Communications Server 2007 R2 では、クライアントバージョンフィルタリングを使用して Lync Server 2013 クライアントのサインインをブロックします。</span><span class="sxs-lookup"><span data-stu-id="937d3-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="937d3-115">次の表に記載されているバージョンフィルターを追加するには、「**クライアントバージョンフィルター**をで構成する」で説明されている手順に従い [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) ます。</span><span class="sxs-lookup"><span data-stu-id="937d3-115">Follow the steps described in **Configuring Client Version Filtering** at [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="937d3-116">各バージョン フィルターで、[**ブロック**] のアクションを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="937d3-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="937d3-117">クライアント</span><span class="sxs-lookup"><span data-stu-id="937d3-117">Client</span></span></th>
    <th><span data-ttu-id="937d3-118">ユーザー エージェントのヘッダー</span><span class="sxs-lookup"><span data-stu-id="937d3-118">User agent header</span></span></th>
    <th><span data-ttu-id="937d3-119">バージョン</span><span class="sxs-lookup"><span data-stu-id="937d3-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="937d3-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="937d3-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="937d3-121">OC</span><span class="sxs-lookup"><span data-stu-id="937d3-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="937d3-122">15.*..*\*</span><span class="sxs-lookup"><span data-stu-id="937d3-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="937d3-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="937d3-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="937d3-124">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="937d3-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="937d3-125">5.*..*\*</span><span class="sxs-lookup"><span data-stu-id="937d3-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="937d3-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="937d3-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="937d3-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="937d3-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="937d3-128">4.*..*\*</span><span class="sxs-lookup"><span data-stu-id="937d3-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

