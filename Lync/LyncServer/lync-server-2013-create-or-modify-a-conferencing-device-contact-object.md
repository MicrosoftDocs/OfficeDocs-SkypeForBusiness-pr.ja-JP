---
title: 'Lync Server 2013: 会議デバイスの連絡先オブジェクトを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b468b2338d115e7b646c28fd4d0b310b6e132d79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Lync Server 2013 で会議デバイスの連絡先オブジェクトを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-02_

会議室オブジェクトを作成するには、まず、デバイスを表す Active Directory ユーザーアカウントを作成します。 次に、 **Csroom room**コマンドレットを使用して、そのアカウントを会議デバイスとして機能させることができるようにします。 既存の会議デバイスのプロパティを変更する必要がある場合は、 **Set-Csroom room**コマンドレットを使用します。

これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>会議デバイスの作成

  - 新しい会議デバイスを表す Active Directory ユーザーアカウントを作成した後、[**有効にする-Csroom room** ] コマンドレットを使用して有効にします。 会議デバイス id、b) 会議室アカウントが所属するレジストラープール、およびそのアカウントに割り当てられる SIP アドレスを必ず含めてください。)。 次に例を示します。
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>会議デバイスの変更

  - 既存の会議デバイスのプロパティ値を変更するには、 **Set-Csroom room**コマンドレットを使用します。 たとえば、次のコマンドは、会議デバイスに関連付けられている電話番号 (LineUri) を更新します。
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

詳細については、「 [Csroom Room を有効にする](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom)」コマンドレットと、「 [csroom room](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) 」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

