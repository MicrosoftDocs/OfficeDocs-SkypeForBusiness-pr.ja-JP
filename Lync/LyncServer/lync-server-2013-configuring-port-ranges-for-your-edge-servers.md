---
title: 'Lync Server 2013: エッジサーバーのポート範囲の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b526611e2e29f1b8d11e731381898a7db5e71aa8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Lync Server 2013 でのエッジサーバーのポート範囲の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-07-24_

エッジサーバーでは、オーディオ、ビデオ、およびアプリケーション共有に対して個別のポート範囲を構成する必要はありません。同様に、エッジサーバーで使用されるポート範囲は、会議、アプリケーション、および仲介サーバーで使用されるポート範囲と一致している必要はありません。 この例を進める前に、このオプションが存在している間は、ポート範囲を変更しないことをお勧めします。これは、5万のポート範囲から移動すると、一部のシナリオに悪影響を及ぼす可能性があるためです。

たとえば、次のポート範囲を使用するように会議、アプリケーション、および仲介サーバーを構成したとします。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>パケットの種類</th>
<th>開始ポート</th>
<th>予約されたポートの数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アプリケーション共有</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>オーディオ</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>ビデオ</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>合計</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


ご覧のとおり、オーディオ、ビデオ、およびアプリケーション共有のポート範囲は、ポート40803で開始し、合計24732ポートを含んでいます。 必要に応じて、Lync Server 管理シェルから次のようなコマンドを実行すると、指定したエッジ サーバーがこれらのポート範囲全体を使用するように構成できます。

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

または、次のコマンドを使用して、組織内のすべてのエッジ サーバーを同時に構成することもできます。

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

この Lync Server 管理シェルコマンドを使用して、エッジサーバーの現在のポート設定を確認できます。

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

これらのオプションを提供していますが、ポート構成用のものを残しておくことを強くお勧めします。

</div>

<span> </span>

</div>

</div>

</div>

