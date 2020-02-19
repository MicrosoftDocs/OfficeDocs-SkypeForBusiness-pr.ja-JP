---
title: 'Lync Server 2013: PSTN 接続のコマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity cmdlets
ms:assetid: b19ba43c-3987-410d-a704-aba0a4fb0498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415670(v=OCS.15)
ms:contentKeyID: 48185142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e9f07d1233aee5605645b2f849e377c8bc40ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-cmdlets-in-lync-server-2013"></a>Lync Server 2013 の PSTN 接続のコマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

エンタープライズ VoIP を使用すると、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との間で通話できる設定が可能になります。 これらの設定は、Lync Server 管理シェルで使用可能なコマンドレットを使用して構成できます。

<div>

## <a name="pstn-connectivity-cmdlets"></a>PSTN 接続のコマンドレット

PSTN 接続のさまざまな面を構成するには、次のコマンドレットを使用します。

**[Lync Server 2013 の PSTN ゲートウェイのコマンドレット](lync-server-2013-pstn-gateways-cmdlets.md)**

  - <span></span>  
    [Set-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [テスト-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [テスト-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

**[Lync Server 2013 の静的ルーティングのコマンドレット](lync-server-2013-static-routing-cmdlets.md)**

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

**[Lync Server 2013 でのトランク構成のコマンドレット](lync-server-2013-trunking-configuration-cmdlets.md)**

  - [Test-csintertrunkrouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - <span></span>  
    [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - <span></span>  
    [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - <span></span>  
    [New-csoutboundtranslationrule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [取得-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - <span></span>  
    [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - <span></span>  
    [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - <span></span>  
    [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

**[Lync Server 2013 での音声ルーティングのコマンドレット](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [-CsRoutingConfiguration の取得](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - <span></span>  
    [新しい-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - <span></span>  
    [-CsRoutingConfiguration の削除](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - <span></span>  
    [-CsRoutingConfiguration の設定](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

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

