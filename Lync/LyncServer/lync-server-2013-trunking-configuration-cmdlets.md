---
title: 'Lync Server 2013: トランキング構成のコマンドレット'
description: 'Lync Server 2013: トランキング構成コマンドレット。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trunking configuration cmdlets
ms:assetid: 2c36b03a-b80f-4321-a448-6ba26b9357f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416489(v=OCS.15)
ms:contentKeyID: 48183703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4df1c60455275a87b85cb0b0d14f91e58436c80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548893"
---
# <a name="trunking-configuration-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e4f63-103">Lync Server 2013 でのトランク構成のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e4f63-103">Trunking configuration cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4f63-104">_**トピックの最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="e4f63-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="e4f63-p101">トランク構成のコマンドレットは、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX (Public Branch Exchange)、サービス プロバイダーのセッション境界コントローラー (SBC) などのトランキング ピア エンティティの設定の定義に使用します。これらの設定では、このトランクでメディア バイパスが有効か、特定の条件下で Real-time Transport Control Protocol (RTCP) パケットを送信するか、セキュア リアルタイム プロトコル (SRTP) 暗号化を要求するかなどを構成します。</span><span class="sxs-lookup"><span data-stu-id="e4f63-p101">Trunk configuration cmdlets are used to define settings for a trunking peer entity such as a public switched telephone network (PSTN) gateway, IP-public branch exchange (PBX), or Session Border Controller (SBC) at the service provider. These settings configure such things as whether media bypass is enabled on this trunk, whether real-time transport control protocol (RTCP) packets are sent under certain conditions, and whether to require secure real-time protocol (SRTP) encryption.</span></span>

<div>

## <a name="trunking-configuration-cmdlets"></a><span data-ttu-id="e4f63-107">トランク構成のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e4f63-107">Trunking Configuration Cmdlets</span></span>

<span data-ttu-id="e4f63-108">トランク構成には次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4f63-108">Use the following cmdlets for trunk configuration.</span></span>

<span data-ttu-id="e4f63-109">**トランク構成**</span><span class="sxs-lookup"><span data-stu-id="e4f63-109">**Trunking Configuration**</span></span>

  - <span data-ttu-id="e4f63-110">[Test-csintertrunkrouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-110">[Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e4f63-111">[New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-111">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="e4f63-112">[New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-112">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="e4f63-113">[New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-113">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="e4f63-114">[New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-114">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4f63-115">[New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-115">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4f63-116">[New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-116">[New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4f63-117">[New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-117">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4f63-118">[New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-118">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e4f63-119">[取得-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-119">[Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4f63-120">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-120">[Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4f63-121">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-121">[New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4f63-122">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-122">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4f63-123">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-123">[Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e4f63-124">[Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-124">[Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e4f63-125">[CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e4f63-125">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4f63-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4f63-126">See Also</span></span>


[<span data-ttu-id="e4f63-127">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="e4f63-127">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

