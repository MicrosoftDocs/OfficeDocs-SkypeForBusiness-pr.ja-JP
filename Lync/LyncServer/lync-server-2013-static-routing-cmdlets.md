---
title: 'Lync Server 2013: 静的ルーティングのコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 630d9e6651836c44f961a35d2849558306416d69
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a>Lync Server 2013 の静的ルーティングのコマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-20_

管理者は静的ルートを使用して、SIP メッセージが経由するネットワーク ルートをあらかじめ設定できます。サーバーはメッセージを受信すると、そのメッセージのアドレスを確認し、管理者があらかじめ設定した次ホップ サーバーに転送します。正しく構成されている場合、静的ルートによって、メッセージを適切なタイミングで正確に配信でき、サーバーにかかるオーバーヘッドが最小限になります。

<div>

## <a name="static-routing-cmdlets"></a>静的ルーティングのコマンドレット

Microsoft サポート担当者から特に指示がない限り、Microsoft Lync Server 2013 用に構成された静的ルートは、[新しい-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))コマンドレットを使用して作成する必要があります。 ルートの作成後に、CsStaticRoutingConfiguration コマンドレットを使用して、ルートを静的ルーティング コレクションに追加できます。

**静的ルーティング**

  - <span></span>  
    [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - <span></span>  
    [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新しい-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsStaticRoutingConfiguration の取得](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - <span></span>  
    [新しい-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - <span></span>  
    [-CsStaticRoutingConfiguration の削除](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - <span></span>  
    [-CsStaticRoutingConfiguration の設定](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxycustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyrealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytcp](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytls](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyusedefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyusedefaultcert は](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csissuedcertid](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server PowerShell ブログ](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

