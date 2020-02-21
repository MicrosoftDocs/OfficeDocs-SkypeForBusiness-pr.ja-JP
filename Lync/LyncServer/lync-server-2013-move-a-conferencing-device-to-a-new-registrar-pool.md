---
title: 'Lync Server 2013: 会議デバイスを新しいレジストラープールに移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79ac6a28c475c8ec08584788fdb868d2ce30e143
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a>Lync Server 2013 で会議デバイスを新しいレジストラープールに移動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

会議デバイスを1つのレジストラープールから別のレジストラープールに移動するには、「 **move-Csroom room**コマンドレット」を使用します。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a>会議デバイスを新しいレジストラープールに移動する

  - 会議デバイスを移動するには、移動する会議室の id を指定し、ターゲットパラメーターを、デバイスの移動先となるレジストラープールの完全修飾ドメイン名 (FQDN) に設定する必要があります。 次に例を示します。
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

詳細については、「 [Move-Csroom room](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) 」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

