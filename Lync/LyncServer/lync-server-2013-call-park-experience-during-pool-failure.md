---
title: 'Lync Server 2013: プール障害時のコール パーク エクスペリエンス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>プール障害時の Lync Server 2013 のコール パーク エクスペリエンス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-10_

予期しないインシデントが原因で、フロントエンドプールが利用できなくなった場合、保留になっているがまだ取得されていない呼び出しは切断されます。 バックアッププールへのフェールオーバー中は、ユーザーはバックアッププールにリダイレクトされ、回復性モードになります。 回復可能モードでは、ユーザーは電話をパークすることはできませんが、通話を保留にして転送することができます。 フェールオーバーが完了すると、通常どおりに通話を保留したり、取得したりすることができます。 フェールバック中は、回復性モードが終了するまで、ユーザーは通話をパークすることはできません。

障害回復中に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、バックアッププールに展開されているコールパークアプリケーションを使用します。 そのため、バックアッププールにリダイレクトされたユーザーは、バックアッププール内のコールパークアプリケーション用に構成されているコールパーク設定を使用します。

次の表は、障害回復のフェーズを通して、コールパークのエクスペリエンスをまとめたものです。

### <a name="user-experience-during-disaster-recovery"></a>障害回復中のユーザーエクスペリエンス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通話の状態</th>
<th>障害が発生した場合</th>
<th>フェールオーバー中</th>
<th>フェールバック時</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>まだ保留中の通話はありません</p></td>
<td><p>通話は接続されたままですが、保留にできません。</p></td>
<td><ul>
<li><p>フェールオーバー中に、ユーザーが回復可能モードになっている間は、通話を保留にすることはできませんが、保留にして転送することはできます。</p></li>
<li><p>フェールオーバーが完了したら、通話を保留および取得することができます。</p></li>
</ul></td>
<td><ul>
<li><p>フェールバック中に、ユーザーが回復可能モードになっている間は、通話を保留にすることはできませんが、保留にして転送することはできます。</p></li>
<li><p>フェールバックが完了すると、通話を保留および取得することができます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>保留中の通話はまだ取得されていません</p></td>
<td><p>通話が切断されました。</p></td>
<td><p>この状態では、通話はありません。</p></td>
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

