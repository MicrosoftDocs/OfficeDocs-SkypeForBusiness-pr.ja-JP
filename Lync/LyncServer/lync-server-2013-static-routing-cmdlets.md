---
title: 'Lync Server 2013: 静的ルーティングコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca2171e66c9441dc2f2f0ff2a8475e03becefd1a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a>Lync Server 2013 の静的ルーティングコマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-20_

静的ルートの場合、管理者は SIP メッセージによって取得されたネットワークルートを事前に決めることができます。 サーバーによってメッセージが受信されると、サーバーはメッセージアドレスを確認し、管理者によって構成されている次ホップサーバーにメッセージを転送します。 適切に構成されていれば、静的なルートは、迅速かつ正確にメッセージを配信し、サーバーに最小限の overheard を配置することに役立ちます。

<div>

## <a name="static-routing-cmdlets"></a>静的なルーティングコマンドレット

Microsoft サポート担当者から指示があった場合を除き、Microsoft Lync Server 2013 に対して構成されている静的ルートは、[新しい-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))コマンドレットを使って作成する必要があります。 ルートを作成した後は、CsStaticRoutingConfiguration コマンドレットを使って、そのルートを静的ルーティングコレクションに追加することができます。

**静的なルーティング**

  - <span></span>  
    [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))

  - <span></span>  
    [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新しい-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsStaticRoutingConfiguration の取得](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))

  - <span></span>  
    [新しい-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))

  - <span></span>  
    [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))

  - <span></span>  
    [設定-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

