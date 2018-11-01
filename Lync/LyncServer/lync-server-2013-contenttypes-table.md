---
title: 'Lync Server 2013: ContentTypes テーブル'
TOCTitle: ContentTypes テーブル
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48273861
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の ContentTypes テーブル

 

_**トピックの最終更新日:** 2015-03-09_

ContentTypes テーブルは、ピア ツー ピア セッションと電話会議セッションの両方で使用されるコンテンツ タイプのリストを格納するサポート テーブルです。テーブルの各レコードは 1 つのコンテンツ タイプを表します。


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
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>コンテンツ タイプを表す一意の数値。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td> </td>
<td><p>コンテンツ タイプの名前。</p></td>
</tr>
</tbody>
</table>

