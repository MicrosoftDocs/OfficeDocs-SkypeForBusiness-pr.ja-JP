---
title: ConferenceMessageCount ビュー
TOCTitle: ConferenceMessageCount ビュー
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49887046
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceMessageCount ビュー

 

_**トピックの最終更新日:** 2015-03-09_

ConferenceMessageCount ビューには、ユーザーが電話会議に送信したメッセージ数に関する情報が格納されます。このビューは、Microsoft Lync Server 2013 で導入されました。

> [!NOTE]
> ConferenceMessageCount ビューには、次に示す列に加えて「<a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails ビュー</a>」のすべての列が含まれます。



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
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>メッセージを送信したユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>メッセージを送信したユーザーの URI の種類。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>メッセージを送信したユーザーのテナント。詳細については、「<a href="lync-server-2013-tenants-table.md">Lync Server 2013 の Tenants テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>電話会議セッション中にユーザーが送信したメッセージの数。</p></td>
</tr>
</tbody>
</table>

