---
title: 'Lync Server 2013: User テーブル'
TOCTitle: User テーブル
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48272384
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の User テーブル

 

_**トピックの最終更新日:** 2015-03-09_

User テーブルは、データベースに記録されるセッションに参加したさまざまなユーザーの一覧を格納するサポート テーブルです。このテーブルの各レコードは、1 人のユーザーを表しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このユーザーを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>一意</p></td>
<td><p>URI 文字列です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>1 は不明な URI の種類です。</p>
<p>2 はユーザーの URI です。</p>
<p>4 は電話会議の URI です。</p>
<p>8 は電話の URI です。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ユーザーのテナントであり、テナント テーブルから参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>ユーザーが低音質の通話を行った時点を示す最新のタイム スタンプです。</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>

