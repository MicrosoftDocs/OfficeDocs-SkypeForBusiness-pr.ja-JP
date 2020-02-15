---
title: 'Lync Server 2013: 障害復旧時にグループ通話ピックアップを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a0abe6c64b0e6d5cba80c0adb6a01c5dbacb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での障害復旧時のグループ通話ピックアップの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

予期しないインシデントが発生したためにフロントエンドプールが使用できなくなった場合、サービスはバックアッププールにフェールオーバーされます。 バックアッププールへのフェールオーバー中に、ユーザーはバックアッププールにリダイレクトされ、復元モードになります。 復元モードでは、ユーザーは他のユーザーの通話を選択したり、他のユーザーがその通話を選択したりすることはできません。 フェールオーバーが完了すると、ユーザーは通常どおりグループ通話ピックアップを使用できるようになります。

プライマリプールへのフェールバック時に、ユーザーはプライマリプールにリダイレクトされ、再び復元モードになります。 グループ通話ピックアップ機能は、ユーザーが復元モードを終了するまで使用できません。

このセクションでは、障害復旧時のグループ通話ピックアップと、ユーザー環境についての考慮事項について説明します。

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>障害復旧時のグループ通話ピックアップに関する考慮事項

障害復旧時に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、通話ピックアップグループ番号のバックアッププールで実行されているコールパークアプリケーションを使用します。 そのため、障害復旧時にグループ通話ピックアップをサポートするには、プライマリプールとバックアッププールの両方でコールパークアプリケーションを展開して有効にする必要があります。

コールパークオービットテーブルのグループ通話ピックアップ番号の範囲は、バックアッププールへのフェールオーバープロセスが完了した後に、バックアッププールにリダイレクトされる必要があります。 プライマリプールへのフェールバックプロセスが完了したら、番号の範囲をプライマリプールにリダイレクトする必要があります。 グループ通話のピックアップ範囲をリダイレクトするには、 **get-cscallparkorbit**コマンドレットを使用します。

プライマリプールを置き換えるために別の完全修飾ドメイン名 (FQDN) を使用して新しいプールを展開する場合は、プライマリプールに関連付けられているすべてのグループ通話ピックアップ番号の範囲を新しいプールの FQDN に再割り当てする必要があります。 番号範囲を新しいプールに再割り当てするには、 **get-cscallparkorbit**コマンドレットを使用できます。 **Get-cscallparkorbit**コマンドレットの詳細については、「 [get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)」を参照してください。

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>プール障害時のグループ通話ピックアップ環境

次の表では、障害復旧のフェーズを通じてグループ通話ピックアップの使用状況を要約しています。

### <a name="user-experience-during-disaster-recovery"></a>障害復旧時のユーザーの利便性

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>呼び出しの状態</th>
<th>バックアッププールへのフェールオーバー</th>
<th>プライマリプールへのフェールバック</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新しい通話</p></td>
<td><p><strong>フェールオーバー処理中:</strong></p>
<ul>
<li><p>復元モードでユーザーがグループ通話ピックアップを使用できない</p></li>
</ul>
<p><strong>フェールオーバーが完了した後:</strong></p>
<ul>
<li><p>ユーザーの復元性とグループ通話ピックアップ番号の範囲がバックアッププールにリダイレクトされるときに使用可能なグループ通話ピックアップ</p></li>
</ul></td>
<td><p><strong>フェールバック処理中:</strong></p>
<ul>
<li><p>復元モードでユーザーがグループ通話ピックアップを使用できない</p></li>
</ul>
<p><strong>フェールバックが完了すると、次のようになります。</strong></p>
<ul>
<li><p>ユーザーが復元可能で、グループ通話ピックアップ番号の範囲がプライマリプールに再びリダイレクトされるときに使用できるグループ通話ピックアップ</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>グループ通話ピックアップキューの呼び出し</p></td>
<td><p><strong>フェールオーバー処理中:</strong></p>
<ul>
<li><p>キューの呼び出しは、グループ通話ピックアップで応答できません。</p></li>
</ul>
<p><strong>フェールオーバーが完了した後:</strong></p>
<ul>
<li><p>この状態の通話はありません</p></li>
</ul></td>
<td><p><strong>フェールバック処理中:</strong></p>
<ul>
<li><p>キューの呼び出しは、グループ通話ピックアップで応答できません。</p></li>
</ul>
<p><strong>フェールバックが完了すると、次のようになります。</strong></p>
<ul>
<li><p>キューの呼び出しは、グループ通話ピックアップで応答できません。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>確立された通話</p></td>
<td><p><strong>フェールオーバー処理中:</strong></p>
<ul>
<li><p>通話が接続されたまま</p></li>
</ul>
<p><strong>フェールオーバーが完了した後:</strong></p>
<ul>
<li><p>通話が接続されたまま</p></li>
</ul></td>
<td><p><strong>フェールバック処理中:</strong></p>
<ul>
<li><p>通話が接続されたまま</p></li>
</ul>
<p><strong>フェールバックが完了すると、次のようになります。</strong></p>
<ul>
<li><p>通話が接続されたまま</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

