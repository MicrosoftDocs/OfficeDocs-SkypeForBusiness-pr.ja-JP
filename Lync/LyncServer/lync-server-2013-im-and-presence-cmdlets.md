---
title: 'Lync Server 2013: IM およびプレゼンスのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17a99610f003d3ca74d1dfb9d1df1ac048aed517
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526734"
---
# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Lync Server 2013 の IM およびプレゼンスのコマンドレット

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-26_

インスタントメッセージング (IM) とプレゼンスのコマンドレットを使用すると、Windows PowerShell を使用してこれらのクライアント機能を管理できます。 グローバル サイト、またはユーザーごとのスコープに適用されるプレゼンス ポリシーを設定できます。 また、さまざまなプライバシー機能と IM 機能を構成できます。

<div>

## <a name="im-and-presence-cmdlets"></a>IM およびプレゼンスのコマンドレット

IM とプレゼンスを構成するには、以下のコマンドレットを使用します。

  - <span></span>  
    [Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - <span></span>  
    [Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - <span></span>  
    [新しい-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - <span></span>  
    [Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - <span></span>  
    [Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [新しい-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - <span></span>  
    [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - <span></span>  
    [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - <span></span>  
    [Get-csprivacyconfiguration 戻し](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [設定-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-Csuserサービス構成を取得する](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - <span></span>  
    [新しい-Csuserサービスの構成](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - <span></span>  
    [-Csuserサービス構成を削除する](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - <span></span>  
    [-Csuserサービス構成の設定](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsFileTransferFilterConfiguration の取得](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - <span></span>  
    [新しい-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - <span></span>  
    [削除-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - <span></span>  
    [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-Cシム Filterconfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - <span></span>  
    [New-Cシム Filterconfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - <span></span>  
    [Remove-Cシム Filterconfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - <span></span>  
    [Set-Cシム Filterconfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [テスト-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [テスト-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [テスト-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csp2pav](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [テスト-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のクライアント管理のコマンドレット](lync-server-2013-client-management-cmdlets.md)  


[Lync Server PowerShell ブログ](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

