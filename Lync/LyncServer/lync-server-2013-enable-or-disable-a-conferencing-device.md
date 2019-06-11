---
title: 'Lync Server 2013: 会議デバイスを有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 435c119e81923ec19e4f8a1e0d3fc35180b8508a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Lync Server 2013 で会議デバイスを有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-20_

お使いの会議デバイスを有効または無効にするには、 **Csroom room**コマンドレットと**csroom room**コマンドレットを使用します。 これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>会議デバイスを有効にする

  - 会議デバイスを有効にするには、 **Csroom room**コマンドレットを使用します。 会議デバイスを有効にする場合は、会議デバイス id、b) 会議室のアカウントが所属するレジストラープール、およびそのアカウントに割り当てられる SIP アドレスを含める必要があります。
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>会議デバイスの無効化

  - 会議デバイスを無効にするには、 **Csroom room**コマンドレットを使用します。 無効にする会議デバイスの id を指定していることを確認してください。
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

詳細については、「 [Csroom room room](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) !」コマンドレットと「 [csroom room room](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom)コマンドレットを無効にする」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

