---
title: 'Lync Server 2013: ビデオサンプルシナリオの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71eb886bb50f503b43eb757cc41310583fc11303
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Lync Server 2013 のビデオサンプルシナリオの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

Lync 2013 は、1920 x 1080 完全高品位 (HD) ビデオおよびギャラリービューのビデオをサポートする新しいビデオ機能を追加します。 お客様のデータに基づく測定値は、一般的なビデオ帯域幅が Lync 2010 に比べてわずかに増加しましたが、フル HD サポートのために最大ビデオストリーム帯域幅が増加しています。詳細については、「 [media traffic for media トラッフィック In Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)」の「Media Traffic network Usage」セクションを参照してください。 そのため、管理者は特定のユーザー (ネットワークの容量が少ない支社のユーザーなど) のビデオ帯域幅を制限したり、他のユーザー (エグゼクティブなど) に最適なビデオ品質を確保するために役立てることができます。

次の表に、さまざまなネットワーク容量に対してビデオを構成する際に推奨される設定の一覧を示します。 これらの設定により、一部のユーザーシナリオでは、より高解像度のビデオを送受信することができなくなります (右端の列を参照)。 最小値を設定すると、最大受信ネットワーク帯域幅が少ないため、ギャラリーのビデオが使用できなくなります。

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
<th>良好な品質のビデオに必要なビデオ解像度</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>高</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>ピアツーピア: 最大 1920 x 1080 ビデオ解像度</p>
<p>ギャラリービュー: 最大 2 1920 x 1080 ビデオまたは複数の解像度のビデオ</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>ピアツーピア: 最大 1280 x 720 ビデオ解像度</p>
<p>ギャラリービュー: 最大 5 640 x 360 解像度のビデオ</p></td>
</tr>
<tr class="odd">
<td><p>中</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>ピアツーピア: 最大 960 x 540 ビデオ解像度</p>
<p>ギャラリービュー: 最大 5 424 x 240 解像度のビデオ</p></td>
</tr>
<tr class="even">
<td><p>最小値</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>ピアツーピア: 最大 424 x 240 ビデオ解像度</p>
<p>ギャラリービュー: 使用不可</p></td>
</tr>
</tbody>
</table>


前の表に記載されている情報を使用して、新しい HD ビデオおよびギャラリービューのビデオ会議機能を組織の一部のユーザーに展開する一方で、他のユーザーがさまざまなビデオ解像度を使用できるようにすることができます。

次の例では、管理者は、エグゼクティブのみが利用できる最高のビデオ品質で新しいビデオ機能をロールアウトします。 ネットワークの容量が少ないリモートブランチオフィスの従業員の場合、上記の表の最小設定のみが展開されます。 他のすべての従業員の場合、上記の表にある "Good" 設定が展開されます。

エグゼクティブに新機能をロールアウトするために、管理者は ExecutiveVideo という名前の会議ポリシーを作成します。 この会議ポリシーには、次の設定があります。

  - VideoBitRateKB は 8000 Kbps に設定されています。

  - TotalReceiveVideoBitRateKB は 8000 Kbps に設定されています。

  - AllowMultiview が True に設定されている

  - EnableMultiviewJoin が True に設定されている

ブランチオフィスの従業員の場合、管理者は BranchOfficeVideo という名前の会議ポリシーを作成します。 この会議ポリシーには、次の設定があります。

  - VideoBitRateKB は 350 Kbps に設定されています。

  - TotalReceiveVideoBitRateKB は 350 Kbps に設定されています。

  - AllowMultiview が True に設定されている

  - EnableMultiviewJoin が False に設定されている

他のすべての従業員の場合、管理者は StandardVideo という名前の会議ポリシーを作成します。 この会議ポリシーには、次の設定があります。

  - VideoBitRateKB は 2500 Kbps に設定されています。

  - TotalReceiveVideoBitRateKB は 2500 Kbps に設定されています。

  - AllowMultiview が True に設定されている

  - EnableMultiviewJoin が True に設定されている

管理者は、次のように会議ポリシーをユーザーに割り当てます。

  - ExecutiveVideo 会議ポリシーが役職者に割り当てられます。

  - BranchOfficeVideo 会議ポリシーは、ブランチオフィスのすべての従業員に割り当てられます。

  - StandardVideo 会議ポリシーは、他のすべての従業員に割り当てられます。

これらの会議ポリシーの割り当てによって、次のようなユーザーの環境が発生します。

  - 任意のユーザーによって開催されたすべての会議はギャラリービューをサポートしますが、ブランチオフィスの従業員はギャラリービューを利用できません。

  - 2パーティまたはマルチパーティの会議の場合、エグゼクティブは 1920 x 1080 フル HD ビデオを送信できます。ハードウェアとネットワークリンクがサポートしている場合は、他の参加者のクライアントがサポートしている 1920 x 1080 フル HD ビデオを受信できます。

  - エグゼクティブではない従業員は、2者またはマルチパーティの会議では、エグゼクティブよりも低い解像度で表示されますが、適切な解決策を得ることができます。

  - Lync が既定のビデオウィンドウサイズを表示すると、ブランチオフィスの従業員は、2者間通話で優れたビデオ品質を得ることができます。ただし、Lync ウィンドウが全画面表示に最大化されている場合は、ビデオ解像度は上がりません。 マルチパーティ会議では、ブランチオフィスの従業員には1つのアクティブなビデオのみが表示されます。

</div>

<span> </span>

</div>

</div>

</div>

