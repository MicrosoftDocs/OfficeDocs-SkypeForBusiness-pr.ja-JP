---
title: 'Lync Server 2013: ダイヤルイン会議のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing cmdlets
ms:assetid: 0718f82a-91c4-466f-8443-a85002deaa48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415630(v=OCS.15)
ms:contentKeyID: 48183320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63b24ad9b6203f3b73033e1c4f80dc8252d0f67
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514544"
---
# <a name="dial-in-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="46e02-102">Lync Server 2013 でのダイヤルイン会議のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="46e02-102">Dial-in conferencing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46e02-103">_**トピックの最終更新日:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="46e02-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="46e02-104">ダイヤルイン会議は、電話会議の音声部分に参加するために、ユーザーが "通常の" 電話 (公衆交換電話網上のデバイス) を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="46e02-104">Dial-in conferencing provides a way for users to use a "regular" telephone (that is, a device on the public switched telephone network) to join the audio portion of a conference.</span></span>

<div>

## <a name="dial-in-conferencing-cmdlets"></a><span data-ttu-id="46e02-105">Dial-In Conferencing Cmdlets</span><span class="sxs-lookup"><span data-stu-id="46e02-105">Dial-In Conferencing Cmdlets</span></span>

<span data-ttu-id="46e02-106">ダイヤルイン会議を許可しない場合は、Set-CsConferencingPolicy コマンドレットを使用し、Enabledial Inコンファレンスプロパティを False に設定することによって、この機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="46e02-106">If you do not want to allow dial-in conferencing you can disable this capability by using the Set-CsConferencingPolicy cmdlet and setting the EnableDialInConferencing property to False.</span></span> <span data-ttu-id="46e02-107">既定では、すべてのユーザーは、ダイヤルイン会議を含む会議をホストすることを許可されています。</span><span class="sxs-lookup"><span data-stu-id="46e02-107">By default, all users are allowed to host meetings that include dial-in conferencing.</span></span>

<span data-ttu-id="46e02-108">**ダイヤルイン会議**</span><span class="sxs-lookup"><span data-stu-id="46e02-108">**Dial-In Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-109">[Get-csconferencedirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-109">[Get-CsConferenceDirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-110">[Get-csconferencedirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-110">[Move-CsConferenceDirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-111">[Get-csconferencedirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-111">[New-CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-112">[Get-csconferencedirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-112">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="46e02-113">[テスト-Csダイヤルイン会議](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-113">[Test-CsDialInConferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="46e02-114">[Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-114">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-115">[Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-115">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-116">[Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-116">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-117">[Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-117">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="46e02-118">[Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-118">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-119">[Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-119">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-120">[Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-120">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-121">[Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-121">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="46e02-122">[Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-122">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-123">[Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-123">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-124">[Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-124">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="46e02-125">[Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-125">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="46e02-126">[Get-csdialinconferencinglanguagelist](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46e02-126">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46e02-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="46e02-127">See Also</span></span>


[<span data-ttu-id="46e02-128">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="46e02-128">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

