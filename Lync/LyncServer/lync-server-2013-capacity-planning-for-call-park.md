---
title: 'Lync Server 2013: コール パークの処理能力計画'
TOCTitle: コール パークの処理能力計画
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48272493
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のコール パークの処理能力計画

 

_**トピックの最終更新日:** 2015-03-09_

次の表は、処理能力の計画要件の土台として使用できる、 コール パークのユーザー モデルを示しています。


> [!IMPORTANT]
> 障害復旧に関する処理能力の計画では、ペアになったプールの各プールが双方のプール内の コール パーク サービスの負荷を処理できる必要があります。



### コール パークのユーザー モデル

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>指標</th>
<th>フロント エンド プールごと (8 つのフロントエンド サーバー)</th>
<th>Standard Edition サーバーごと</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>保留率</p></td>
<td><p>8 分間に 1 回</p></td>
<td><p>1 分間に 1 回</p></td>
</tr>
<tr class="even">
<td><p>取得通話保留率</p></td>
<td><p>8 分間に 1 回</p></td>
<td><p>1 分間に 1 回</p></td>
</tr>
<tr class="odd">
<td><p>平均保留時間</p></td>
<td><p>60 秒</p></td>
<td><p>60 秒</p></td>
</tr>
</tbody>
</table>

