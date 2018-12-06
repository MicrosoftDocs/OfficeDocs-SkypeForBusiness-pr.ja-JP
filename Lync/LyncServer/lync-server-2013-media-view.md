---
title: メディア ビュー
TOCTitle: メディア ビュー
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49886860
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# メディア ビュー

 

_**トピックの最終更新日:** 2015-03-09_

Media ビューには、ピアツーピア セッションで使用される 1 つのメディア種類に関する情報が格納されます。複数のメディア種類が使用されている場合、1 つのセッションがテーブルでは複数のレコードによって表されます。このビューは Microsoft Lync Server 2013 で導入されました。

> [!NOTE]
> Media ビューを使用してセッションでのメディアの継続時間を計算することはできません。このビューには、セッションでのメディア交換の信号の詳細が格納されます。メディア交換は INVITE 要求によって行われ、StartTime は INVITE が送信された時刻を示します。メディアはセッションが受け付けられた後にのみ開始するので、招待時間は必ずしもメディアの開始時刻を意味しません。


Media ビューには、次に示す列に加えて、[SessionDetails ビュー](lync-server-2013-sessiondetails-view.md)内のすべての列が含まれます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>メディア種類。詳細については、「<a href="lync-server-2013-medialist-table.md">Lync Server 2013 の MediaList テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>メディア要求が送信された時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>セッションの終了時刻。</p></td>
</tr>
</tbody>
</table>

