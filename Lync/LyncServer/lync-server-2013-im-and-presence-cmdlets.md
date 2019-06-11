---
title: 'Lync Server 2013: IM とプレゼンスコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5047a8fbb4d9533e7364ca0d566c0a9ce9660fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="b754e-102">Lync Server 2013 の IM とプレゼンスのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b754e-102">IM and presence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b754e-103">_**最終更新日:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="b754e-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="b754e-104">インスタントメッセージング (IM) とプレゼンスコマンドレットを使用すると、Windows PowerShell を介してそれらのクライアント機能を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b754e-104">Instant Messaging (IM) and presence cmdlets allow you to manage those client features through Windows PowerShell.</span></span> <span data-ttu-id="b754e-105">グローバル、サイト、またはユーザーごとのスコープでユーザーに適用されるプレゼンスポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b754e-105">You can set presence policies that apply to users at the global, site, or per-user scope.</span></span> <span data-ttu-id="b754e-106">また、プライバシーと IM のさまざまな機能を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b754e-106">You can also configure various privacy and IM features.</span></span>

<div>

## <a name="im-and-presence-cmdlets"></a><span data-ttu-id="b754e-107">IM とプレゼンスコマンドレット</span><span class="sxs-lookup"><span data-stu-id="b754e-107">IM and Presence Cmdlets</span></span>

<span data-ttu-id="b754e-108">IM とプレゼンスを構成するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b754e-108">The configure IM and presence, use the following cmdlets:</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-109">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-109">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-110">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-110">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-111">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-111">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-112">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-112">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-113">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-113">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="b754e-114">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-114">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="b754e-115">[新しい-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-115">[New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="b754e-116">[削除-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-116">[Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="b754e-117">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-117">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-118">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-118">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-119">[新規-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-119">[New-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-120">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-120">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-121">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-121">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-122">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-122">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-123">[Csuserサービスの構成を取得する](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-123">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-124">[新しい Csuserサービス構成](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-124">[New-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-125">[Csuserサービス構成の削除](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-125">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-126">[設定-Csuserサービス構成](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-126">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-127">[CsFileTransferFilterConfiguration の取得](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-127">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-128">[新しい-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-128">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-129">[CsFileTransferFilterConfiguration の削除](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-129">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-130">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-130">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-131">[取得-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-131">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-132">[新しい-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-132">[New-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-133">[削除-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-133">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b754e-134">[Set-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-134">[Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-135">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-135">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-136">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-136">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-137">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-137">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-138">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-138">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b754e-139">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b754e-139">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b754e-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="b754e-140">See Also</span></span>


[<span data-ttu-id="b754e-141">Lync Server 2013 のクライアント管理コマンドレット</span><span class="sxs-lookup"><span data-stu-id="b754e-141">Client management cmdlets in Lync Server 2013</span></span>](lync-server-2013-client-management-cmdlets.md)  


[<span data-ttu-id="b754e-142">Lync Server PowerShell ブログ</span><span class="sxs-lookup"><span data-stu-id="b754e-142">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

