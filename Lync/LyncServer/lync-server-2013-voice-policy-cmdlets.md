---
title: 'Lync Server 2013: 音声ポリシーのコマンドレット'
description: 'Lync Server 2013: 音声ポリシーのコマンドレット。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policy cmdlets
ms:assetid: 92744ec6-754d-498b-b430-dcd5c985ce10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415663(v=OCS.15)
ms:contentKeyID: 48184800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88f87f232ab9922a3e204f11e5231457a867426a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549793"
---
# <a name="voice-policy-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e5d92-103">Lync Server 2013 の音声ポリシーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e5d92-103">Voice policy cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5d92-104">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e5d92-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e5d92-p101">エンタープライズ VoIP の管理には、音声ポリシーやダイヤル プランの構成、および音声ポリシーとボイス ルートの関連付けが含まれます。音声ポリシーの管理に関連するコマンドレットは、同時呼び出し (会社の電話への着信時に 2 番目の電話を呼び出す機能)、着信の転送、ダイヤル要件など、各機能の設定に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5d92-p101">Managing Enterprise Voice includes configuring such things as voice policies and dial plans, and associating voice policies with voice routes. Cmdlets related to managing voice policies can be used to set features such as simultaneous ringing (the ability to have a second phone ring each time someone calls your office phone), call forwarding, and dialing requirement.</span></span>

<div>

## <a name="voice-policy-cmdlets"></a><span data-ttu-id="e5d92-107">音声ポリシーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e5d92-107">Voice Policy Cmdlets</span></span>

<span data-ttu-id="e5d92-108">以下のコマンドレットを使用して、エンタープライズ VoIP の音声ポリシーとダイヤル プランを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e5d92-108">The following cmdlets can be used to manage voice policies and dial plans for Enterprise Voice.</span></span>

<span data-ttu-id="e5d92-109">**音声ポリシー**</span><span class="sxs-lookup"><span data-stu-id="e5d92-109">**Voice Policy**</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-110">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-110">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-111">[Get-csdialplan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-111">[Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-112">[Get-csdialplan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-112">[New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-113">[Get-csdialplan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-113">[Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-114">[Get-csdialplan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-114">[Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-115">[Get-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-115">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5d92-116">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-116">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-117">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-117">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e5d92-118">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-118">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-119">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-119">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-120">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-120">[New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-121">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-121">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-122">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-122">[Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e5d92-123">[Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e5d92-123">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5d92-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5d92-124">See Also</span></span>


[<span data-ttu-id="e5d92-125">Lync Server 2013 のエンタープライズ Voip のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e5d92-125">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="e5d92-126">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="e5d92-126">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

