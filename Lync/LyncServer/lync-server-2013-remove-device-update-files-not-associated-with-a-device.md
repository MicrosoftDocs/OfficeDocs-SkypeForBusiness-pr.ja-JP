---
title: 'Lync Server 2013: デバイスに関連付けられていないデバイス更新ファイルを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea26cd20826ed099e27c7287c53cc7ca79bef9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Lync Server 2013 でデバイスに関連付けられていないデバイス更新ファイルを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-20_

新しいデバイス更新プログラムがシステムにアップロードされるたびに、対応するデバイス更新ルールが作成されます。 既定では、これらの新しいデバイス更新ルールは保留状態に割り当てられます。 つまり、テストデバイスにはルールをダウンロードしてインストールすることができますが、ユーザーが更新プログラムを使用できるようになる前にテストをテストすることができます。 テストに基づいて、更新プログラムを承諾して展開するか、または元に戻して削除します。 更新プログラムを拒否すると、デバイス更新プログラムのデバイス更新ルールとの関連付けが解除されます。

<div>


デバイスに関連付けられていないデバイス更新ファイルは、Windows PowerShell と**空の Deviceupdatefile**コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。



</div>

<div>


  - たとえば、次のコマンドを実行すると、デバイスに関連付けられていない Web サーバー atl-cs-001.litwareinc.com 上のデバイス更新ルールがすべて削除されます。
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

詳細については、「 [CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile)コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

