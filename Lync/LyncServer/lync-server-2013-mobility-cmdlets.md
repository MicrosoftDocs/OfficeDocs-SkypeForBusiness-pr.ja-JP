---
title: 'Lync Server 2013: Mobility コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility cmdlets
ms:assetid: 42a30a34-d66b-4c91-b596-a6fc7666e600
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690019(v=OCS.15)
ms:contentKeyID: 48183973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88343e0e430f28e7661c18072bad799c46d84f3f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-cmdlets-in-lync-server-2013"></a><span data-ttu-id="32726-102">Lync Server 2013 でのモビリティのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="32726-102">Mobility cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32726-103">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="32726-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="32726-104">Mobility コマンドレットは、Lync Server 2010 の累積的な更新プログラム (11 月 2011) で追加されたモビリティ機能を管理するために導入されました。</span><span class="sxs-lookup"><span data-stu-id="32726-104">Mobility cmdlets were introduced to manage the mobility feature added in cumulative update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="32726-105">これらのコマンドレットを使用して、Mobility Service の構成、ユーザー ポリシーなどのモビリティ機能の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="32726-105">Use these cmdlets to manage settings for mobility features, such as Mobility Service configuration and user policies.</span></span>

<div>

## <a name="mobility-cmdlets"></a><span data-ttu-id="32726-106">モビリティ コマンドレット</span><span class="sxs-lookup"><span data-stu-id="32726-106">Mobility Cmdlets</span></span>

<span data-ttu-id="32726-107">モビリティ機能を構成するコマンドレットを使用すると、Lync Server 管理シェルからコマンドを実行したり、さまざまなモビリティ設定を構成およびテストするためのスクリプトを書き込んだりすることができます。</span><span class="sxs-lookup"><span data-stu-id="32726-107">The cmdlets that configure mobility features allow you to run commands from the Lync Server Management Shell or to write scripts to configure and test various mobility settings.</span></span>

  - <span></span>  
    <span data-ttu-id="32726-108">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-108">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-109">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-109">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-110">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-110">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-111">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-111">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-112">[新しい-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-112">[New-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="32726-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-114">[新しい-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-114">[New-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-115">[Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-115">[Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-116">[Set-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-116">[Set-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="32726-117">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-117">[Get-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-118">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-118">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-119">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-119">[New-CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-120">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-120">[Remove-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-121">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-121">[Set-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="32726-122">[Get-Cspの、構成](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-122">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-123">[新しい-Cspの、構成](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-123">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-124">[削除-Cspの "構成"](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-124">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-125">[Set-Cspの通知構成](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-125">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="32726-126">[テスト-CsMcxConference 会議](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-126">[Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-127">[Test-csmcxp2pim](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-127">[Test-CsMcxP2PIM](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="32726-128">[テスト-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="32726-128">[Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32726-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="32726-129">See Also</span></span>


[<span data-ttu-id="32726-130">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="32726-130">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

