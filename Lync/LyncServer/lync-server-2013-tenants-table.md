---
title: 'Lync Server 2013: Tenants テーブル'
TOCTitle: Tenants テーブル
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48273488
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Tenants テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Tenants テーブルは、各種テナントの一覧を格納しているサポート テーブルです。テーブル内の各レコードが 1 つのテナントを表します。

> [!NOTE]
> 内部設置型展開では、CDR は組み込みのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。



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
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このテナント ID を識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>有効な値は次のとおりです。</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 - エンタープライズ</p></li>
<li><p>00000000-0000-0000-0000-000000000001 - フェデレーション</p></li>
<li><p>00000000-0000-0000-0000-000000000002 - 匿名</p></li>
<li><p>00000000-0000-0000-0000-000000000003 - パブリック IM 接続</p></li>
</ul></td>
</tr>
</tbody>
</table>

