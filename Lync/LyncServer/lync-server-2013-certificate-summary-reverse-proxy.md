---
title: 'Lync Server 2013: 証明書の概要 - リバース プロキシ'
TOCTitle: 証明書の概要 - リバース プロキシ
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48273971
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 証明書の概要 - Lync Server 2013 リバース プロキシ

 

_**トピックの最終更新日:** 2015-03-09_

リバース プロキシの証明書要件は、 エッジ サーバーの証明書要件よりずっと簡単です。提供されているフローチャートは必要な要件を示します。添付の表は、 エッジ サーバーのディスカッションの中で見てきたシナリオに関連する代表的な証明書のサブジェクト名およびサブジェクトの別名を示しています。 エッジ サーバーのシナリオの詳細については、「[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。

**リバース プロキシの証明書のフロー チャート**

![エッジ サーバー用の証明書のフロー チャート](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "エッジ サーバー用の証明書のフロー チャート")

### リバース プロキシ: 外部インターフェイス

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
<th>サブジェクト名</th>
<th>サブジェクトの別名 (SAN)/順序</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>リバース プロキシ</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(オプション): *.contoso.com</p></td>
<td><p>証明書は公的 CA によって発行され、サーバー EKU を含んでいる必要があります。サービスには、アドレス帳サービス、会議向けの配布グループ拡張 Office Web Apps、および Lync IP デバイス公開ルールが含まれます。サブジェクトの別名には、次のものがあります。</p>
<ul>
<li><p>フロント エンド サーバーまたは フロント エンド プールの外部 Web サービス FQDN</p></li>
<li><p>ディレクターまたはディレクター プールの外部 Web サービス FQDN</p></li>
<li><p>ダイヤルイン会議</p></li>
<li><p>オンライン会議の公開ルール</p></li>
<li><p>会議用の Office Web Apps</p></li>
<li><p>Lyncdiscover (自動検出)</p></li>
</ul>
<p>オプションのワイルドカードは meet と dialin SAN の両方を置き換えます</p></td>
</tr>
</tbody>
</table>

