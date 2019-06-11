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

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Lync Server 2013 の IM とプレゼンスのコマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-26_

インスタントメッセージング (IM) とプレゼンスコマンドレットを使用すると、Windows PowerShell を介してそれらのクライアント機能を管理することができます。 グローバル、サイト、またはユーザーごとのスコープでユーザーに適用されるプレゼンスポリシーを設定できます。 また、プライバシーと IM のさまざまな機能を構成することもできます。

<div>

## <a name="im-and-presence-cmdlets"></a>IM とプレゼンスコマンドレット

IM とプレゼンスを構成するには、次のコマンドレットを使用します。

  - <span></span>  
    [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))

  - <span></span>  
    [Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))

  - <span></span>  
    [New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))

  - <span></span>  
    [Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))

  - <span></span>  
    [Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))

  - [新しい-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))

  - [削除-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))

  - <span></span>  
    [新規-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))

  - <span></span>  
    [Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))

  - <span></span>  
    [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Csuserサービスの構成を取得する](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))

  - <span></span>  
    [新しい Csuserサービス構成](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))

  - <span></span>  
    [Csuserサービス構成の削除](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))

  - <span></span>  
    [設定-Csuserサービス構成](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsFileTransferFilterConfiguration の取得](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))

  - <span></span>  
    [新しい-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))

  - <span></span>  
    [CsFileTransferFilterConfiguration の削除](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))

  - <span></span>  
    [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))

  - <span></span>  
    [新しい-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))

  - <span></span>  
    [削除-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))

  - <span></span>  
    [Set-Cシム Filterconfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のクライアント管理コマンドレット](lync-server-2013-client-management-cmdlets.md)  


[Lync Server PowerShell ブログ](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

