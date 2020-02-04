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
ms.openlocfilehash: b6eddf59f6fe4b2575e0e7d70adddb2e94c90e05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="34c56-102">Lync Server 2013 でエッジサーバーのポート範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="34c56-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34c56-103">_**最終更新日:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="34c56-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="34c56-104">エッジサーバーでは、音声、ビデオ、アプリケーション共有のために個別のポート範囲を構成する必要はありません。同様に、エッジサーバーに使われるポート範囲も、会議、アプリケーション、および仲介サーバーで使用されるポート範囲と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34c56-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="34c56-105">例を始める前に、このオプションが存在している間、ポート範囲を変更しないことをお勧めします。これは、5万のポート範囲から移動した場合に、一部のシナリオに悪影響を与える可能性があるため、これを強調することが重要です。</span><span class="sxs-lookup"><span data-stu-id="34c56-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="34c56-106">たとえば、次のようなポート範囲を使用するように会議、アプリケーション、および仲介業者を構成したとします。</span><span class="sxs-lookup"><span data-stu-id="34c56-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34c56-107">パケットの種類</span><span class="sxs-lookup"><span data-stu-id="34c56-107">Packet Type</span></span></th>
<th><span data-ttu-id="34c56-108">開始ポート</span><span class="sxs-lookup"><span data-stu-id="34c56-108">Starting Port</span></span></th>
<th><span data-ttu-id="34c56-109">予約されているポートの数</span><span class="sxs-lookup"><span data-stu-id="34c56-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34c56-110">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="34c56-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="34c56-111">40803</span><span class="sxs-lookup"><span data-stu-id="34c56-111">40803</span></span></p></td>
<td><p><span data-ttu-id="34c56-112">8348</span><span class="sxs-lookup"><span data-stu-id="34c56-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c56-113">オーディオ</span><span class="sxs-lookup"><span data-stu-id="34c56-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="34c56-114">49152</span><span class="sxs-lookup"><span data-stu-id="34c56-114">49152</span></span></p></td>
<td><p><span data-ttu-id="34c56-115">8348</span><span class="sxs-lookup"><span data-stu-id="34c56-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34c56-116">ビデオ</span><span class="sxs-lookup"><span data-stu-id="34c56-116">Video</span></span></p></td>
<td><p><span data-ttu-id="34c56-117">57500</span><span class="sxs-lookup"><span data-stu-id="34c56-117">57500</span></span></p></td>
<td><p><span data-ttu-id="34c56-118">8034</span><span class="sxs-lookup"><span data-stu-id="34c56-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34c56-119"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="34c56-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="34c56-120">24730</span><span class="sxs-lookup"><span data-stu-id="34c56-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="34c56-121">ご覧のとおり、オーディオ、ビデオ、およびアプリケーション共有のポート範囲は、ポート40803から始まり、24732ポートの合計をカバーしています。</span><span class="sxs-lookup"><span data-stu-id="34c56-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="34c56-122">必要に応じて、次のようなポート値を使用するように特定のエッジサーバーを構成するには、Lync Server 管理シェルで、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="34c56-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="34c56-123">または、次のコマンドを使用して、組織内のすべてのエッジサーバーを同時に構成します。</span><span class="sxs-lookup"><span data-stu-id="34c56-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="34c56-124">次の Lync Server 管理シェルコマンドを使用して、エッジサーバーの現在のポート設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="34c56-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="34c56-125">ここでも、これらのオプションを用意していますが、ポート構成のためにそのままにしておくことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34c56-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

