---
title: 'Lync Server 2013: エッジサーバーのポート範囲の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9124ba5b2a800190f49a9ac81fd9a2477eac215
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535024"
---
# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="fbc04-102">Lync Server 2013 でのエッジサーバーのポート範囲の構成</span><span class="sxs-lookup"><span data-stu-id="fbc04-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbc04-103">_**トピックの最終更新日:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="fbc04-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="fbc04-104">エッジサーバーでは、オーディオ、ビデオ、およびアプリケーション共有に対して個別のポート範囲を構成する必要はありません。同様に、エッジサーバーで使用されるポート範囲は、会議、アプリケーション、および仲介サーバーで使用されるポート範囲と一致している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fbc04-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="fbc04-105">この例を進める前に、このオプションが存在している間は、ポート範囲を変更しないことをお勧めします。これは、5万のポート範囲から移動すると、一部のシナリオに悪影響を及ぼす可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="fbc04-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="fbc04-106">たとえば、次のポート範囲を使用するように会議、アプリケーション、および仲介サーバーを構成したとします。</span><span class="sxs-lookup"><span data-stu-id="fbc04-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fbc04-107">パケットの種類</span><span class="sxs-lookup"><span data-stu-id="fbc04-107">Packet Type</span></span></th>
<th><span data-ttu-id="fbc04-108">開始ポート</span><span class="sxs-lookup"><span data-stu-id="fbc04-108">Starting Port</span></span></th>
<th><span data-ttu-id="fbc04-109">予約されたポートの数</span><span class="sxs-lookup"><span data-stu-id="fbc04-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fbc04-110">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="fbc04-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="fbc04-111">40803</span><span class="sxs-lookup"><span data-stu-id="fbc04-111">40803</span></span></p></td>
<td><p><span data-ttu-id="fbc04-112">8348</span><span class="sxs-lookup"><span data-stu-id="fbc04-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbc04-113">オーディオ</span><span class="sxs-lookup"><span data-stu-id="fbc04-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="fbc04-114">49152</span><span class="sxs-lookup"><span data-stu-id="fbc04-114">49152</span></span></p></td>
<td><p><span data-ttu-id="fbc04-115">8348</span><span class="sxs-lookup"><span data-stu-id="fbc04-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fbc04-116">ビデオ</span><span class="sxs-lookup"><span data-stu-id="fbc04-116">Video</span></span></p></td>
<td><p><span data-ttu-id="fbc04-117">57500</span><span class="sxs-lookup"><span data-stu-id="fbc04-117">57500</span></span></p></td>
<td><p><span data-ttu-id="fbc04-118">8034</span><span class="sxs-lookup"><span data-stu-id="fbc04-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fbc04-119"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="fbc04-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="fbc04-120">24730</span><span class="sxs-lookup"><span data-stu-id="fbc04-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fbc04-121">ご覧のとおり、オーディオ、ビデオ、およびアプリケーション共有のポート範囲は、ポート40803で開始し、合計24732ポートを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="fbc04-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="fbc04-122">必要に応じて、Lync Server 管理シェルから次のようなコマンドを実行すると、指定したエッジ サーバーがこれらのポート範囲全体を使用するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="fbc04-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="fbc04-123">または、次のコマンドを使用して、組織内のすべてのエッジ サーバーを同時に構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbc04-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="fbc04-124">この Lync Server 管理シェルコマンドを使用して、エッジサーバーの現在のポート設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fbc04-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="fbc04-125">これらのオプションを提供していますが、ポート構成用のものを残しておくことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fbc04-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

