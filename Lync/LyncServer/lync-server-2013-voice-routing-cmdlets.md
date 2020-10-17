---
title: 'Lync Server 2013: 音声ルーティングのコマンドレット'
description: 'Lync Server 2013: 音声ルーティングのコマンドレット。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routing cmdlets
ms:assetid: 8f05b25e-cc62-4d85-a5d8-4ed56f28dfbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416494(v=OCS.15)
ms:contentKeyID: 48184821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b895eb84bccea6fcb014e61d5609b45c8c14d4cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554073"
---
# <a name="voice-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="5dcaf-103">Lync Server 2013 での音声ルーティングのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5dcaf-103">Voice routing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dcaf-104">_**トピックの最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="5dcaf-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="5dcaf-105">音声ルートには、Microsoft Lync Server 2013 に対して、エンタープライズ Voip ユーザーから公衆交換電話網 (PSTN) または構内交換機 (PBX) 上の電話番号への通話をルーティングする方法を指示する指示が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5dcaf-105">Voice routes contain instructions that tell Microsoft Lync Server 2013 how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX).</span></span>

<div>

## <a name="voice-routing-cmdlets"></a><span data-ttu-id="5dcaf-106">音声ルーティングのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5dcaf-106">Voice Routing Cmdlets</span></span>

<span data-ttu-id="5dcaf-107">ボイス ルートを構成するには、以下のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5dcaf-107">Use the following cmdlets to configure voice routes.</span></span>

<span data-ttu-id="5dcaf-108">**音声ルーティング**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-108">**Voice Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-109">[-CsRoutingConfiguration の取得](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-109">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-110">[新しい-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-110">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-111">[-CsRoutingConfiguration の削除](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-111">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-112">[-CsRoutingConfiguration の設定](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-112">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5dcaf-113">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-113">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-114">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-114">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-115">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-115">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-116">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-116">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-117">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-117">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="5dcaf-118">[Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-118">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="5dcaf-119">[Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-119">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="5dcaf-120">[Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-120">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="5dcaf-121">[Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-121">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="5dcaf-122">[Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-122">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5dcaf-123">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-123">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5dcaf-124">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5dcaf-124">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5dcaf-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dcaf-125">See Also</span></span>


[<span data-ttu-id="5dcaf-126">Lync Server 2013 のエンタープライズ Voip のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5dcaf-126">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="5dcaf-127">Lync Server 2013 の PSTN 接続のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5dcaf-127">PSTN connectivity cmdlets in Lync Server 2013</span></span>](lync-server-2013-pstn-connectivity-cmdlets.md)  


[<span data-ttu-id="5dcaf-128">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="5dcaf-128">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

