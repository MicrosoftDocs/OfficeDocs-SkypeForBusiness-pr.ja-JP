---
title: 'Lync Server 2013: PurgeSettings table (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46516be447fa3099afe492e5edc4f4008ea5a079
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>Lync Server 2013 の PurgeSettings テーブル (QoE)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

PurgeSettings テーブルには、古い品質のエクスペリエンスレコードが QoE データベースから自動的に削除されるかどうかを指定する情報が含まれています。 また、次のコマンドを実行することで、Microsoft Lync Server 2013 管理シェル内からパージに関連する情報を取得することもできます。

    Get-CsQoEConfiguration

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
<td><p>Primary</p></td>
<td><p>QoE の消去設定のコレクションの一意の識別子です。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>True (1) に設定すると、Microsoft Lync Server 2013 は、古いレコードを QoE データベースから定期的に削除します。 パージは、PurgeHour 設定によって指定されたサントメで毎日行われます。 False (0) に設定すると、レコードはデータベースから自動的に削除されません。 既定値は True です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>データベースから削除される QoE レコード (日数) を指定します。 [削除] が有効になっていると、この値よりも古い QoE レコードはデータベースから削除されます。 既定値は60日です。</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>データベースの消去が行われるローカル時刻を指定します。 時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。 時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。 既定値は 1 (1:00 AM) です。 データベースの消去が行われるローカル時刻を指定します。 時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。 時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。 既定値は 1 (1:00 AM) です。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

