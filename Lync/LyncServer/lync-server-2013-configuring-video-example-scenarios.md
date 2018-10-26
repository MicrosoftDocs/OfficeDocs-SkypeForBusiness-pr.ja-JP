---
title: ビデオのシナリオ例の構成
TOCTitle: ビデオのシナリオ例の構成
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48273732
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ビデオのシナリオ例の構成

 

_**トピックの最終更新日:** 2015-03-09_

Lync 2013 は、1920 x 1080 フル高解像度 (HD) ビデオおよびギャラリー ビュー ビデオをサポートするための新しいビデオ機能を追加します。顧客データに基づく測定では、通常のビデオ帯域幅は Lync 2010 と比較してわずかしか増加していないが、フル HD サポートによって、ビデオ ストリームの最大帯域幅が増加していることが示されています (詳細については、「[Lync Server 2013 でのメディア トラフィックのネットワーク帯域幅の要件](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)」の「メディア トラフィック ネットワークの使用」セクションを参照してください)。したがって、管理者は、特定のユーザー (ネットワーク キャパシティが不十分なブランチ オフィスのユーザーなど) に対してビデオ帯域幅を制限し、他のユーザー (上級管理職など) に最善のビデオ品質を確保することができます。

次の表は、異なるネットワーク キャパシティ用にビデオを構成するための推奨設定の一覧です。これらの設定は、いくつかのユーザー シナリオで高解像度のビデオ (一番右側の列を参照してください) を送受信することを制限します。最小の設定値にすると、最大受信ネットワーク帯域幅が小さくなるため、ギャラリー ビデオが利用できなくなります。

### 推奨されるビデオ設定

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
<th>良好な品質のビデオに必要とされる解像度</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>最高</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>ピアツーピア: 最大 1920 x 1080 ビデオ解像度</p>
<p>ギャラリー ビュー: 最大 ２ つの 1920 x 1080 ビデオ、または複数の低解像度ビデオ</p></td>
</tr>
<tr class="even">
<td><p>良好</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>ピアツーピア: 最大 1280 x 720 ビデオ解像度</p>
<p>ギャラリー ビュー: 最大 5 つの 640 x 360 解像度ビデオ</p></td>
</tr>
<tr class="odd">
<td><p>中</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>ピアツーピア: 最大 960 x 540 ビデオ解像度</p>
<p>ギャラリー ビュー: 最大 5 つの 424 x 240 解像度ビデオ</p></td>
</tr>
<tr class="even">
<td><p>中</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>ピアツーピア: 最大 424 x 240 ビデオ解像度</p>
<p>ギャラリー ビュー: 利用不可</p></td>
</tr>
</tbody>
</table>


上記の表にある情報を使用して、新しい HD ビデオおよびギャラリー ビュー ビデオの会議機能を組織の一部のユーザー向けに展開しながら、異なるビデオ解像度を他のユーザーに提供することができます。

次の例では、管理者が新しいビデオ機能を展開し、上級管理職だけが最高のビデオ品質を利用できるようにしています。ネットワーク キャパシティが不十分なリモート ブランチ オフィスの従業員に対しては、上記の表の最小設定値のみが展開されています。他のすべての従業員に対しては、上記の表の「良好」な設定値が展開されています。

新しい機能を上級管理職に展開するために、管理者は、ExecutiveVideo という名前の会議ポリシーを作成します。この会議ポリシーは次のように設定されます。

  - VideoBitRateKB を 8000 Kbps に設定する。

  - TotalReceiveVideoBitRateKB を 8000 Kbps に設定する。

  - AllowMultiview を True に設定する。

  - EnableMultiviewJoin を True に設定する。

ブランチ オフィスの従業員に対して、管理者は BranchOfficeVideo という名前の会議ポリシーを作成します。この会議ポリシーは次のように設定されます。

  - VideoBitRateKB を 350 Kbps に設定する。

  - TotalReceiveVideoBitRateKB を 350 Kbps に設定する。

  - AllowMultiview を True に設定する。

  - EnableMultiviewJoin を False に設定する。

他のすべての従業員に対して、管理者は StandardVideo という名前の会議ポリシーを作成します。この会議ポリシーは次のように設定されます。

  - VideoBitRateKB を 2500 Kbps に設定する。

  - TotalReceiveVideoBitRateKB を 2500 Kbps に設定する。

  - AllowMultiview を True に設定する。

  - EnableMultiviewJoin を True に設定する。

管理者は、次のように会議ポリシーをユーザーに割り当てます。

  - ExecutiveVideo 会議ポリシーを上級管理職に割り当てる。

  - BranchOfficeVideo 会議ポリシーをブランチ オフィスの従業員すべてに割り当てる。

  - StandardVideo 会議ポリシーを他のすべての従業員に割り当てる。

これらの会議ポリシー割り当ては、次のユーザー エクスペリエンスをもたらします。

  - ユーザーが開催する会議はギャラリー ビューをサポートしますが、ブランチ オフィスの従業員はギャラリー ビューを利用できません。

  - 2 者間またはマルチパーティの会議で、上級管理職は 1920 x 1080 フル HD ビデオを送信したり (ハードウェアとネットワーク リンクがサポートしている場合)、他の参加クライアントがサポートしている 1920 x 1080 フル HD ビデオを受信したりできます。

  - 2 者間またはマルチパーティの会議で上級管理職以外の従業員が利用できるビデオは、上級管理職向けのものよりも低解像度になりますが、その解像度は良好です。

  - Lync が既定のビデオ ウィンドウ サイズを表示する場合、ブランチ オフィスの従業員は 2 者間の会議で良好なビデオ品質を利用できます。ただし、Lync のウィンドウが全画面表示になっている場合は、ビデオの解像度が向上しません。マルチパーティの会議の場合、ブランチ オフィスの従業員には、アクティブなビデオが 1 つしか表示されません。

