---
title: PurgeSettings テーブル (QoE)
TOCTitle: PurgeSettings テーブル (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48271674
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PurgeSettings テーブル (QoE)

 

_**トピックの最終更新日:** 2015-03-09_

PurgeSettings テーブルには、古い QoE レコードを QoE データベースから自動的に削除するか、また削除する場合はどのタイミングで削除するかを指定する情報が含まれます。また、削除に関連する情報は、Microsoft Lync Server 2013 管理シェルから以下のコマンドを実行しても得られます。

    Get-CsQoEConfiguration

このテーブルは、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>QoE の削除設定のコレクションに対する一意識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>True (1) に設定すると、Microsoft Lync Server 2013は、QoE データベースから古いレコードを定期的に削除します。削除は、毎日、PurgeHour 設定で指定された時間に行われます。False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。既定値は True です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>データベースから削除する QoE レコードの保有期間を (日単位で) 指定します。削除が有効の場合、この値より古い QoE レコードはデータベースから削除されます。既定値は 60 日です。</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>データベースでの削除が行われる日のローカル時間を指定します。時刻は 24 時間制を使用して指定します。0 は夜中 12 時 (12:00 AM) を、23 は 11:00 PM を表します。指定できるのは時間のみです。(午前 10 時 00 分を意味する) 10 の値は指定できますが、(午前 10 時 30 分を意味する) 10.5 の値は指定できません。既定値は 1 です (AM 01:00:00)。</p></td>
</tr>
</tbody>
</table>

