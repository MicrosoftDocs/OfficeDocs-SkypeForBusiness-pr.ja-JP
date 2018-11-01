---
title: PurgeSettings テーブル
TOCTitle: PurgeSettings テーブル
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48273013
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PurgeSettings テーブル

 

_**トピックの最終更新日:** 2015-03-09_

PurgeSettings テーブルには、古くなった通話詳細記録を CDR データベースから自動的に削除するかどうか (およびいつ削除するか) を指定する情報が含まれています。削除関連の情報は、Microsoft Lync Server 2013 管理シェルで次のコマンドを実行して取得することもできます。

    Get-CsCdrConfiguration

PurgeSettings テーブルは読み取り専用として扱う必要があります。通話詳細記録の削除設定を変更するには、[New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) コマンドレットまたは [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) コマンドレットを使用する必要があります。

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
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>CDR 削除設定のコレクションの一意の識別子です。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>True (1) に設定すると、古くなったレコードが CDR データベースから定期的に削除されます。削除は、PurgeHour の設定で指定した時刻に毎日行われます。False (0) に設定すると、データベースのレコードは自動的に削除されません。既定値は True です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>データベースから削除する CDR レコードの保管期間 (日数) を指定します。削除が有効になっている場合、この値より古い CDR レコードがデータベースから削除されます。既定値は 60 日です。</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>データベースから削除するエラー レポート レコードの保管期間 (日数) を指定します。削除が有効になっている場合、この値より古いエラー レポート レコードがデータベースから削除されます。既定値は 60 日です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>データベースの削除を実行するローカル時刻を指定します。時刻は 24 時間制を使用して指定します。0 は夜中 12 時 (12:00 AM) を、23 は 11:00 PM を表します。指定できるのは時間のみです。したがって、値 10 (10:00 AM) は使用できますが、値 10:30 や 10.5 (10:30 AM) は使用できません。この既定値は 2 (2:00 AM) です。</p></td>
</tr>
</tbody>
</table>

