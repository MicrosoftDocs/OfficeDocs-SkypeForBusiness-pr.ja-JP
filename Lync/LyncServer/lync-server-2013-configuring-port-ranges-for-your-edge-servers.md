---
title: エッジ サーバー のポート範囲の構成
TOCTitle: エッジ サーバー のポート範囲の構成
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48272422
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# エッジ サーバー のポート範囲の構成

 

_**トピックの最終更新日:** 2015-07-24_

エッジ サーバーでは、音声、ビデオ、およびアプリケーション共有に別々のポート範囲を構成する必要はありません。同様に、エッジ サーバーで使用されるポート範囲は、会議サーバー、アプリケーション サーバー、および仲介サーバーで使用されるポート範囲と一致している必要はありません。しかし、管理を容易にするために、エッジ サーバーのポート範囲を他のサーバーのポート範囲と一致するように変更できます。たとえば、会議サーバー、アプリケーション サーバー、および仲介サーバーが以下のポート範囲を使用するように構成されているとします。


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
<td><p>音声</p></td>
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


上に示したように、音声、ビデオ、およびアプリケーション共有のポート範囲はポート 40803 から始まり、合計 24732 個のポートにわたっています。必要に応じて、Lync Server 管理シェルから次のようなコマンドを実行すると、指定したエッジ サーバーがこれらのポート範囲全体を使用するように構成できます。

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

または、次のコマンドを使用して、組織内のすべてのエッジ サーバーを同時に構成することもできます。

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

エッジ サーバーの現在のポートの設定は、次の Lync Server 管理シェル コマンドを使用して確認できます。

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

