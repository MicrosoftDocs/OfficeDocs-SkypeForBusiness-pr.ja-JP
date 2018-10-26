---
title: VoIPDetails ビュー
TOCTitle: VoIPDetails ビュー
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49886850
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VoIPDetails ビュー

 

_**トピックの最終更新日:** 2015-03-09_

VoIPDetails ビューには、少なくとも 1 人のユーザーが VoIP ユーザーであるピアツーピア セッションに関する情報が格納されます。このビューは Microsoft Lync Server 2013 で導入されました。

> [!NOTE]
> VoIPDetails ビューには、<a href="lync-server-2013-sessiondetails-view.md">SessionDetails ビュー</a>のすべての列のほか、次の列が含まれす。



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
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを開始したユーザーの 電話 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションに参加したユーザーの 電話 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを切断したユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>セッションを切断したユーザーの URI の種類。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>セッションを切断したユーザーのテナント。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>セッションを切断したユーザーの 電話 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>セッションを開始したユーザーの仲介サーバー。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>セッションに参加したユーザーの仲介サーバー。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>セッションを開始したユーザーが使用するゲートウェイ。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>セッションに参加したユーザーが使用するゲートウェイ。</p></td>
</tr>
</tbody>
</table>

