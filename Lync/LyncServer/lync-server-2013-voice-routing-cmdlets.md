---
title: 'Lync Server 2013: ボイスルーティングコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routing cmdlets
ms:assetid: 8f05b25e-cc62-4d85-a5d8-4ed56f28dfbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416494(v=OCS.15)
ms:contentKeyID: 48184821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1d32ef285c30229510e0ff28ac978a8230fd01b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="61d2b-102">Lync Server 2013 の音声ルーティングコマンドレット</span><span class="sxs-lookup"><span data-stu-id="61d2b-102">Voice routing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61d2b-103">_**最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="61d2b-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="61d2b-104">音声ルートには、Microsoft Lync Server 2013 で、エンタープライズボイスユーザーから公衆交換電話網 (PSTN) または構内交換機 (PBX) 上の電話番号に着信をルーティングする方法について説明する手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="61d2b-104">Voice routes contain instructions that tell Microsoft Lync Server 2013 how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX).</span></span>

<div>

## <a name="voice-routing-cmdlets"></a><span data-ttu-id="61d2b-105">音声ルーティングコマンドレット</span><span class="sxs-lookup"><span data-stu-id="61d2b-105">Voice Routing Cmdlets</span></span>

<span data-ttu-id="61d2b-106">ボイスルーティングを構成するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="61d2b-106">Use the following cmdlets to configure voice routes.</span></span>

<span data-ttu-id="61d2b-107">**音声ルーティング**</span><span class="sxs-lookup"><span data-stu-id="61d2b-107">**Voice Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-108">[CsRoutingConfiguration を取得する](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-108">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-109">[新しい-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-109">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-110">[CsRoutingConfiguration の削除](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-110">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-111">[設定-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-111">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="61d2b-112">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-112">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-113">[新規-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-113">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-114">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-114">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-115">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-115">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-116">[テスト-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-116">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="61d2b-117">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-117">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="61d2b-118">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-118">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="61d2b-119">[新規-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-119">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="61d2b-120">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-120">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="61d2b-121">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-121">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="61d2b-122">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-122">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61d2b-123">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61d2b-123">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61d2b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="61d2b-124">See Also</span></span>


[<span data-ttu-id="61d2b-125">Lync Server 2013 のエンタープライズボイスコマンドレット</span><span class="sxs-lookup"><span data-stu-id="61d2b-125">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="61d2b-126">Lync Server 2013 の PSTN 接続コマンドレット</span><span class="sxs-lookup"><span data-stu-id="61d2b-126">PSTN connectivity cmdlets in Lync Server 2013</span></span>](lync-server-2013-pstn-connectivity-cmdlets.md)  


[<span data-ttu-id="61d2b-127">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="61d2b-127">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

