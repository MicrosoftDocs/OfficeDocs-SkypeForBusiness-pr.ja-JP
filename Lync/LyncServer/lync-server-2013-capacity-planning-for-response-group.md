---
title: 'Lync Server 2013: 応答グループの処理能力の計画'
TOCTitle: 応答グループの処理能力の計画
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48273143
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の応答グループの処理能力の計画

 

_**トピックの最終更新日:** 2015-03-09_

次の表は、処理能力の計画要件の土台として使用できる、 応答グループのユーザー モデルを示しています。

> [!NOTE]
> 次の表の数字は、すべての応答グループのオーディオ ファイルに、16 kHz、モノ、16 ビットの WAVE (.wav) ファイルを使用することを前提としています。Windows Media Audio (.wma) ファイルなどの他のファイル形式を使用した場合は、数字が変わる可能性があります。



> [!IMPORTANT]
> 障害復旧のキャパシティ計画時には、ペアになっているプールの各プールで、両方のプールに含まれるすべての応答グループのワークロードを処理する必要があることを念頭においてください。



### 応答グループのユーザー モデル

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>指標</th>
<th>Enterprise Edition プールごと (8 つのフロントエンド サーバー)</th>
<th>Standard Edition サーバーごと</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 秒あたりの着信</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>IVR または MoH に接続した同時通話</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>匿名の同時セッション (IM なし)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>匿名の同時セッション (IM あり)</p></td>
<td><p>64</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>アクティブ エージェント (公式および非公式)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>ハント グループ数</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>IVR グループ数 (音声認識を使用)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>

