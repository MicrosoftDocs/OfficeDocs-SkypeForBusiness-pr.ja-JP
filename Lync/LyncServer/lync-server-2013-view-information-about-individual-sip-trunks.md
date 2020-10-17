---
title: 'Lync Server 2013: 個別の SIP トランクに関する情報の表示'
description: 'Lync Server 2013: 個々の SIP トランクに関する情報を表示します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c2f9fb1df4e916615cf7f95f95ae167d7216ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569613"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="64161-103">Lync Server 2013 の個々の SIP トランクに関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="64161-103">View information about individual SIP trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64161-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="64161-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="64161-105">SIP トランクは、Lync Server 2013 ボイスオーバー IP 電話ネットワークと公衆交換電話網を接続するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="64161-105">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="64161-106">以前のバージョンの製品では、トランクを使用して仲介サーバーから PSTN ゲートウェイに発信通話がルーティングされ、各ゲートウェイは 1 つのトランクに制限されていました。</span><span class="sxs-lookup"><span data-stu-id="64161-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="64161-107">その結果、PSTN ゲートウェイと SIP トランクは実質的に同一でした。</span><span class="sxs-lookup"><span data-stu-id="64161-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="64161-108">管理者にとって、このことは、関連付けられている PSTN ゲートウェイに関する情報を表示するだけで個々の SIP トランクに関する情報を表示できることを意味していました。</span><span class="sxs-lookup"><span data-stu-id="64161-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="64161-109">ただし、Lync Server 2013 では、複数のトランクを1つの PSTN ゲートウェイに割り当てることができるようになりました。これは、ゲートウェイとトランクが同じではなく、同じであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="64161-109">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="64161-110">そのため、管理者は、個々の SIP トランクに関する情報を表示するために、新しい [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64161-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="64161-111">Get-CsTrunk コマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="64161-111">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="64161-112">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="64161-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="64161-113">すべての SIP トランクに関する情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="64161-113">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="64161-114">次のコマンドは、組織で使用中のすべての SIP トランクに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="64161-114">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="64161-115">特定の SIP トランクに関する情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="64161-115">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="64161-116">このコマンドは、PstnGateway:192.168.0.240 という Identity を持つ SIP トランクに関する情報のみを返します。</span><span class="sxs-lookup"><span data-stu-id="64161-116">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="64161-117">プールに割り当てられているすべての SIP トランクに関する情報の表示</span><span class="sxs-lookup"><span data-stu-id="64161-117">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="64161-118">この例では、プール atl-cs-001.litwareinc.com に割り当てられているすべての SIP トランクについて情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="64161-118">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

