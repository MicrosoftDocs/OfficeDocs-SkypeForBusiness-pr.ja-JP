---
title: 'Lync Server 2013: トランク構成コマンドレット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Trunking configuration cmdlets
ms:assetid: 2c36b03a-b80f-4321-a448-6ba26b9357f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416489(v=OCS.15)
ms:contentKeyID: 48183703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec65e877d480924f3fcc312b3972cc329ad4ed34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="trunking-configuration-cmdlets-in-lync-server-2013"></a>Lync Server 2013 のトランク構成コマンドレット

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-08_

トランク構成コマンドレットは、公衆交換電話網 (PSTN) ゲートウェイ、IP パブリックブランチエクスチェンジ (PBX)、またはサービスプロバイダのセッションボーダーコントローラー (SBC) などのトランクピアエンティティの設定を定義するために使用されます。 これらの設定では、このトランクでメディア バイパスが有効かどうか、特定の条件下でリアルタイム転送制御プロトコル (RTCP) パケットを送信するかどうか、セキュア リアルタイム プロトコル (SRTP) 暗号化を要求するかどうかなどを構成します。

<div>

## <a name="trunking-configuration-cmdlets"></a>トランク構成コマンドレット

トランク構成には、次のコマンドレットを使用します。

**トランク構成**

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))

  - [新規-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))

  - [Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))

  - <span></span>  
    [New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))

  - <span></span>  
    [Remove-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))

  - <span></span>  
    [Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-Set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))

  - <span></span>  
    [新規-Set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))

  - <span></span>  
    [Remove-Set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))

  - <span></span>  
    [テスト-Set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新規-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))

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

