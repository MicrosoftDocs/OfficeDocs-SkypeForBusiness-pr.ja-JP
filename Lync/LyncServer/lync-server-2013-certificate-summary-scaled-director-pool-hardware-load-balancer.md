---
title: 'Lync Server 2013: 証明書の概要 - 拡張ディレクター プール、ハードウェア ロード バランサー'
TOCTitle: 証明書の概要 - 拡張ディレクター プール、ハードウェア ロード バランサー
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48271955
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 証明書の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー

 

_**トピックの最終更新日:** 2015-03-09_

ロード バランサー機器のある ディレクターに対する証明書要件では、ディレクター プールが受信できるサービスのサブジェクト名とサブジェクトの別名を持つ既定の証明書が使用されます。プール内の ディレクターごとに 1 つの証明書が要求されます。また、サーバー間認証用の OAuth トークンの証明書も各サーバーにインストールされています。

### ロード バランサー機器を使用する拡張ディレクター用の証明書

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
<p>ディレクターは、境界にあるリバース プロキシからの要求または エッジ サーバーからの要求に応答します。</p>
<p>または、簡易 URL のワイルドカード エントリ</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>エントリなし</p></td>
<td><div>

> [!IMPORTANT]
> 最小のキー長は 1024 ビットですが、最小の推奨キー長は 2048 ビットであるという警告が表示される場合があります。


</div>
<p>OAuthTokenIssuer 証明書は、大規模環境内のサーバーを認証するための専用の証明書で、内部 CA またはパブリック CA から要求できます。この証明書は必須です。</p></td>
</tr>
</tbody>
</table>

