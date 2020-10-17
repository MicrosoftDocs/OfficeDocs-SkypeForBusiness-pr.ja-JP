---
title: 'Lync Server 2013: QoE ビューの詳細'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bba917427e42dcba689d3b248c7d889c798368f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512164"
---
# <a name="qoe-view-details-in-lync-server-2013"></a>Lync Server 2013 の QoE ビューの詳細

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

ビューは、QoE SQL データベースからデータを返すための最も一般的なシナリオをカバーしています。 データベーステーブルに直接アクセスするのではなく、カスタムレポートを作成するために使用することをお勧めします。これは、ビューが今後のリリースとの下位互換性を維持する可能性が高くなるためです。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ビュー名</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 の AudioStreamDetail ビュー</a></p></td>
<td><p>データベース内の各オーディオ ストリームについての情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">Lync Server 2013 の MediaLine ビュー</a></p></td>
<td><p>データベース内の各メディア ラインについての情報を格納します。 通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。 また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 の NetworkConfigurationSettings ビュー</a></p></td>
<td><p>ネットワーク構成についての情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Lync Server 2013 のセッションビュー</a></p></td>
<td><p>データベース内のレコードを持つセッションについての情報を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">Lync Server 2013 の UserAgent ビュー</a></p></td>
<td><p>データベース内のレコードを持つセッションに関与しているユーザー エージェントについての情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 の VideoStreamDetail ビュー</a></p></td>
<td><p>データベース内の各ビデオ ストリームについての情報を格納します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

