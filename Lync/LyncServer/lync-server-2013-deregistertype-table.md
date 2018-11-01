---
title: 'Lync Server 2013: DeRegisterType テーブル'
TOCTitle: DeRegisterType テーブル
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48271187
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の DeRegisterType テーブル

 

_**トピックの最終更新日:** 2015-03-09_

DeRegisterType テーブルは、使用できるユーザー登録解除の種類 ("クライアント開始済み"、"登録期限切れ"、"クライアント停止済み" など) の一覧を格納する静的テーブルです。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>有効な値は次のとおりです。</p>
<ul>
<li><p>0 - 不明</p></li>
<li><p>1 - クライアントが登録解除を開始済み</p></li>
<li><p>2 - 登録期限切れ</p></li>
<li><p>3 - クライアントのクラッシュ</p></li>
<li><p>4 - ユーザー属性変更</p></li>
<li><p>5 - 優先レジストラー変更</p></li>
<li><p>6 - サバイバル モードのレガシ クライアント</p></li>
</ul></td>
</tr>
</tbody>
</table>

