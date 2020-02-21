---
title: 'Lync Server 2013: デバイスに関連付けられていないデバイス更新ファイルを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1376e82ac29efbe2fcbf996445a75fc3bea1492d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Lync Server 2013 でデバイスに関連付けられていないデバイス更新ファイルを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

新しいデバイス更新プログラムがシステムにアップロードされるたびに、対応するデバイス更新ルールが作成されます。 既定では、これらの新しいデバイス更新ルールは保留状態に割り当てられます。 これは、これらのルールはテストデバイスでダウンロードおよびインストールできますが、運用デバイスではインストールできないため、更新プログラムをテストしてからユーザーが使用できるようにすることができます。 テストに基づいて、更新を承諾して、展開するか、または拒否して削除します。 更新を拒否すると、デバイスの更新はデバイス更新ルールから関連付けが解除されます。

<div>


デバイスに関連付けられていないデバイス更新ファイルは、Windows PowerShell と、 **CsDeviceUpdateFile**コマンドレットを使用して削除できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]  
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>


  - たとえば、次のコマンドを実行すると、デバイスに関連付けられていない、Web サーバー atl-cs-001.litwareinc.com 上のデバイス更新ルールがすべて削除されます。
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

詳細につい[ては、このコマンドレット](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile)のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

