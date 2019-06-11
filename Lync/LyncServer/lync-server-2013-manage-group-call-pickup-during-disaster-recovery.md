---
title: 'Lync Server 2013: 障害回復中にグループ通話のピックアップを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での障害回復中にグループ通話のピックアップを管理する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-30_

予期しないインシデントが原因でフロントエンドプールが利用できなくなった場合、サービスはバックアッププールにフェールオーバーされます。 バックアッププールへのフェールオーバー中は、ユーザーはバックアッププールにリダイレクトされ、回復性モードになります。 回復性モードでは、ユーザーは他のユーザーの通話を受けたり、他のユーザーがその通話をピックアップしたりすることはできません。 フェールオーバーが完了したら、ユーザーはグループ通話ピックアップを通常どおりに使うことができます。

プライマリプールへのフェールバック中に、ユーザーはプライマリプールにリダイレクトされ、復元モードになります。 グループ通話のピックアップ機能は、ユーザーが回復可能モードでなくなるまでは使用できません。

このセクションでは、障害回復中のグループ通話のピックアップに関するいくつかの考慮事項について説明し、ユーザーエクスペリエンスについても説明します。

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>障害回復中のグループ通話のピックアップに関する考慮事項

障害回復中に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、バックアッププールで実行されている Call パークアプリケーションを、通話ピックアップグループ番号として使用します。 そのため、障害回復中のグループ通話のピックアップのサポートでは、プライマリプールとバックアッププールの両方でコールパークアプリケーションを展開して有効にする必要があります。

通話パークのグループ通話の集配の番号範囲は、バックアッププールへのフェールオーバープロセスが完了した後に、バックアッププールにリダイレクトする必要があります。 プライマリプールへのフェールバックプロセスが完了した後は、番号範囲をプライマリプールに戻す必要があります。 グループ通話のピックアップ範囲をリダイレクトするには、 **CsCallParkOrbit**コマンドレットを使用します。

別の完全修飾ドメイン名 (FQDN) で新しいプールを展開してプライマリプールを置き換える場合は、プライマリプールに関連付けられていたすべてのグループ呼び出しのピックアップ番号の範囲を、新しいプールの FQDN に再割り当てする必要があります。 番号範囲を新しいプールに再割り当てするには、 **CsCallParkOrbit**コマンドレットを使用します。 **CsCallParkOrbit**コマンドレットの詳細については、「 [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)」を参照してください。

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>プール障害時のグループ通話のピックアップ操作

次の表は、障害回復のフェーズを通じたグループ通話のピックアップエクスペリエンスをまとめたものです。

### <a name="user-experience-during-disaster-recovery"></a>障害回復中のユーザーエクスペリエンス

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通話の状態</th>
<th>バックアッププールへのフェールオーバー</th>
<th>プライマリプールへのフェールバック</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新規通話</p></td>
<td><p><strong>フェールオーバー処理中:</strong></p>
<ul>
<li><p>回復可能モードのユーザーに対してグループ通話のピックアップが利用できない</p></li>
</ul>
<p><strong>フェールオーバーが完了したら、次の操作を行います。</strong></p>
<ul>
<li><p>ユーザの回復性とグループ通話の集配番号範囲にアクセスできない場合に使用可能なグループ通話のピックアップがバックアッププールにリダイレクトされる</p></li>
</ul></td>
<td><p><strong>フェールバック処理中:</strong></p>
<ul>
<li><p>回復可能モードのユーザーに対してグループ通話のピックアップが利用できない</p></li>
</ul>
<p><strong>フェールバックが完了したら、次の操作を行います。</strong></p>
<ul>
<li><p>ユーザの回復性とグループ通話の集配番号の範囲を使用しているユーザーが、プライマリプールにリダイレクトされた場合に、グループ通話のピックアップが利用可能になる</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>グループ通話のピックアップキューでの通話</p></td>
<td><p><strong>フェールオーバー処理中:</strong></p>
<ul>
<li><p>グループ通話のピックアップを使用して通話を発信することはできません。</p></li>
</ul>
<p><strong>フェールオーバーが完了したら、次の操作を行います。</strong></p>
<ul>
<li><p>この状態では通話はありません</p></li>
</ul></td>
<td><p><strong>フェールバック処理中:</strong></p>
<ul>
<li><p>グループ通話のピックアップを使用して通話を発信することはできません。</p></li>
</ul>
<p><strong>フェールバックが完了したら、次の操作を行います。</strong></p>
<ul>
<li><p>グループ通話のピックアップを使用して通話を発信することはできません。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>確立された通話</p></td>
<td><p><strong>フェールオーバー処理中:</strong></p>
<ul>
<li><p>通話が接続されたまま</p></li>
</ul>
<p><strong>フェールオーバーが完了したら、次の操作を行います。</strong></p>
<ul>
<li><p>通話が接続されたまま</p></li>
</ul></td>
<td><p><strong>フェールバック処理中:</strong></p>
<ul>
<li><p>通話が接続されたまま</p></li>
</ul>
<p><strong>フェールバックが完了したら、次の操作を行います。</strong></p>
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

