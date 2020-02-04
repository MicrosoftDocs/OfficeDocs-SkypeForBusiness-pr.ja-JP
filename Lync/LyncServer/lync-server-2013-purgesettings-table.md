---
title: 'Lync Server 2013: PurgeSettings テーブル'
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
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Lync Server 2013 の PurgeSettings テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

PurgeSettings テーブルには、古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報が含まれています。 また、次のコマンドを実行することで、Microsoft Lync Server 2013 管理シェル内からパージに関連する情報を取得することもできます。

    Get-CsCdrConfiguration

管理者は、PurgeSettings テーブルを読み取り専用として扱う必要があります。呼び出しの詳細の消去設定への変更は、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)または[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration)コマンドレットを使用して行う必要があります。

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
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>CDR 消去設定のコレクションの一意の識別子です。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>True に設定すると (1) Microsoft Lync Server 2013 は、古いレコードを CDR データベースから定期的に削除します。 パージは、PurgeHour 設定によって指定されたサントメで毎日行われます。 False (0) に設定すると、レコードはデータベースから自動的に削除されません。 既定値は True です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>データベースから削除される CDR レコード (日数) を指定します。 [削除] が有効になっていると、この値よりも古い CDR レコードがデータベースから削除されます。 既定値は60日です。</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>データベースから削除されるエラーレポートレコード (日数) を指定します。 [削除] を有効にすると、この値よりも古いエラーレポートレコードがデータベースから削除されます。 既定値は60日です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>データベースの消去が行われるローカル時刻を指定します。 時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。 時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。 既定値は 2 (2:00 AM) です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

