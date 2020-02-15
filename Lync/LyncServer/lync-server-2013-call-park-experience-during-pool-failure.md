---
title: 'Lync Server 2013: プール障害時のコールパーク環境'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a89acc193f70ba5047a2f1c6362b957d182afdb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>プール障害発生時の Lync Server 2013 でのコールパークの動作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-10_

予期しないインシデントが発生したためにフロントエンドプールが使用できなくなった場合、保留されたがまだ取得されていない呼び出しは切断されます。 バックアッププールへのフェールオーバー中、ユーザーはバックアッププールにリダイレクトされ、復元モードになります。 復元モードでは、ユーザーは通話をパークできませんが、通話を保留にして転送することができます。 フェールオーバーが完了すると、通常どおりに通話を保留して取得することができます。 フェールバック時に、ユーザーは復元モードが解除されるまで通話をパークできません。

障害復旧時に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、バックアッププールに展開されているコールパークアプリケーションを使用します。 そのため、バックアッププールにリダイレクトされたユーザーは、バックアッププールのコールパークアプリケーションに対して構成されているコールパーク設定を使用します。

次の表では、障害復旧のフェーズを通じてコールパークの使用状況を要約しています。

### <a name="user-experience-during-disaster-recovery"></a>障害復旧時のユーザーの利便性

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼び出しの状態</th>
<th>停止が発生した場合</th>
<th>フェールオーバー中</th>
<th>フェールバック中</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>通話はまだパークされていません</p></td>
<td><p>通話は接続されたままですが、パークすることはできません。</p></td>
<td><ul>
<li><p>フェールオーバー中は、ユーザーが復元モードの間は通話をパークすることはできませんが、通話を保留および転送することはできます。</p></li>
<li><p>フェールオーバーが完了すると、通話をパークおよび取得できます。</p></li>
</ul></td>
<td><ul>
<li><p>フェールバック時に、ユーザーが復元モードの間は通話を保留することはできませんが、保留にして転送することはできます。</p></li>
<li><p>フェールバックが完了すると、通話をパークおよび取得できます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>コールパーク (まだ取得されていない)</p></td>
<td><p>通話は切断されます。</p></td>
<td><p>この状態の通話はありません。</p></td>
<td><p>通話は保留中のままになります。</p></td>
</tr>
<tr class="odd">
<td><p>既に取得された保留中の通話</p></td>
<td><p>通話は接続されたままです。</p></td>
<td><p>通話は接続されたままです。</p></td>
<td><p>通話は接続されたままです。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

