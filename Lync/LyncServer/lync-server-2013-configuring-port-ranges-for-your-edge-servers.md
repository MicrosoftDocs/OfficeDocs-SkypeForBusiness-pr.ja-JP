---
title: 'Lync Server 2013: エッジサーバーのポート範囲の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73827b9c16903a6b3cf06f0c56446c0409fb9cd4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Lync Server 2013 でエッジサーバーのポート範囲を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-07-24_

エッジサーバーでは、音声、ビデオ、アプリケーション共有のために個別のポート範囲を構成する必要はありません。同様に、エッジサーバーに使われるポート範囲も、会議、アプリケーション、および仲介サーバーで使用されるポート範囲と一致する必要はありません。 例を始める前に、このオプションが存在している間、ポート範囲を変更しないことをお勧めします。これは、5万のポート範囲から移動した場合に、一部のシナリオに悪影響を与える可能性があるため、これを強調することが重要です。

たとえば、次のようなポート範囲を使用するように会議、アプリケーション、および仲介業者を構成したとします。


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
<th>予約されているポートの数</th>
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


ご覧のとおり、オーディオ、ビデオ、およびアプリケーション共有のポート範囲は、ポート40803から始まり、24732ポートの合計をカバーしています。 必要に応じて、次のようなポート値を使用するように特定のエッジサーバーを構成するには、Lync Server 管理シェルで、次のようなコマンドを実行します。

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

または、次のコマンドを使用して、組織内のすべてのエッジサーバーを同時に構成します。

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

次の Lync Server 管理シェルコマンドを使用して、エッジサーバーの現在のポート設定を確認できます。

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

ここでも、これらのオプションを用意していますが、ポート構成のためにそのままにしておくことを強くお勧めします。

</div>

<span> </span>

</div>

</div>

</div>

