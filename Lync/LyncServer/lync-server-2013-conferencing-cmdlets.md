---
title: 'Lync Server 2013: 会議コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a95cf0c07726670b15891b2a067346e3452f333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="23666-102">Lync Server 2013 での会議コマンドレット</span><span class="sxs-lookup"><span data-stu-id="23666-102">Conferencing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23666-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="23666-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="23666-104">Microsoft Lync Server 2013 を使用すると、ユーザーは、Lync 2013 などの会議アプリケーションまたは電話でダイヤルインすることにより、2つの異なる方法で会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="23666-104">Microsoft Lync Server 2013 enables users to join conferences in two different ways: by using a conferencing application such as Lync 2013, or by dialing in using a telephone.</span></span> <span data-ttu-id="23666-105">ダイヤルインユーザーは、スライドの表示やインスタントメッセージなどの操作を行うことはできませんが、会議の音声部分に完全に参加することはできます。</span><span class="sxs-lookup"><span data-stu-id="23666-105">Dial-in users are not be able to do such things as view slides or exchange instant messages, but they are able to fully participate in the audio portion of a conference.</span></span>

<div>

## <a name="conferencing-cmdlets"></a><span data-ttu-id="23666-106">会議コマンドレット</span><span class="sxs-lookup"><span data-stu-id="23666-106">Conferencing Cmdlets</span></span>

<span data-ttu-id="23666-107">**Csdial incall**コマンドレットは、ダイヤルイン会議のプロパティを構成するために使用されます。電話番号の指定は、ユーザーが会議に参加した後で電話会議に参加できるようにするために使います (たとえば、6を押すと、電話をミュートまたはミュート解除します)。</span><span class="sxs-lookup"><span data-stu-id="23666-107">The **CsDialInConferencing** cmdlets are used to configure dial-in conferencing properties, including everything from specifying the phone numbers users can call in order to join a conference to the keypad commands available to them after they join a conference (for example, pressing 6 to mute or unmute their phone).</span></span> <span data-ttu-id="23666-108">会議のその他の機能 (たとえば、ユーザーが会議を記録したり、会議中にユーザーを共有できる場合など) は、 **set-csconferencingpolicy**コマンドレットを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="23666-108">Most of the other features of a conference (for example, can users record the conference, can users share applications during the conference, and so on) are managed by using the **CsConferencingPolicy** cmdlets.</span></span>

<span data-ttu-id="23666-109">**[Lync Server 2013 でのダイヤルイン会議のコマンドレット](lync-server-2013-dial-in-conferencing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="23666-109">**[Dial-in conferencing cmdlets in Lync Server 2013](lync-server-2013-dial-in-conferencing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="23666-110">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-110">[Get-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-111">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-111">[Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-112">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-112">[New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-113">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-113">[Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-114">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-114">[Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-115">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-115">[Get-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-116">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-116">[New-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-117">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-117">[Remove-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-118">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-118">[Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-119">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-119">[Get-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-120">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-120">[New-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-121">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-121">[Remove-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-122">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-122">[Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-123">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-123">[Get-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-124">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-124">[New-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-125">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-125">[Remove-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-126">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-126">[Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-127">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-127">[Get-CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))</span></span>

<span data-ttu-id="23666-128">**[Lync Server 2013 の Web 会議コマンドレット](lync-server-2013-web-conferencing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="23666-128">**[Web conferencing cmdlets in Lync Server 2013](lync-server-2013-web-conferencing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="23666-129">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-129">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-130">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-130">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-131">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-131">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-132">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-132">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-133">[Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-133">[Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-134">[New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-134">[New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-135">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-135">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-136">[Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-136">[Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-137">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-137">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-138">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-138">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-139">[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-139">[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-140">[Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-140">[Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-141">[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-141">[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-142">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-142">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-143">[New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-143">[New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-144">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-144">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-145">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-145">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="23666-146">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-146">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="23666-147">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-147">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="23666-148">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-148">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="23666-149">[Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-149">[Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="23666-150">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-150">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="23666-151">[Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-151">[Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-152">[Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-152">[Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-153">[Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-153">[Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-154">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-154">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-155">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-155">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="23666-156">[Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="23666-156">[Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23666-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="23666-157">See Also</span></span>


[<span data-ttu-id="23666-158">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="23666-158">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

