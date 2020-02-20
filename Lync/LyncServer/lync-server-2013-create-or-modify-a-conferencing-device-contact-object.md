---
title: 'Lync Server 2013: 会議デバイスの連絡先オブジェクトを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65f2e1c76815a1c495ed2014b363ae88eed1e301
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Lync Server 2013 で会議デバイスの連絡先オブジェクトを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-02_

会議室オブジェクトを作成するには、まず、デバイスを表す Active Directory ユーザーアカウントを作成します。 その後、この**コマンドレットを使用して**、そのアカウントを会議デバイスとして機能できるようにします。 既存の会議デバイスのプロパティを変更する必要がある場合は、コマンドレットの**設定**を使用します。

これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>会議デバイスの作成

  - 新しい会議デバイスを表す Active Directory ユーザーアカウントを作成した後、 **enable-csコンファレンスルーム**コマンドレットを使用して有効にします。 会議デバイス id、b) 会議室のアカウントが所属するレジストラープール、およびそのアカウントに割り当てる SIP アドレスは、必ず含めるようにしてください。 次に例を示します。
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>会議デバイスの変更

  - 既存の会議デバイスのプロパティ値を変更するには、コマンドレットの**設定**を使用します。 たとえば、次のコマンドを実行すると、会議デバイスに関連付けられた電話番号 (LineUri) が更新されます。
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

詳細については、を参照してください。[このコマンドレット](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom)[のヘルプ](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom)トピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

