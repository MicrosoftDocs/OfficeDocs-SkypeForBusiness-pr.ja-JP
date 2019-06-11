---
title: 'Lync Server 2013: ビデオの例のシナリオを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>ビデオの構成 Lync Server 2013 のシナリオの例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

Lync 2013 では、1920 x 1080 full definition (HD) ビデオとギャラリービューのビデオをサポートする新しいビデオ機能が追加されています。 顧客データに基づく測定値は、一般的なビデオの帯域幅が Lync 2010 に比べてわずかに増加していますが、フル HD のサポートにより、ビデオストリームの最大帯域幅が増加していることを示しています (詳細については、「メディアトラフィックネットワークの使用状況」セクション[を参照してください)。Lync Server 2013 でのメディアトラフィックのネットワーク帯域幅要件](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)。 そのため、管理者は、特定のユーザー (ネットワーク容量が少ない支店のユーザーなど) のビデオ帯域幅を制限したり、他のユーザー (エグゼクティブなど) に最適なビデオ品質を確保したりすることができます。

次の表は、さまざまなネットワーク容量に対応したビデオを構成するための推奨される設定の一覧です。 これらの設定により、一部のユーザーシナリオでは、高解像度のビデオの送受信が制限されます (右端の列を参照)。 [最小] 設定では、ネットワーク帯域幅の上限が最大になったため、ギャラリーのビデオは利用できなくなります。

### <a name="recommended-video-settings"></a>推奨されるビデオ設定

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>高品質ビデオにはビデオ解像度が期待されている</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>よく</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>ピアツーピア: 最大 1920 x 1080 のビデオ解像度</p>
<p>ギャラリービュー: 最大 2 1920 x 1080 のビデオまたは複数の小さな解像度のビデオ</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>ピアツーピア: 最大 1280 x 720 のビデオ解像度</p>
<p>ギャラリービュー: 最大 5 640 x 360 解像度のビデオ</p></td>
</tr>
<tr class="odd">
<td><p>中</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>ピアツーピア: 最大 960 x 540 のビデオ解像度</p>
<p>ギャラリービュー: 最大 5 424 x 240 解像度のビデオ</p></td>
</tr>
<tr class="even">
<td><p>最低</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>ピアツーピア: 最大 424 x 240 のビデオ解像度</p>
<p>ギャラリービュー: 使用できません</p></td>
</tr>
</tbody>
</table>


上の表の情報を使用して、組織内の一部のユーザーにビデオ会議機能を追加し、他のユーザーには別のビデオ解像度を適用することができます。

次の例では、管理者が、最高のビデオ品質で、[エグゼクティブ] のみで利用可能な新しいビデオ機能をロールアウトします。 ネットワーク容量が少ないリモート支店の従業員については、上記の表の最小設定のみが展開されます。 その他のすべての従業員については、上記の表の "良好" 設定が展開されます。

新しい機能を役員にロールアウトするために、管理者は ExecutiveVideo という名前の会議ポリシーを作成します。 この会議ポリシーには、次の設定があります。

  - VideoBitRateKB が 8000 Kbps に設定されている

  - TotalReceiveVideoBitRateKB が 8000 Kbps に設定されている

  - AllowMultiview が True に設定されている

  - EnableMultiviewJoin が True に設定されている

支社の従業員の場合、管理者は BranchOfficeVideo という名前の会議ポリシーを作成します。 この会議ポリシーには、次の設定があります。

  - VideoBitRateKB が 350 Kbps に設定されている

  - TotalReceiveVideoBitRateKB が 350 Kbps に設定されている

  - AllowMultiview が True に設定されている

  - EnableMultiviewJoin が False に設定されている

他のすべての従業員の場合、管理者は StandardVideo という名前の会議ポリシーを作成します。 この会議ポリシーには、次の設定があります。

  - VideoBitRateKB が 2500 Kbps に設定されている

  - TotalReceiveVideoBitRateKB が 2500 Kbps に設定されている

  - AllowMultiview が True に設定されている

  - EnableMultiviewJoin が True に設定されている

管理者は、次のようにして会議ポリシーをユーザーに割り当てます。

  - ExecutiveVideo 会議のポリシーが役員に割り当てられます。

  - BranchOfficeVideo 会議ポリシーは、支社のすべての従業員に割り当てられます。

  - 標準ビデオ会議ポリシーは、他のすべての従業員に割り当てられます。

これらの会議ポリシーを割り当てると、次のユーザーエクスペリエンスが得られます。

  - 任意のユーザーサポートギャラリービューによって開催されたすべての会議。ただし、ブランチオフィスの従業員はギャラリービューを表示できません。

  - 2パーティまたはマルチパーティの会議では、役員は、1920 x 1080 のフル HD ビデオ (ハードウェアとネットワークリンクがサポートされている場合) を送信できます。また、他の参加者のクライアントがサポートしている 1920 x 1080 フル HD ビデオも受信できます。

  - エグゼクティブ以外の従業員は、2パーティまたはマルチパーティの会議では、役員よりも低い解像度で表示されますが、解決策は引き続き有効です。

  - Lync が既定のビデオウィンドウサイズで表示されている場合は、支社にいる従業員は、2パーティーの通話で優れたビデオ品質を得ることができます。ただし、Lync ウィンドウが全画面に最大化されている場合、ビデオの解像度は増加しません。 マルチパーティ会議の場合、支店の従業員は1つのアクティブなビデオのみを表示します。

</div>

<span> </span>

</div>

</div>

</div>

