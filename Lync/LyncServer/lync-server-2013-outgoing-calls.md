---
title: 'Lync Server 2013: 発信通話'
TOCTitle: 発信通話
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994049(v=OCS.15)
ms:contentKeyID: 52056636
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の発信通話

 

_**トピックの最終更新日:** 2015-03-09_

場所に基づくルーティングが有効になっているユーザーの発信通話のルーティングは、ユーザーのエンドポイントが配置されているネットワークの場所に影響されます。次の表は、発信者のエンドポイントの場所によって、場所に基づくルーティングが発信通話のルーティングにどのように影響するかを示しています。

### 発信者から PSTN への発信通話

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ユーザーのエンドポイントが、場所に基づくルーティングが有効なネットワーク サイトにある</th>
<th>ユーザーのエンドポイントが不明なネットワーク サイトまたは場所に基づくルーティングが有効でないネットワーク サイトにある</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>発信の承認</p></td>
<td><p>通話はユーザーの音声ポリシーに基づいて承認される</p></td>
<td><p>通話はユーザーの音声ポリシーに基づいて承認される</p></td>
</tr>
<tr class="even">
<td><p>発信通話のルーティング</p></td>
<td><p>通話はネットワーク サイトの音声ルーティング ポリシーに従ってルーティングされる</p></td>
<td><p>通話はユーザーの音声ポリシーに従い、場所に基づくルーティングが有効になっていないトランク (使用可能な場合) のみを経由してルーティングされる</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### その他のリソース

[Lync Server 2013 の場所に基づくルーティングのシナリオ](lync-server-2013-scenarios-for-location-based-routing.md)

