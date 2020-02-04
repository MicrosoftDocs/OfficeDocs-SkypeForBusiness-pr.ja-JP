---
title: 'Lync Server 2013: 通話受付制御コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control cmdlets
ms:assetid: dd9d3912-b562-4839-a337-bfc5277cfb62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415676(v=OCS.15)
ms:contentKeyID: 48185602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3805a597cba993e8b50e006a198fdc693a1d595b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a>Lync Server 2013 での通話受付制御コマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-03-21_

通話受付制御 (CAC) では、許容可能な品質の音声またはビデオセッションを確立するために十分なネットワーク帯域幅があるかどうかを判別します。 CAC を管理するには、ネットワーク、サイト、サブネットの制限と設定を構成します。

<div>

## <a name="call-admission-control-cmdlets"></a>通話受付制御コマンドレット

Lync Server 管理シェルから CAC を管理するには、次のコマンドレットを使用します。

**通話受付管理**

  - <span></span>  
    [Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))

  - <span></span>  
    [新規-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))

  - <span></span>  
    [Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))

  - <span></span>  
    [Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))

  - <span></span>  
    [新規-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新しい-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新しい-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))

  - <span></span>  
    [Remove-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))

  - <span></span>  
    [Set-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))

  - <span></span>  
    [新しい (CsNetworkInterRegionRoute)](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))

  - <span></span>  
    [CsNetworkInterRegionRoute の削除](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))

  - <span></span>  
    [設定-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))

  - <span></span>  
    [新規-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))

  - <span></span>  
    [新しい CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))

  - <span></span>  
    [CsNetworkRegion の削除](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))

  - <span></span>  
    [新しい-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))

  - <span></span>  
    [CsNetworkRegionLink を削除する](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))

  - <span></span>  
    [新しい-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))

  - <span></span>  
    [CsNetworkSite の削除](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))

  - <span></span>  
    [新しい-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))

  - <span></span>  
    [CsNetworkSubnet の削除](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の通話受付制御の概要](lync-server-2013-overview-of-call-admission-control.md)  


[Lync Server PowerShell ブログ](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

