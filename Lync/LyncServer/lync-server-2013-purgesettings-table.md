---
title: 'Lync Server 2013: PurgeSettings テーブル'
description: 'Lync Server 2013: PurgeSettings テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec2d1508d8362988bddbab2fe7303a23a8ee2d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559183"
---
# <a name="purgesettings-table-in-lync-server-2013"></a>Lync Server 2013 の PurgeSettings テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

PurgeSettings テーブルには、(およびいつ) 古くなった通話詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報が含まれています。 削除に関連する情報は、Microsoft Lync Server 2013 管理シェルから次のコマンドを実行することによって取得することもできます。

    Get-CsCdrConfiguration

管理者は、PurgeSettings テーブルを読み取り専用として扱う必要があります。呼び出し詳細の削除設定に対する変更は、 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) コマンドレットまたは [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) コマンドレットを使用してのみ実行する必要があります。

この表は、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Column</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>CDR 削除設定のコレクションの一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>True (1) に設定されている場合、Microsoft Lync Server 2013 は、古いレコードを CDR データベースから定期的に削除します。 削除は、毎日、PurgeHour 設定で指定された時間に行われます。 False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。 既定値は True です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>データベースから削除される CDR レコード (日数) を指定します。この場合、削除が有効になっていると、この値より古い CDR レコードがデータベースから削除されます。 既定値は 60 日です。</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>データベースから削除されるエラー報告レコード (日数) を指定します。削除が有効になっている場合は、この値よりも古いエラーレポートレコードがデータベースから削除されます。 既定値は 60 日です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>データベースの削除が行われるローカル時刻を指定します。 時刻は24時間形式を使用して指定されます。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。 指定できるのは1日の時間のみです。値 10 (10:00 AM) は許可されていますが、10:30 10.5 の (10:30 AM を示す) の値は許可されていません。 既定値は 2 (2:00 AM) です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

