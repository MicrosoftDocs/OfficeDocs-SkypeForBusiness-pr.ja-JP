---
title: 'Lync Server 2013: ユーザー テーブル'
TOCTitle: ユーザー テーブル
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48273184
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のユーザー テーブル

 

_**トピックの最終更新日:** 2015-03-09_

ユーザー テーブルは補助的なテーブルです。このテーブルの個々のレコードには、データベースに記録が残された通話またはセッションに関係する特定のユーザーの情報が格納されています。


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>タイム スタンプ (社内使用向け)。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このユーザーを識別する一意の番号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p>ユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このユーザーのテナント ID。詳細については、「<a href="lync-server-2013-tenants-table.md">Lync Server 2013 の Tenants テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このユーザーの URI の種類。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

