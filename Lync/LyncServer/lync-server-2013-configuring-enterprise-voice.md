---
title: Lync Server 2013 でのエンタープライズ VoIP の構成
TOCTitle: Lync Server 2013 でのエンタープライズ VoIP の構成
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994041(v=OCS.15)
ms:contentKeyID: 52056632
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのエンタープライズ VoIP の構成

 

_**トピックの最終更新日:** 2015-03-09_

エンタープライズ VoIP を展開するには、次の操作を実行する必要があります。

  - トランクの作成

  - 音声ポリシーの定義

  - 音声ルートの作成

  - エンタープライズ VoIP に対するユーザーの有効化

## トランクの作成

エンタープライズ VoIP 展開にトランクを定義する必要があります。場所に基づくルーティングでは、トランクごとにトランク構成を作成する必要があります。Lync Serverトポロジ ビルダーを使用してトランクを定義し、Lync ServerWindows PowerShell コマンドの New-CsTrunkConfiguration または Lync Server コントロール パネルを使用して対応するトランク構成を定義します。トランク構成で場所に基づくルーティングを有効にする方法の詳細については、「[Lync Server 2013 での場所に基づくルーティングの有効化](lync-server-2013-enabling-location-based-routing.md)」の「トランクに対する場所に基づくルーティングの有効化」を参照してください。この例では、このシナリオで使用されるトランクを次の表に示します。

詳細については、「[Lync Server 2013 でのトポロジ ビルダーでの追加トランクの定義](lync-server-2013-define-additional-trunks-in-topology-builder.md)」を参照してください。


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>トランク名</th>
<th>システムの種類</th>
<th>名前</th>
<th>場所</th>
<th>仲介サーバー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トランク 1 DEL-GW</p></td>
<td><p>PSTN ゲートウェイ</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>トランク 2 HYD-GW</p></td>
<td><p>PSTN ゲートウェイ</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>トランク 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>トランク 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>



## 音声ポリシーの定義

エンタープライズ VoIP 展開の音声ポリシーを定義する必要があります。ユーザーのサブネットのみが場所に基づくルーティングを使用する必要がある場合は、音声ポリシーを定義して、場所に基づくルーティングの制約をユーザーのサブネットに適用します。この例では、次の表に示す音声ポリシーをこのシナリオで使用しています。わかりやすく説明するために、表に含まれているのは場所に基づくルーティングに固有の設定のみです。

詳細については、「[Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)」を参照してください。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>音声ポリシー 1</th>
<th>音声ポリシー 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声ポリシー ID</p></td>
<td><p>Delhi の音声ポリシー</p></td>
<td><p>Hyderabad の音声ポリシー</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用法</p></td>
<td><p>Delhi の使用法、PBX Del の使用法、PBX Hyd の使用法</p></td>
<td><p>Hyderabad の使用法、PBX Hyd の使用法、PBX Del の使用法</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>



## 音声ルートの定義

エンタープライズ VoIP 展開の音声ルートを定義する必要があります。この例では、次の表に示す音声ルートをこのシナリオで使用しています。わかりやすく説明するために、表に含まれているのは場所に基づくルーティングに固有の設定のみです。

詳細については、「[Lync Server 2013 での発信通話用のボイス ルートの構成](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)」を参照してください。


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>音声ルート 1</th>
<th>音声ルート 2</th>
<th>音声ルート 3</th>
<th>音声ルート 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名前</p></td>
<td><p>Delhi のルート</p></td>
<td><p>Hyderabad のルート</p></td>
<td><p>PBX Del のルート</p></td>
<td><p>PBX Hyd のルート</p></td>
</tr>
<tr class="even">
<td><p>PSTN 使用法</p></td>
<td><p>Delhi の使用法</p></td>
<td><p>Hyderabad の使用法</p></td>
<td><p>PBX Del の使用法</p></td>
<td><p>PBX Hyd の使用法</p></td>
</tr>
<tr class="odd">
<td><p>トランク</p></td>
<td><p>トランク 1 DEL-GW</p></td>
<td><p>トランク 2 HYD-GW</p></td>
<td><p>トランク 3 DEL-PBX</p></td>
<td><p>トランク 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>



## エンタープライズ VoIP に対するユーザーの有効化

ユーザーをエンタープライズ VoIP に対して有効にして、前に定義した音声ポリシーを割り当てます。この例では、次の表に示す割り当てをこのシナリオで使用しています。わかりやすく説明するために、表に含まれているのは場所に基づくルーティングに固有の設定のみです。

詳細については、「[Lync Server 2013 でのエンタープライズ VoIP に対するユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Delhi に配置されたユーザー</th>
<th>Hyderabad に配置されたユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>関連する音声ポリシー</p></td>
<td><p>Delhi の音声ポリシー</p></td>
<td><p>Hyderabad の音声ポリシー</p></td>
</tr>
<tr class="even">
<td><p>サンプル ユーザー</p></td>
<td><p>DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>



## 関連項目

#### その他のリソース

[Lync Server 2013 の場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)

