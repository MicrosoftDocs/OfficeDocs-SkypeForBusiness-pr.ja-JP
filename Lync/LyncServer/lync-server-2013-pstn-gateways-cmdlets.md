---
title: 'Lync Server 2013: PSTN ゲートウェイのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateways cmdlets
ms:assetid: 6a8aa6ea-f349-4b95-b3ce-c28d2ae0a84b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416491(v=OCS.15)
ms:contentKeyID: 48184397
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b3481d274f71ac5a0458e5ed1db018fc456f213
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-cmdlets-in-lync-server-2013"></a><span data-ttu-id="89ecb-102">Lync Server 2013 の PSTN ゲートウェイのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="89ecb-102">PSTN gateways cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89ecb-103">_**最終更新日:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="89ecb-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="89ecb-104">PSTN ゲートウェイを使用すると、エンタープライズボイスユーザーは、PSTN ネットワーク上のユーザー (つまり、公衆交換電話網) を使って電話をかけたり、通話を受けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="89ecb-104">PSTN gateways enable your Enterprise Voice users to make phone calls to, and receive phone calls from, people on the PSTN network (that is, the public switched telephone network).</span></span> <span data-ttu-id="89ecb-105">これらのゲートウェイは、仲介サーバーと PSTN ネットワーク間のブリッジとして機能します。</span><span class="sxs-lookup"><span data-stu-id="89ecb-105">These gateways act as a bridge between the Mediation Server and the PSTN network.</span></span>

<div>

## <a name="pstn-gateways-cmdlets"></a><span data-ttu-id="89ecb-106">PSTN ゲートウェイのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="89ecb-106">PSTN Gateways Cmdlets</span></span>

<span data-ttu-id="89ecb-107">[テスト用の CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))と[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))コマンドレットを使用して、ユーザーが PSTN ネットワーク経由で通話を発信できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="89ecb-107">The [Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15)) and [Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15)) cmdlets enable you to verify that users are able to make call over the PSTN network.</span></span>

<span data-ttu-id="89ecb-108">**PSTN ゲートウェイ**</span><span class="sxs-lookup"><span data-stu-id="89ecb-108">**PSTN Gateways**</span></span>

  - <span></span>  
    <span data-ttu-id="89ecb-109">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89ecb-109">[Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89ecb-110">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89ecb-110">[Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89ecb-111">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89ecb-111">[Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89ecb-112">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89ecb-112">[Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89ecb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="89ecb-113">See Also</span></span>


[<span data-ttu-id="89ecb-114">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="89ecb-114">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

