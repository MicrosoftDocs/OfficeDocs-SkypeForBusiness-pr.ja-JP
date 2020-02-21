---
title: 'Lync Server 2013: Web 会議のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing cmdlets
ms:assetid: dac4d934-1500-4799-be4d-82809d4e7eb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415675(v=OCS.15)
ms:contentKeyID: 48185556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a147174d0e38a2c200a546bfaf70936dd57d539
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="61b8d-102">Lync Server 2013 での Web 会議のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="61b8d-102">Web conferencing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61b8d-103">_**トピックの最終更新日:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="61b8d-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="61b8d-104">会議とオンライン会議は、Microsoft Lync Server 2013 の重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="61b8d-104">Conferencing and online meetings are important elements in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="61b8d-105">Get-csconferencingconfiguration および Get-csconferencingpolicy コマンドレットは、Windows PowerShell を使用して会議を管理するための主要な管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="61b8d-105">The CsConferencingConfiguration and CsConferencingPolicy cmdlets are the primary administrative tools for managing conferences by using Windows PowerShell.</span></span>

<div>

## <a name="web-conferencing-cmdlets"></a><span data-ttu-id="61b8d-106">Web Conferencing Cmdlets</span><span class="sxs-lookup"><span data-stu-id="61b8d-106">Web Conferencing Cmdlets</span></span>

<span data-ttu-id="61b8d-107">[新しい-csclientpolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))コマンドレットおよび[Set-csclientpolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))コマンドレットを使用すると、Lync Server 2013 を構成および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="61b8d-107">The [New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15)) and [Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) cmdlets provide additional ways to configure and manage Lync Server 2013.</span></span>

<span data-ttu-id="61b8d-108">**Web 会議**</span><span class="sxs-lookup"><span data-stu-id="61b8d-108">**Web Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-109">[Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-109">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-110">[Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-110">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-111">[Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-111">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="61b8d-112">[CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-112">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="61b8d-113">[Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-113">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-114">[Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-114">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-115">[Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-115">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-116">[Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-116">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="61b8d-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-118">[Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-118">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-119">[Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-119">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-120">[Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-120">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-121">[Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-121">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="61b8d-122">[-Cs会議構成の取得](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-122">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-123">[新しい-Cs会議の構成](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-123">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-124">[削除-Cs会議の構成](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-124">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-125">[設定-Cs会議構成](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-125">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="61b8d-126">[無効化-Csの会議室](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-126">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="61b8d-127">[Enable-Csの会議室](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-127">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="61b8d-128">[取得-Cs会議室](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-128">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="61b8d-129">[移行-Csの会議室](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-129">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="61b8d-130">[セットアップ-Csの会議室](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-130">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="61b8d-131">[テスト-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-131">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-132">[テスト-CsAVConference 会議](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-132">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-133">[Test-csdataconference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-133">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-134">[テスト-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-134">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-135">[Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-135">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="61b8d-136">[テスト-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="61b8d-136">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61b8d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="61b8d-137">See Also</span></span>


[<span data-ttu-id="61b8d-138">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="61b8d-138">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

