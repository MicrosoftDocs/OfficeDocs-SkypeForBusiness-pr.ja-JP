---
title: 'Lync Server 2013: 証明書の概要 - DNS および HLB による負荷分散'
TOCTitle: 証明書の概要 - DNS および HLB による負荷分散
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48272734
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 証明書の概要 - Lync Server 2013 の DNS および HLB による負荷分散

 

_**トピックの最終更新日:** 2015-03-09_

DNS 負荷分散およびハードウェア ロード バランサーを使用する ディレクターの証明書要件は、ディレクターが受信できるサービスのサブジェクト名およびサブジェクトの別名を含む既定の証明書を使用することです。プール内の ディレクターごとに証明書が要求されます。ハードウェア ロード バランサーはリバース プロキシからのトラフィックだけを負荷分散することを理解しておくことが重要です。さらに、サーバー間認証のために各サーバーにインストールされる OAuth トークンがあります。

### ディレクターの証明書

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名 (SN)</th>
<th>サブジェクトの別名 (SAN)</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既定</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(オプション) *.contoso.com</p></td>
<td><p>ディレクターの証明書は、内部管理の証明機関 (CA) またはパブリック CA のどちらかから要求できます。</p>
<p>ディレクターは、境界内のリバース プロキシまたは エッジ サーバーからの要求に応答します。内部クライアントは ディレクターを使用しません。</p>
<p>または、簡易 URL のワイルドカード エントリ</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>エントリなし</p></td>
<td>

> [!IMPORTANT]
> 最小のキー長は 1024 ビットですが、最小の推奨キー長は 2048 ビットであるという警告が表示される場合があります。


<p>OAuthTokenIssuer 証明書は、大規模環境内のサーバーを認証するための専用の証明書で、内部 CA またはパブリック CA から要求できます。この証明書は必須です。</p></td>
</tr>
</tbody>
</table>

