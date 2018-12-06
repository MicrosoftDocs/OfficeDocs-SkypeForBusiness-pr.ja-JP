---
title: 'Lync Server 2013: DNS の概要 - 単一ディレクター'
TOCTitle: DNS の概要 - 単一ディレクター
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48272600
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS の概要 - Lync Server 2013 の単一ディレクター

 

_**トピックの最終更新日:** 2015-03-09_

次の表では、単一の ディレクターをサポートするために必要な DNS レコードをまとめて示します。 ディレクターの役割には、 フロント エンド サーバーと同様の DNS レコードが必要です。必要なレコードの数は、 ディレクター証明書で必要なサブジェクトの別名に反映されます。 フロント エンド サーバーとは異なり、 ディレクターではユーザー アカウントまたは Mobility Service はホストされません。

### ディレクターで必要な DNS レコード

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN/DNS レコード</th>
<th>IP アドレス/FQDN</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>ディレクター</p></td>
<td><p>レプリケーションおよびサーバー間に使用される ディレクター ホスト レコード</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>ディレクター</p></td>
<td><p>エッジ サーバーの内部エッジ インターフェイスからの受信セッション開始プロトコル (SIP)</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>ディレクター</p></td>
<td><p>リバース プロキシからの公開済みダイヤルイン Web サービス</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>ディレクター</p></td>
<td><p>リバース プロキシからの公開済みミーティング Web サービス</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>ディレクター</p></td>
<td><p>ディレクターに対するリバース プロキシ Web チケット外部 Web サービスによって公開および定義</p></td>
</tr>
</tbody>
</table>

