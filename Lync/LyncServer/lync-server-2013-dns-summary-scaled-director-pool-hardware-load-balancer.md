---
title: 'Lync Server 2013: DNS の概要 - 拡張ディレクター プール、ハードウェア ロード バランサー'
TOCTitle: DNS の概要 - 拡張ディレクター プール、ハードウェア ロード バランサー
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48271176
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー

 

_**トピックの最終更新日:** 2015-03-09_

以下の表に、ハードウェア負荷分散 ディレクターのサポートに必要な DNS レコードの概要を示します。ディレクターの役割には、フロント エンド サーバーと同様の DNS レコードが必要です。必要なレコードの数は、ディレクターの証明書で必要なサブジェクトの別名に反映されます。フロント エンド サーバーとは異なり、ディレクター プールはユーザー アカウントも Mobility Service もホストしません。

### ロード バランサー機器および DNS 負荷分散を使用する ディレクター プールで必要な DNS レコード

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
<td><p>レプリケーションおよびサーバー間通信のための ディレクター ホスト レコード</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>ディレクター プール プール HLB VIP</p></td>
<td><p>DNS 負荷分散 ディレクター プールのホスト レコード</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>ディレクター プール HLB VIP</p></td>
<td><p>エッジ サーバーの内部インターフェイスからの受信 SIP (セッション開始プロトコル)</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>ディレクター プール HLB VIP</p></td>
<td><p>リバース プロキシから、ハードウェア負荷分散される公開ダイヤルイン Web サービス</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>ディレクター プール HLB VIP</p></td>
<td><p>リバース プロキシから、ハードウェア負荷分散される公開ミーティング Web サービス</p></td>
</tr>
<tr class="even">
<td><p>内部 DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>ディレクター プール HLB VIP</p></td>
<td><p>ハードウェア負荷分散が行われ、リバース プロキシによって公開および定義された、ディレクター プールの Web チケット外部 Web サービス</p></td>
</tr>
</tbody>
</table>

