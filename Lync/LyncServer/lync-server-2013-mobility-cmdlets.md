---
title: 'Lync Server 2013: モビリティーコマンドレット'
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
ms.openlocfilehash: c2e1f5339f2c47a611fa29d9511d4d73148afcda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-cmdlets-in-lync-server-2013"></a><span data-ttu-id="0ab0b-102">Lync Server 2013 のモバイルコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0ab0b-102">Mobility cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab0b-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="0ab0b-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="0ab0b-104">モバイルコマンドレットは、Lync Server 2010 の累積的な更新で追加されたモバイル機能を管理するために導入されました。2011年11月。</span><span class="sxs-lookup"><span data-stu-id="0ab0b-104">Mobility cmdlets were introduced to manage the mobility feature added in cumulative update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="0ab0b-105">これらのコマンドレットを使用して、モビリティーサービス構成やユーザーポリシーなどのモビリティ機能の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="0ab0b-105">Use these cmdlets to manage settings for mobility features, such as Mobility Service configuration and user policies.</span></span>

<div>

## <a name="mobility-cmdlets"></a><span data-ttu-id="0ab0b-106">モバイルコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0ab0b-106">Mobility Cmdlets</span></span>

<span data-ttu-id="0ab0b-107">モバイル機能を構成するコマンドレットを使用すると、Lync Server 管理シェルからコマンドを実行したり、さまざまなモバイル設定を構成およびテストするスクリプトを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ab0b-107">The cmdlets that configure mobility features allow you to run commands from the Lync Server Management Shell or to write scripts to configure and test various mobility settings.</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-108">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-108">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-109">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-109">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-110">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-110">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-111">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-111">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-112">[新しい-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-112">[New-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ab0b-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-114">[新しい-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-114">[New-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-115">[CsMcxConfiguration の削除](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-115">[Remove-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-116">[Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-116">[Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ab0b-117">[Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-117">[Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-118">[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-118">[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-119">[New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-119">[New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-120">[Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-120">[Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-121">[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-121">[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ab0b-122">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-122">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-123">[新しい-Cspの通知構成](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-123">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-124">[削除-Cspの通知構成](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-124">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-125">[Set-Cspの通知構成](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-125">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ab0b-126">[Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-126">[Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-127">[テスト-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-127">[Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ab0b-128">[テスト-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ab0b-128">[Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ab0b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ab0b-129">See Also</span></span>


[<span data-ttu-id="0ab0b-130">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="0ab0b-130">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

