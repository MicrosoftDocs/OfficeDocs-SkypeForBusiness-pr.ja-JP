---
title: 'Lync Server 2013: DNS の概要 - DNS と HLB 負荷分散'
TOCTitle: DNS の概要 - DNS と HLB 負荷分散
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48273716
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS の概要 - Lync Server 2013 での DNS と HLB 負荷分散

 

_**トピックの最終更新日:** 2015-03-09_

次の表に、DNS 負荷分散およびハードウェア負荷分散される ディレクターをサポートするために必要な DNS レコードの概要を示します。 ディレクターの役割には、 フロント エンド サーバーと同様の DNS レコードが必要です。必要なレコードの個数は、 ディレクター証明書で必要なサブジェクト代替名に反映されます。 フロント エンド サーバーと異なり、 ディレクター プールはユーザー アカウントまたは Mobility Service をホストしません。

### DNS 負荷分散およびハードウェア ロード バランサーを使用するディレクター プールに必要な DNS レコード

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
<td><p>dirpool01.contoso.net</p></td>
<td><p>ディレクター プール</p></td>
<td><p>サーバー間の、DNS 負荷分散される ディレクター プール用のホスト ホストレコード</p></td>
</tr>
<tr class="odd">
<td><p>内部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>ディレクター プール</p></td>
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
<td><p>ハードウェア負荷分散され公開され、リバース プロキシによって定義された、ディレクター プールの Web チケット外部 Web サービス</p></td>
</tr>
</tbody>
</table>

