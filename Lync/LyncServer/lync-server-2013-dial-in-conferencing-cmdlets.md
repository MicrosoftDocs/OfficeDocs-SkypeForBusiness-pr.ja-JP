---
title: 'Lync Server 2013: ダイヤルイン会議のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing cmdlets
ms:assetid: 0718f82a-91c4-466f-8443-a85002deaa48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415630(v=OCS.15)
ms:contentKeyID: 48183320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e39081eef29da8d33b693bd4e319564c7be9a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="1a4f7-102">Lync Server 2013 でのダイヤルイン会議のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="1a4f7-102">Dial-in conferencing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a4f7-103">_**最終更新日:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="1a4f7-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="1a4f7-104">ダイヤルイン会議を使うと、ユーザーは "標準" 電話 (公衆交換電話網のデバイス) を使って、会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-104">Dial-in conferencing provides a way for users to use a "regular" telephone (that is, a device on the public switched telephone network) to join the audio portion of a conference.</span></span>

<div>

## <a name="dial-in-conferencing-cmdlets"></a><span data-ttu-id="1a4f7-105">ダイヤルイン会議のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="1a4f7-105">Dial-In Conferencing Cmdlets</span></span>

<span data-ttu-id="1a4f7-106">ダイヤルイン会議を許可したくない場合は、Set-csconferencingpolicy コマンドレットを使用し、Enabledial In会議プロパティを False に設定することで、この機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-106">If you do not want to allow dial-in conferencing you can disable this capability by using the Set-CsConferencingPolicy cmdlet and setting the EnableDialInConferencing property to False.</span></span> <span data-ttu-id="1a4f7-107">既定では、すべてのユーザーは、ダイヤルイン会議を含む会議を主催することができます。</span><span class="sxs-lookup"><span data-stu-id="1a4f7-107">By default, all users are allowed to host meetings that include dial-in conferencing.</span></span>

<span data-ttu-id="1a4f7-108">**ダイヤルイン会議**</span><span class="sxs-lookup"><span data-stu-id="1a4f7-108">**Dial-In Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-109">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-109">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-110">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-110">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-111">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-111">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-112">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-112">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1a4f7-113">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-113">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1a4f7-114">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-114">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-115">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-115">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-116">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-116">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-117">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-117">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1a4f7-118">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-118">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-119">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-119">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-120">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-120">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-121">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-121">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1a4f7-122">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-122">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-123">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-123">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-124">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-124">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1a4f7-125">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-125">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1a4f7-126">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1a4f7-126">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a4f7-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a4f7-127">See Also</span></span>


[<span data-ttu-id="1a4f7-128">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="1a4f7-128">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

